---
title: 异常处理-CLR 下的行为差异 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- EXCEPTION_CONTINUE_EXECUTION macro
- set_se_translator function
ms.assetid: 2e7e8daf-d019-44b0-a51c-62d7aaa89104
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5423e7c5b607f8a38a123a1c7f52c26f305ddb64
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380602"
---
# <a name="differences-in-exception-handling-behavior-under-clr"></a>/CLR 下的异常处理行为的差异

[使用托管异常中的基本概念](../dotnet/basic-concepts-in-using-managed-exceptions.md)讨论托管应用程序中处理的异常。 本主题中详细讨论了异常处理的标准行为中的差异以及某些限制。 有关详细信息，请参阅[_set_se_translator 函数](../c-runtime-library/reference/set-se-translator.md)。

##  <a name="vcconjumpingoutofafinallyblock"></a> 跳出 Finally 块

在本机 C/c + + 代码中，跳出 __**最后**尽管它会生成一条警告，但允许使用结构化的异常处理 (SEH) 的块。  下[/clr](../build/reference/clr-common-language-runtime-compilation.md)，跳出**最后**块将导致错误：

```cpp
// clr_exception_handling_4.cpp
// compile with: /clr
int main() {
   try {}
   finally {
      return 0;   // also fails with goto, break, continue
    }
}   // C3276
```

##  <a name="vcconraisingexceptionswithinanexceptionfilter"></a> 异常筛选器中引发异常

在处理过程中时引发异常[异常筛选器](../cpp/writing-an-exception-filter.md)在托管代码中，此异常将捕获并视为该筛选器将返回 0。

在本机代码中引发嵌套的异常的位置，这是与行为相比**ExceptionRecord**字段中**EXCEPTION_RECORD**结构 (如返回[GetExceptionInformation](/windows/desktop/Debug/getexceptioninformation)) 设置，并**ExceptionFlags**字段设置 0x10 位。 以下示例阐释了这种行为差异：

```cpp
// clr_exception_handling_5.cpp
#include <windows.h>
#include <stdio.h>
#include <assert.h>

#ifndef false
#define false 0
#endif

int *p;

int filter(PEXCEPTION_POINTERS ExceptionPointers) {
   PEXCEPTION_RECORD ExceptionRecord =
                     ExceptionPointers->ExceptionRecord;

   if ((ExceptionRecord->ExceptionFlags & 0x10) == 0) {
      // not a nested exception, throw one
      *p = 0; // throw another AV
   }
   else {
      printf("Caught a nested exception\n");
      return 1;
    }

   assert(false);

   return 0;
}

void f(void) {
   __try {
      *p = 0;   // throw an AV
   }
   __except(filter(GetExceptionInformation())) {
      printf_s("We should execute this handler if "
                 "compiled to native\n");
    }
}

int main() {
   __try {
      f();
   }
   __except(1) {
      printf_s("The handler in main caught the "
               "exception\n");
    }
}
```

### <a name="output"></a>输出

```Output
Caught a nested exception
We should execute this handler if compiled to native
```

##  <a name="vccondisassociatedrethrows"></a> 解除关联的重新引发

**/clr**不支持重新引发 catch 处理程序 （称为解除关联的重新引发） 之外的异常。 此类型的异常被视为一个标准的 C++ 重新引发。 如果在存在活动的托管异常时遇到解除关联的重新引发，则此异常将包装为 C++ 异常，然后重新引发。 仅可以作为类型的异常捕获到此类型的异常[system:: sehexception](https://msdn.microsoft.com/library/system.runtime.interopservices.sehexception.aspx)。

以下示例演示了作为 C++ 异常重新引发的托管异常：

```cpp
// clr_exception_handling_6.cpp
// compile with: /clr
using namespace System;
#include <assert.h>
#include <stdio.h>

void rethrow( void ) {
   // This rethrow is a dissasociated rethrow.
   // The exception would be masked as SEHException.
   throw;
}

int main() {
   try {
      try {
         throw gcnew ApplicationException;
      }
      catch ( ApplicationException^ ) {
         rethrow();
         // If the call to rethrow() is replaced with
         // a throw statement within the catch handler,
         // the rethrow would be a managed rethrow and
         // the exception type would remain
         // System::ApplicationException
      }
   }

    catch ( ApplicationException^ ) {
      assert( false );

      // This will not be executed since the exception
      // will be masked as SEHException.
    }
   catch ( Runtime::InteropServices::SEHException^ ) {
      printf_s("caught an SEH Exception\n" );
    }
}
```

### <a name="output"></a>输出

```Output
caught an SEH Exception
```

##  <a name="vcconexceptionfiltersandexception_continue_execution"></a> 异常筛选器和 EXCEPTION_CONTINUE_EXECUTION

如果筛选器在托管应用程序中返回 `EXCEPTION_CONTINUE_EXECUTION`，则将按照筛选器返回 `EXCEPTION_CONTINUE_SEARCH` 对其进行处理。 有关这些常量的详细信息，请参阅[试用-除非语句](../cpp/try-except-statement.md)。

以下示例演示了这一差异：

```cpp
// clr_exception_handling_7.cpp
#include <windows.h>
#include <stdio.h>
#include <assert.h>

int main() {
   int Counter = 0;
   __try {
      __try  {
         Counter -= 1;
         RaiseException (0xe0000000|'seh',
                         0, 0, 0);
         Counter -= 2;
      }
      __except (Counter) {
         // Counter is negative,
         // indicating "CONTINUE EXECUTE"
         Counter -= 1;
      }
    }
    __except(1) {
      Counter -= 100;
   }

   printf_s("Counter=%d\n", Counter);
}
```

### <a name="output"></a>输出

```Output
Counter=-3
```

##  <a name="vcconthe_set_se_translatorfunction"></a> _Set_se_translator 函数

通过调用 `_set_se_translator` 设置的转换器函数仅会影响非托管代码中的 catch 语句。 以下示例演示了这一限制：

```cpp
// clr_exception_handling_8.cpp
// compile with: /clr /EHa
#include <iostream>
#include <windows.h>
#include <eh.h>
#pragma warning (disable: 4101)
using namespace std;
using namespace System;

#define MYEXCEPTION_CODE 0xe0000101

class CMyException {
public:
   unsigned int m_ErrorCode;
   EXCEPTION_POINTERS * m_pExp;

   CMyException() : m_ErrorCode( 0 ), m_pExp( NULL ) {}

   CMyException( unsigned int i, EXCEPTION_POINTERS * pExp )
         : m_ErrorCode( i ), m_pExp( pExp ) {}

   CMyException( CMyException& c ) : m_ErrorCode( c.m_ErrorCode ),
                                      m_pExp( c.m_pExp ) {}

   friend ostream& operator <<
                 ( ostream& out, const CMyException& inst ) {
      return out <<  "CMyException[\n" <<
             "Error Code: " << inst.m_ErrorCode <<  "]";
    }
};

#pragma unmanaged
void my_trans_func( unsigned int u, PEXCEPTION_POINTERS pExp ) {
   cout <<  "In my_trans_func.\n";
   throw CMyException( u, pExp );
}

#pragma managed
void managed_func() {
   try  {
      RaiseException( MYEXCEPTION_CODE, 0, 0, 0 );
   }
   catch ( CMyException x ) {}
   catch ( ... ) {
      printf_s("This is invoked since "
               "_set_se_translator is not "
               "supported when /clr is used\n" );
    }
}

#pragma unmanaged
void unmanaged_func() {
   try  {
      RaiseException( MYEXCEPTION_CODE,
                      0, 0, 0 );
   }
   catch ( CMyException x ) {
      printf("Caught an SEH exception with "
             "exception code: %x\n", x.m_ErrorCode );
    }
    catch ( ... ) {}
}

// #pragma managed
int main( int argc, char ** argv ) {
   _set_se_translator( my_trans_func );

   // It does not matter whether the translator function
   // is registered in managed or unmanaged code
   managed_func();
   unmanaged_func();
}
```

### <a name="output"></a>输出

```Output
This is invoked since _set_se_translator is not supported when /clr is used
In my_trans_func.
Caught an SEH exception with exception code: e0000101
```

## <a name="see-also"></a>请参阅

[异常处理](../windows/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../windows/safe-cast-cpp-component-extensions.md)<br/>
[异常处理](../cpp/exception-handling-in-visual-cpp.md)
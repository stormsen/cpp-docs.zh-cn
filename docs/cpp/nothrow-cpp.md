---
title: nothrow （C++） |Microsoft 文档
ms.custom: ''
ms.date: 01/03/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- nothrow_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 65b8a0420bc996812eed5996757e05d50aafc030
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023522"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Microsoft 专用**

一个 **__declspec**扩展的特性，可以在函数的声明中使用。

## <a name="syntax"></a>语法

> *返回类型*__declspec （nothrow) [*调用约定*]*函数名称*([*自变量列表*])

## <a name="remarks"></a>备注

我们建议所有新代码改用[noexcept](noexcept-cpp.md)运算符而非`__declspec(nothrow)`。

此特性告知编译器，声明的函数及其调用的函数从不引发异常。  但是，它不会强制指令。 换而言之，但决不导致[std:: terminate](../standard-library/exception-functions.md#terminate)要调用与不同`noexcept`，或在**std:C++ 17模式 (Visual Studio 2017 15.5 及更高版本)， `throw()`。

利用当前默认的同步异常处理模式，编译器可以消除跟踪此类函数中的某些不可展开的对象的生命周期的机制，从而显著减小代码大小。 给定以下预处理器指令，下面的三个函数声明是等效的 **/std:C++ 14**模式：

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

在 **/std:C++ 17**模式下，`throw()`不等效于其他使用`__declspec(nothrow)`因为它会导致`std::terminate`要调用从函数引发的异常。

`void __stdcall f3() throw();`声明将使用由 C++ 标准定义的语法。 C++ 17 中`throw()`关键字已弃用。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[__declspec](../cpp/declspec.md)<br/>
[noexcept](noexcept-cpp.md)<br/>
[关键字](../cpp/keywords-cpp.md)
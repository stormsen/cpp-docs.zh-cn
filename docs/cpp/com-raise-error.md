---
title: _com_raise_error |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dea1ac5bb15c77d1c8e0a84d2c66e3c119f01fd6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031010"
---
# <a name="comraiseerror"></a>_com_raise_error

**Microsoft 专用**

将引发[_com_error](../cpp/com-error-class.md)中响应失败。

## <a name="syntax"></a>语法

```
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>参数

*hr*<br/>
HRESULT 的信息。

*perrinfo*<br/>
`IErrorInfo` 对象。

## <a name="remarks"></a>备注

**_com_raise_error**，其定义中\<comdef.h >，可由用户编写相同的名称和原型的版本替换。 若要使用 `#import` 但不使用 C++ 异常处理，则可以执行此操作。 在此情况下，用户版 **_com_raise_error**可能决定执行`longjmp`或显示一个消息框并暂停。 但不应返回用户版本，因为编译器 COM 支持代码不希望返回它。

此外可以使用[_set_com_error_handler](../cpp/set-com-error-handler.md)来替换默认错误处理函数。

默认情况下 **_com_raise_error**定义，如下所示：

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**结束 Microsoft 专用**

## <a name="requirements"></a>要求

**标头：** \<comdef.h >

**Lib:** 如果**wchar_t 是本机类型**编译器选项已打开，请使用 comsuppw.lib 或 comsuppwd.lib。 如果**wchar_t 是本机类型**未启用，请使用 comsupp.lib。 有关详细信息，请参阅 [/Zc:wchar_t（wchar_t 是本机类型）](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)。

## <a name="see-also"></a>请参阅

[编译器 COM 全局函数](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)
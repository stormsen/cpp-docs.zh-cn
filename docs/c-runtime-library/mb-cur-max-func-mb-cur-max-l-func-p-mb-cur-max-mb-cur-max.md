---
title: ___mb_cur_max_func、___mb_cur_max_l_func、__p___mb_cur_max、__mb_cur_max | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- ___mb_cur_max_l_func
- __p___mb_cur_max
- ___mb_cur_max_func
- __mb_cur_max
apilocation:
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
- __mb_cur_max
dev_langs:
- C++
helpviewer_keywords:
- __mb_cur_max
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
ms.assetid: 60d36108-1ca7-45a6-8ce7-68a91f13e3a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7eb9682a648f8e302a620e3c2e0dc1631abf7945
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068268"
---
# <a name="mbcurmaxfunc-mbcurmaxlfunc-pmbcurmax-mbcurmax"></a>___mb_cur_max_func、___mb_cur_max_l_func、__p___mb_cur_max、__mb_cur_max

内部 CRT 函数。 检索当前或指定区域设置的多字节字符中的最大字节数。

## <a name="syntax"></a>语法

```cpp
int ___mb_cur_max_func(void);
int ___mb_cur_max_l_func(_locale_t locale);
int * __p___mb_cur_max(void);
#define __mb_cur_max (___mb_cur_max_func())
```

#### <a name="parameters"></a>参数

locale 要从中检索结果的区域设置结构。 如果此值是 null，则使用当前线程区域设置。

## <a name="return-value"></a>返回值

当前线程区域设置或指定区域设置的多字节字符中的最大字节数。

## <a name="remarks"></a>备注

这是一个 CRT 用于从线程本地存储中检索 [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md) 宏的当前值的内部函数。 出于可移植性考虑，我们建议你在代码中使用 `MB_CUR_MAX` 宏。

`__mb_cur_max` 宏是一种用于调用 `___mb_cur_max_func()` 函数的便捷方式。 定义 `__p___mb_cur_max` 函数，以便与 Visual C++ 5.0 及其早期版本兼容。

内部 CRT 函数特定于实现且会根据每个发行版本发生更改。 不建议在代码中使用它们。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|`___mb_cur_max_func`, `___mb_cur_max_l_func`, `__p___mb_cur_max`|\<ctype.h>、\<stdlib.h>|

## <a name="see-also"></a>请参阅

[MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)
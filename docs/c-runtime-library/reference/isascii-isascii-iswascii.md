---
title: "isascii、__isascii、iswascii | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- iswascii
- __isascii
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- iswascii
- istascii
- __isascii
- _istascii
- isascii
- ctype/isascii
- ctype/__isascii
- corecrt_wctype/iswascii
dev_langs:
- C++
helpviewer_keywords:
- __isascii function
- _isascii function
- isascii function
- _istascii function
- istascii function
- iswascii function
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 401d8d05cc80ef1c72e7c72c06f94707b8c9848b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/01/2017

---
# <a name="isascii-isascii-iswascii"></a>isascii、__isascii、iswascii
确定特定字符是否是 ASCII 字符。  
  
## <a name="syntax"></a>语法  
  
```  
int __isascii(   
   int c   
);  
int iswascii(   
   wint_t c   
);  
#define isascii __isascii  
```  
  
#### <a name="parameters"></a>参数  
 `c`  
 要测试的整数。  
  
## <a name="return-value"></a>返回值  
 如果 `c` 是 ASCII 字符的特定表示形式，则每个实例将返回非零值。 `__isascii`返回一个非零值，如果`c`是 ASCII 字符 （位于范围 0x00-0x7F）。 如果 `iswascii` 是 ASCII 字符的宽字符表示形式，则 `c` 将返回一个非零值。 如果 `c` 不满足测试条件，则这些例程都返回 0。  
  
## <a name="remarks"></a>备注  
 除非定义了预处理器宏 _CTYPE_DISABLE_MACROS，否则会将 `__isascii` 和 `iswascii` 同时作为宏实现。  
  
 对于反向兼容，仅在未定义 [__STDC\_\_](../../preprocessor/predefined-macros.md) 或将其定义为 0 时将 `isascii` 作为宏实现；否则不进行定义。  
  
### <a name="generic-text-routine-mappings"></a>一般文本例程映射  
  
|Tchar.h 例程|未定义 _UNICODE 和 _MBCS|已定义 _MBCS|已定义 _UNICODE|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_istascii`|`__isascii`|`__isascii`|`iswascii`|  
  
## <a name="requirements"></a>要求  
  
|例程|必需的标头|  
|-------------|---------------------|  
|`isascii`, `__isascii`|C：\<ctype.h><br /><br /> C++：\<cctype> 或 \<ctype.h>|  
|`iswascii`|C：\<wctype.h 1>、\<ctype.h 1>，或 \<wchar.h 1><br /><br /> C++：\<cwctype 1>、\<cctype 1>、\<wctype.h 1>、\<ctype.h 1>，或 \<wchar.h 1>|  
  
 `isascii`、`__isascii` 和 `iswascii` 函数是 Microsoft 的特定函数。 有关其他兼容性信息，请参见“简介”中的[兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="see-also"></a>另请参阅  
 [字符分类](../../c-runtime-library/character-classification.md)   
 [区域设置](../../c-runtime-library/locale.md)   
 [is、isw 例程](../../c-runtime-library/is-isw-routines.md)
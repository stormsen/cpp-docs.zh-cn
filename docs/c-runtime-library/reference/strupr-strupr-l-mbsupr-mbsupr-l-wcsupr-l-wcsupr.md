---
title: _strupr、_strupr_l、_mbsupr、_mbsupr_l、_wcsupr_l、_wcsupr | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsupr_l
- _mbsupr
- _strupr_l
- _wcsupr
- _wcsupr_l
- _strupr
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbsupr
- _ftcsupr
- mbsupr
- _tcsupr
- strupr_l
- _fstrupr
- _strupr
- mbsupr_l
- _wcsupr
dev_langs:
- C++
helpviewer_keywords:
- tcsupr_l function
- mbsupr function
- strupr function
- uppercase, converting strings to
- wcsupr function
- _wcsupr function
- string conversion [C++], case
- ftcsupr function
- _ftcsupr function
- _wcsupr_l function
- wcsupr_l function
- strings [C++], case
- tcsupr function
- _tcsupr_l function
- _fstrupr function
- _strupr_l function
- _mbsupr_l function
- converting case, CRT functions
- fstrupr function
- mbsupr_l function
- strupr_l function
- _strupr function
- _mbsupr function
- _tcsupr function
- strings [C++], converting case
ms.assetid: caac8f16-c233-41b6-91ce-575ec7061b77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d34f0bd4e24fa70f37bb2191293cbc2a3e7ad9c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415379"
---
# <a name="strupr-struprl-mbsupr-mbsuprl-wcsuprl-wcsupr"></a>_strupr、_strupr_l、_mbsupr、_mbsupr_l、_wcsupr_l、_wcsupr

将字符串转换成大写形式。 提供这些函数的更多安全版本，请参阅 [_strupr_s、_strupr_s_l、_mbsupr_s、_mbsupr_s_l、_wcsupr_s、_wcsupr_s_l](strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)。

> [!IMPORTANT]
> **_mbsupr**和 **_mbsupr_l**不能用于在 Windows 运行时中执行的应用程序。 有关详细信息，请参阅[通用 Windows 平台应用中不支持的 CRT 函数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)。

## <a name="syntax"></a>语法

```C
char *_strupr(
   char *str
);
wchar_t *_wcsupr(
   wchar_t *str
);
unsigned char *_mbsupr(
   unsigned char *str
);
char *_strupr_l(
   char *str,
   _locale_t locale
);
wchar_t *_wcsupr_l(
   wchar_t *str,
   _locale_t locale
);
unsigned char *_mbsupr_l(
   unsigned char *str,
   _locale_t locale
);
template <size_t size>
char *_strupr(
   char (&str)[size]
); // C++ only
template <size_t size>
wchar_t *_wcsupr(
   wchar_t (&str)[size]
); // C++ only
template <size_t size>
unsigned char *_mbsupr(
   unsigned char (&str)[size]
); // C++ only
template <size_t size>
char *_strupr_l(
   char (&str)[size],
   _locale_t locale
); // C++ only
template <size_t size>
wchar_t *_wcsupr_l(
   wchar_t (&str)[size],
   _locale_t locale
); // C++ only
template <size_t size>
unsigned char *_mbsupr_l(
   unsigned char (&str)[size],
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>参数

*str*<br/>
大写字符串。

*locale*<br/>
要使用的区域设置。

## <a name="return-value"></a>返回值

返回指向修改后的字符串的指针。 由于修改是就地完成的，因此所返回的指针与作为输入参数传递的指针相同。 没有保留任何返回值以指示错误。

## <a name="remarks"></a>备注

**_Strupr**函数将转换时，就地情况下，每个小写字母*str*为大写形式。 转换由**LC_CTYPE**类别设置的区域设置。 其他字符不受影响。 有关详细信息**LC_CTYPE**，请参阅[setlocale](setlocale-wsetlocale.md)。 版本的这些功能，而不必 **_l**后缀使用当前区域设置; 的版本与 **_l**后缀是相同，只不过它们使用传递的区域设置。 有关详细信息，请参阅 [Locale](../../c-runtime-library/locale.md)。

**_wcsupr**和 **_mbsupr**宽字符及多字节字符版本的 **_strupr**。 自变量和返回值 **_wcsupr**是宽字符字符串; 而的 **_mbsupr**是多字节字符字符串。 否则这三个函数否则具有相同行为。

如果*str*是 null 指针，则调用无效参数处理程序，如中所述[参数验证](../../c-runtime-library/parameter-validation.md)。 如果允许执行继续，则这些函数返回的原始字符串和集**errno**到**EINVAL**。

在 C++ 中，这些函数具有模板重载，以调用这些函数的更新、更安全副本。 有关详细信息，请参阅 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)。

### <a name="generic-text-routine-mappings"></a>一般文本例程映射

|TCHAR.H 例程|未定义 _UNICODE 和 _MBCS|已定义 _MBCS|已定义 _UNICODE|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsupr**|**_strupr**|**_mbsupr**|**_wcsupr**|
|**_tcsupr_l**|**_strupr_l**|**_mbsupr_l**|**_wcsupr_l**|

## <a name="requirements"></a>要求

|例程|必需的标头|
|-------------|---------------------|
|**_strupr**， **_strupr_l**|\<string.h>|
|**_wcsupr**， **_wcsupr_l**|\<string.h> 或 \<wchar.h>|
|**_mbsupr**， **_mbsupr_l**|\<mbstring.h>|

有关其他兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

请参阅 [_strlwr](strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md) 的示例。

## <a name="see-also"></a>请参阅

[区域设置](../../c-runtime-library/locale.md)<br/>
[字符串操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strlwr、_wcslwr、_mbslwr、_strlwr_l、_wcslwr_l、_mbslwr_l](strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md)<br/>

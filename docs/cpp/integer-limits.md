---
title: 整数限制 |Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integral limits
- limits, integer
- limits.h header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f49e224520751e08ba6aa7e37932314e11ef8a5
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315180"
---
# <a name="integer-limits"></a>整数限制

**Microsoft 专用**

下表列出了整数类型的限制。 标准标头文件中也定义了这些限制\<limits.h >。

## <a name="limits-on-integer-constants"></a>对整数常量的限制

|返回的常量|含义|“值”|
|--------------|-------------|-----------|
|CHAR_BIT|不是位域的最小变量中的位数。|8|
|SCHAR_MIN|**signed char** 类型的变量的最小值。|-128|
|SCHAR_MAX|**signed char** 类型的变量的最大值。|127|
|UCHAR_MAX|unsigned char 类型的变量的最大值。|255 (0xff)|
|CHAR_MIN|char 类型的变量的最小值。|-128；如果使用了 /J 选项，则为 0|
|CHAR_MAX|char 类型的变量的最大值。|127；如果使用了 /J 选项，则为 255|
|MB_LEN_MAX|多字符常量中的最大字节数。|5|
|SHRT_MIN|**short** 类型的变量的最小值。|-32768|
|SHRT_MAX|**short** 类型的变量的最大值。|32767|
|USHRT_MAX|**unsigned short** 类型的变量的最大值。|65535 (0xffff)|
|INT_MIN|int 类型的变量的最小值。|-2147483648|
|INT_MAX|int 类型的变量的最大值。|2147483647|
|UINT_MAX|unsigned int 类型的变量的最大值。|4294967295 (0xffffffff)|
|LONG_MIN|**long** 类型的变量的最小值。|-2147483648|
|LONG_MAX|**long** 类型的变量的最大值。|2147483647|
|ULONG_MAX|unsigned long 类型的变量的最大值。|4294967295 (0xffffffff)|
|LLONG_MIN|最小值的变量的类型**长时间长**|-9223372036854775808|
|与 LLONG_MAX|最大值类型的变量的**长时间长**|9223372036854775807|
|ULLONG_MAX|最大值类型的变量的**无符号长时间长**|18446744073709551615 (0xffffffffffffffff)|

如果值超出了最大整数表示形式，则 Microsoft 编译器会产生错误。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[浮点限制](../cpp/floating-limits.md)
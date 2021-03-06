---
title: __movsd |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __movsd
dev_langs:
- C++
helpviewer_keywords:
- rep movsd instruction
- __movsd intrinsic
- movsd instruction
ms.assetid: eb5cccf3-aa76-47f0-b9fc-eeca38fd943f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b70e8709f028f5aa9cb313365ed078f2af2c1a48
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377547"
---
# <a name="movsd"></a>__movsd

**Microsoft 专用**

生成移动字符串 (`rep movsd`) 指令。

## <a name="syntax"></a>语法

```
void __movsd( 
   unsigned long* Dest, 
   unsigned long* Source, 
   size_t Count 
);
```

#### <a name="parameters"></a>参数

*dest*<br/>
[out]该操作的目标。

*Source*<br/>
[in]操作的源。

“计数”<br/>
[in]双字数组要复制的数。

## <a name="requirements"></a>要求

|内部函数|体系结构|
|---------------|------------------|
|`__movsd`|x86、x64|

**标头文件** \<intrin.h >

## <a name="remarks"></a>备注

结果是，第一个`Count`指向双字`Source`复制到`Dest`字符串。

此例程仅可用作内部函数。

## <a name="example"></a>示例

```
// movsd.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsd)

int main()
{
    unsigned long a1[10];
    unsigned long a2[10] = {950, 850, 750, 650, 550, 450, 350,
                            250, 150, 50};
    __movsd(a1, a2, 10);

    for (int i = 0; i < 10; i++)
        printf_s("%d ", a1[i]);
    printf_s("\n");
}
```

```Output
950 850 750 650 550 450 350 250 150 50
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
---
title: __writegsbyte，__writegsdword，__writegsqword，__writegsword |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __writegsbyte
- __writegsqword
- __writegsdword
- __writegsword
dev_langs:
- C++
helpviewer_keywords:
- __writegsqword intrinsic
- __writegsbyte intrinsic
- __writegsword intrinsic
- __writegsdword intrinsic
ms.assetid: 7746cf6d-2259-4139-9aab-c07dd75c8037
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8dded14f47c4c0305e4dc145ee2b006c76da9b8f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393550"
---
# <a name="writegsbyte-writegsdword-writegsqword-writegsword"></a>__writegsbyte, __writegsdword, __writegsqword, __writegsword

**Microsoft 专用**

内存写入指定相对于 GS 段开头的偏移量的位置。

## <a name="syntax"></a>语法

```
void __writegsbyte( 
   unsigned long Offset, 
   unsigned char Data 
);
void __writegsword( 
   unsigned long Offset, 
   unsigned short Data 
);
void __writegsdword( 
   unsigned long Offset, 
   unsigned long Data 
);
void __writegsqword( 
   unsigned long Offset, 
   unsigned __int64 Data 
);
```

#### <a name="parameters"></a>参数

*偏移量*<br/>
[in]从要写入到的 GS 开头的偏移量。

*Data*<br/>
[in]要写入的值。

## <a name="requirements"></a>要求

|内部函数|体系结构|
|---------------|------------------|
|`__writegsbyte`|X64|
|`__writegsdword`|X64|
|`__writegsqword`|X64|
|`__writegsword`|X64|

**标头文件** \<intrin.h >

## <a name="remarks"></a>备注

这些内部函数可用于在内核模式下，并且这些例程仅用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[__readgsbyte， \__readgsdword， \__readgsqword， \__readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)<br/>
[编译器内部函数](../intrinsics/compiler-intrinsics.md)
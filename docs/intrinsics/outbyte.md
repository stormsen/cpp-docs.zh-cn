---
title: __outbyte |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __outbyte
dev_langs:
- C++
helpviewer_keywords:
- out instruction
- __outbyte intrinsic
ms.assetid: c4cd1a34-8a02-4e37-993d-3201bc17901a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 684461d1d758db2a0c5850219c00d158342b8a3d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398154"
---
# <a name="outbyte"></a>__outbyte

**Microsoft 专用**

将生成`out`指令，将发送由指定 1 个字节`Data`出指定的 I/O 端口`Port`。

## <a name="syntax"></a>语法

```
void __outbyte( 
   unsigned short Port, 
   unsigned char Data 
);
```

#### <a name="parameters"></a>参数

*端口*<br/>
[in]要向其发送数据的端口。

*Data*<br/>
[in]要指定的端口发送的字节。

## <a name="requirements"></a>要求

|内部函数|体系结构|
|---------------|------------------|
|`__outbyte`|x86、x64|

**标头文件** \<intrin.h >

## <a name="remarks"></a>备注

此例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
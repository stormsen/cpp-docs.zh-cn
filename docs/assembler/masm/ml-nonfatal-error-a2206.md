---
title: ML 非致命错误 A2206 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2206
dev_langs:
- C++
helpviewer_keywords:
- A2206
ms.assetid: 711846d0-5a09-4353-8857-60588c25526a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10edbe68ca7f0093cdeb6a9ca5a02cde07f556e6
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676343"
---
# <a name="ml-nonfatal-error-a2206"></a>ML 非致命错误 A2206

**在表达式中缺少运算符**

无法计算表达式，因为它缺少运算符。 此错误消息也可能是前面的程序错误的副作用。

以下行将生成此错误：

```asm
value1 = ( 1 + 2 ) 3
```

## <a name="see-also"></a>请参阅

[ML 错误消息](../../assembler/masm/ml-error-messages.md)<br/>
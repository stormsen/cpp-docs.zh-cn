---
title: 编译器警告 （等级 2 和 3） 等级 C4008 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4008
dev_langs:
- C++
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd052b8dd6a0b70dd90ca076d0085675b33dc621
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091174"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>编译器警告（等级 2 和等级 3）C4008

“identifier”：“attribute”属性被忽略

编译器忽略了函数（级别 3 警告）或数据（等级 2 警告）的 `__fastcall`、 **static**或 **inline** 属性。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 带数据的`__fastcall` 属性。

1. 带**inline** 函数的 **static** 或 **inline** 属性。
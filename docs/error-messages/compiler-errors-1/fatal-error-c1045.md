---
title: 错误 C1045 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1045
dev_langs:
- C++
helpviewer_keywords:
- C1045
ms.assetid: 766c2f89-4ecd-4281-adaa-14b270cc0829
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c18d6f9b502e818992097c3042689cf66457792
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024770"
---
# <a name="fatal-error-c1045"></a>错误 C1045

编译器限制 : 链接规范嵌套太深

嵌套的外部对象超过编译器限制。 允许嵌套的外部项使用外部链接类型，如 `extern` “C++”。 减少嵌套的外部项的数量以解决该错误。
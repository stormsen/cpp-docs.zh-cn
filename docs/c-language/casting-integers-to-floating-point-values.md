---
title: 将整数强制转换为浮点值 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a81b72a7dfedbc1d6033d53bde63be22943abb08
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055216"
---
# <a name="casting-integers-to-floating-point-values"></a>将整数转换为浮点值

**ANSI 3.2.1.3** 当一个整数转换为无法确切表示原始值的浮点数时的截断方向

当一个整数转换为无法确切表示值的浮点值时，值将被舍入（向上或向下）到最接近的适当值。

例如，将 unsigned long（具有 32 位精度）转换为 float（尾数具有 23 位精度）会将该数字舍入到 256 的最接近倍数。 介于 4,294,966,913 和 4,294,967,167 之间的所有 long 值都将舍入到 float 值 4,294,967,040。

## <a name="see-also"></a>请参阅

[浮点数学](../c-language/floating-point-math.md)
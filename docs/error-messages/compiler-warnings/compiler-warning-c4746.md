---
title: 编译器警告 C4746 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e6abce7ebbcdc41effed05ccf54337e3976c34e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054855"
---
# <a name="compiler-warning-c4746"></a>编译器警告 C4746

可变访问\<表达式 > 受 /volatile: [iso&#124;ms] 设置; 请考虑使用 __iso_volatile_load/store 内部函数。

直接访问可变变量时会发出 C4746。 它旨在帮助开发人员识别受当前指定的特定可变模型的代码位置 (这可以使用控制[/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md)编译器选项)。 具体而言，如果要在使用 /volatile:ms 时查找编译器生成的硬件内存屏障，它很有用。

__iso_volatile_load/store 内部函数可用于显式访问可变内存而不会受可变模型的影响。 使用这些内部函数不会触发 C4746。

默认情况下，此警告处于关闭状态。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。
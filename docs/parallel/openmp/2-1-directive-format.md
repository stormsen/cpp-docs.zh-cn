---
title: 2.1 指令格式 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 918b6445-d35e-4176-9565-b045be941b4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b2f2d2f5742dbc4faa1d8386e935c9d4ccc8049
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424646"
---
# <a name="21-directive-format"></a>2.1 指令格式

该语法进行了正式指定 OpenMP 指令的语法[附录 C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)，和非正式的方式，如下所示：

```
#pragma omp directive-name  [clause[ [,] clause]...] new-line
```

每个指令开头 **#pragma omp**，以减少与具有相同名称的其他 （非 OpenMP 或供应商扩展与 OpenMP） 杂注指令发生冲突的可能性。 指令的其余部分遵循编译器指令的 C 和 c + + 标准的约定。 之前和之后具体而言，可以使用空格**#**，并有时必须使用空格分隔指令中的单词。 预处理标记后面 **#pragma omp**宏替换。

指令是区分大小写。 子句在指令中的显示顺序并不重要。 根据需要每个子句的说明中列出的限制的制约，可能会重复指令上的子句。 如果*变量列表*将出现在子句中，它必须指定只有变量。 只有一个*指令名称*可以指定每个指令。  例如，不允许以下指令：

```
/* ERROR - multiple directive names not allowed */
#pragma omp parallel barrier
```

OpenMP 指令适用于最多一个后续语句，该语句必须是结构化的块中。
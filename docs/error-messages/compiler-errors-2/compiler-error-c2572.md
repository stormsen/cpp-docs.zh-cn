---
title: 编译器错误 C2572 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2572
dev_langs:
- C++
helpviewer_keywords:
- C2572
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56d49fe95dca7861b18d417dcd6049a12776e8d2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057829"
---
# <a name="compiler-error-c2572"></a>编译器错误 C2572

class::member： 重定义默认参数： 参数 param

不能重新定义默认参数。 如果您需要另一个参数的值，默认参数应保持为未定义状态。

下面的示例生成 C2572:

```
// C2572.cpp
// compile with: /c
void f(int i = 1);   // function declaration

// function definition
void f(int i = 1) {}   // C2572

// try the following line instead
// void f(int i) {}
```
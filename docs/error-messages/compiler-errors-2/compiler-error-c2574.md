---
title: 编译器错误 C2574 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2574
dev_langs:
- C++
helpviewer_keywords:
- C2574
ms.assetid: 3e1c5c18-ee8b-4dbb-bfc0-d3b8991af71b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51874eed00c66832cbae11490147eca50c2d5071
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058388"
---
# <a name="compiler-error-c2574"></a>编译器错误 C2574

析构函数： 不能声明为静态

可以声明析构函数和构造函数都不`static`。

下面的示例生成 C2574:

```
// C2574.cpp
// compile with: /c
class A {
   virtual static ~A();   // C2574
   //  try the following line instead
   // virtual ~A();
};
```
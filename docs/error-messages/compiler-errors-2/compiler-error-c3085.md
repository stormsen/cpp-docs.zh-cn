---
title: 编译器错误 C3085 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3085
dev_langs:
- C++
helpviewer_keywords:
- C3085
ms.assetid: 1ac40bf2-f63e-439e-8921-47e6dadc8354
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbe3cd1b5c3aab71b38bca694df28fdf5b079474
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033298"
---
# <a name="compiler-error-c3085"></a>编译器错误 C3085

“constructor”：构造函数不能是“keyword”

未正确声明构造函数。 有关更多信息，请参见 [Override Specifiers](../../windows/override-specifiers-cpp-component-extensions.md) 。

## <a name="example"></a>示例

以下示例生成 C3085。

```
// C3085.cpp
// compile with: /c /clr
ref struct S {
   S() abstract;   // C3085
   S(S%) abstract;   // C3085
};

ref struct T {
   T() sealed {}   // C3085
   T(T%) sealed {}   // C3085
};
```
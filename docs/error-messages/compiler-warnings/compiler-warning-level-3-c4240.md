---
title: 编译器警告 （等级 3） C4240 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4240
dev_langs:
- C++
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2f3c059e63bcca9bbde9e863cc17c9e240e4f78
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057010"
---
# <a name="compiler-warning-level-3-c4240"></a>编译器警告（等级 3）C4240

使用了非标准扩展： 访问 classname 现定义为访问说明符，而以前它被定义为访问说明符

在 ANSI 兼容性 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))，不能用于嵌套类更改的访问权限。 在默认的 Microsoft 扩展 (/Ze) 中，您可以，并发出以下警告。

## <a name="example"></a>示例

```
// C4240.cpp
// compile with: /W3
class X
{
private:
   class N;
public:
   class N
   {   // C4240
   };
};

int main()
{
}
```
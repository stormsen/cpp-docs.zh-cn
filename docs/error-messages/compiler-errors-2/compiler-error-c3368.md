---
title: 编译器错误 C3368 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3368
dev_langs:
- C++
helpviewer_keywords:
- C3368
ms.assetid: 5bfd5be4-dfa9-4b33-9612-010561b40955
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 236bfdfc031544e05d4aa95d9c36720ddb0ebdf8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051290"
---
# <a name="compiler-error-c3368"></a>编译器错误 C3368

“function declaration”：IDL 的调用约定无效

你只能在 .idl 文件中使用 [__stdcall](../../cpp/stdcall.md) 或 [__cdecl](../../cpp/cdecl.md) 调用约定。

以下示例生成 C3368：

```
// C3368.cpp
// processor: x86
[idl_module(name="Name", dllname="Some.dll")];

[idl_module(name="Name")]
int __fastcall f1();   // C3368
```
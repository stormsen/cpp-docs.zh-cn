---
title: 资源编译器错误 RC2101 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2101
dev_langs:
- C++
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 196806e6d2767c889ae96d239af69113c542ba6c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034754"
---
# <a name="resource-compiler-error-rc2101"></a>资源编译器错误 RC2101

预处理过的 RC 文件中的指令无效

资源编译器文件包含 **#pragma**指令。

使用 **#ifndef** RC_INVOKED 常量资源编译器定义处理的包含文件时使用的预处理器指令。 位置 **#pragma**指令定义 RC_INVOKED 常量时不处理的代码块。 仅由 C/c + + 编译器，而不是由资源编译器处理代码块中。 下面的示例代码演示了此种方法：

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

**#Pragma**预处理器指令没有任何意义。RC 文件。 **#Include**中经常使用预处理器指令。RC 文件以包括标头文件 （基于项目的自定义标头文件或使用其产品的一个由 Microsoft 提供的标准标头文件）。 其中包括文件包含 **#pragma**指令。 由于标头文件可以包括一个或多个其他标头文件，包含有问题的文件 **#pragma**指令可能不会即时显现。

**#Ifndef** RC_INVOKED 技术包括基于项目的标头文件中的标头文件可以控制。
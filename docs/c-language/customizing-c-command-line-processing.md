---
title: 自定义 C 命令行处理 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _spawn functions
- command line, processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line, processing arguments
- suppressing environment processing
- _exec function
ms.assetid: c20fa11d-b35b-4f3e-93b6-2cd5a1c3c993
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 541cfed194262aa5bff6810b19d5d2c89468ffa4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090810"
---
# <a name="customizing-c-command-line-processing"></a>自定义 C 命令行处理

如果程序不采用命令行自变量，则可以通过取消使用执行命令行处理的库例程来节省少量空间。 此例程称为 _setargv（在宽字符环境中，称为 _wsetargv），如[展开通配符参数](../c-language/expanding-wildcard-arguments.md)中所述。 若要禁止使用它，请在包含 main 函数的文件中定义一个不执行任何操作的例程，并将其命名为 _setargv（在宽字符环境中为 _wsetargv）。 随后，对 _setargv 或 _wsetargv 的调用由 _setargv 或 _wsetargv 的定义实现，并且不会加载库版本。

同样，如果从不通过 `envp` 自变量访问环境表，则可以提供用来代替 _setenvp（或 _wsetenvp）的你自己的空例程（环境处理例程）。

如果程序在 C 运行库中调用 _spawn 或 _exec 系列例程，则不应停止环境处理例程，因为需使用此例程将环境从生成进程传递到新进程。

## <a name="see-also"></a>请参阅

[main 函数和程序执行](../c-language/main-function-and-program-execution.md)
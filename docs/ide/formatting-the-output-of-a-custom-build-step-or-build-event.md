---
title: 设置自定义生成步骤或生成事件输出的格式 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- builds [C++], build events
- custom build steps [C++], output format
- events [C++], build
- build events [C++], output format
- build steps [C++], output format
- builds [C++], custom build steps
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a975951142c028ffcfb8ece870ab3ac2d2b60fc
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203244"
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>设置自定义生成步骤或生成事件输出的格式

如果自定义生成步骤或生成事件的输出格式正确，则用户将获得以下好处：

- 警告和错误将在“输出”窗口中计数。

- 在“任务列表”窗口中显示输出。

- 单击“输出”窗口中的输出，显示相应主题。

- 可在“任务列表”窗口或“输出”窗口中启用 F1 操作。

输出格式应为：

> {<em>filename</em>**(**<em>line#</em> \[**,** <em>column#</em>]**)** &#124; *toolname*} **:** \[ <em>any text</em> ] {**error** &#124; **warning**} <em>code+number</em>**:**<em>localizable string</em> \[ <em>any text</em> ]

其中：

- {a &#124; b} 表示在 a 或 b 中任选一个。

- \[<em>item</em>] 为可选的字符串或参数。

- 粗体代表文本。

例如:

> C:\\sourcefile.cpp(134) : 错误 C2143: 语法错误 : "}" 前缺少 ";"

> LINK : 灾难性错误 LNK1104: 无法打开文件 "somelib.lib"

## <a name="see-also"></a>请参阅

[了解自定义生成步骤和生成事件](../ide/understanding-custom-build-steps-and-build-events.md)
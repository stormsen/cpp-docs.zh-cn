---
title: 创建声明/定义 | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 6b1cdcb2-765e-4b93-8cef-92b861f64eba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 383691a5c2da2af6e4a992ab8766cd99ffa3d781
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408383"
---
# <a name="create-declaration--definition"></a>创建声明/定义
功能：允许立即生成函数的声明或定义。

时间：有需要声明的函数，反之亦然。

原因：可手动创建声明/定义，但这将自动创建声明/定义，并在需要时创建头文件/代码文件。

方法：

1. 将文本或鼠标光标置于要为其创建声明或定义的函数上。

   ![突出显示的代码](images/createdefinition_highlight.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从关联菜单选择“创建声明/定义”。
   * **鼠标**
     * 右键单击并选择“快速操作和重构”菜单，然后从关联菜单选择“创建声明/定义”。

1. 随即在源文件或头文件中创建函数的声明/定义，并在弹出的预览窗口中显示。  如果源文件或头文件不存在，也将创建它并将其放置在项目中。

   ![“创建声明/定义”结果](images/createdefinition_result.png)

---
title: 在 CStatusBarCtrl 对象中使用工具提示 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f17dff6680209664e9d029404e4ef012b9f12046
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392354"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>在 CStatusBarCtrl 对象中使用工具提示

若要启用状态栏控件的工具提示，请创建`CStatusBarCtrl`SBT_TOOLTIPS 样式的对象。

> [!NOTE]
>  如果要使用 `CStatusBar` 对象实现状态栏，请使用 `CStatusBar::CreateEx` 函数。 它允许您指定的嵌入其他样式`CStatusBarCtrl`对象。

一次`CStatusBarCtrl`已成功创建对象，请使用[cstatusbarctrl:: Settiptext](../mfc/reference/cstatusbarctrl-class.md#settiptext)并[cstatusbarctrl:: Gettiptext](../mfc/reference/cstatusbarctrl-class.md#gettiptext)来设置和检索特定窗格的提示文本。

设置工具提示后，仅当部件具有图标且没有文本，或所有文本无法在部件内显示时才显示工具提示。 简单模式中不支持工具提示。

## <a name="see-also"></a>请参阅

[使用 CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[控件](../mfc/controls-mfc.md)


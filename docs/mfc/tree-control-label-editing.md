---
title: 树控件标签编辑 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99b3490e98ba9cf9640c4903d88064a7808c6494
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376572"
---
# <a name="tree-control-label-editing"></a>树控件标签编辑

用户可以直接编辑树控件中的项的标签 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md))，其**TVS_EDITLABELS**样式。 用户通过单击具有焦点的项的标签开始编辑。 应用程序开始编辑通过使用[EditLabel](../mfc/reference/ctreectrl-class.md#editlabel)成员函数。 树控件在编辑开始以及编辑取消或完成时发送通知。 当编辑完成时，您负责根据需要更新项的标签。

当标签编辑开始时，树控件将发送[TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit)通知消息。 通过处理此通知，您可以允许某些标签的编辑并阻止其他标签的编辑。 返回 0 将允许编辑，返回非零将阻止编辑。

当标签编辑取消或完成时，树控件将发送[TVN_ENDLABELEDIT](/windows/desktop/Controls/tvn-endlabeledit)通知消息。 *LParam*参数是地址[2&AMP;GT;NMTVDISPINFO&AMP;LT;2](/windows/desktop/api/commctrl/ns-commctrl-tagtvdispinfoa)结构。 **项**成员是[TVITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtvitema)结构，它标识项和包括的已编辑的文本。 您负责根据需要更新项的标签（可能在验证编辑过的字符串之后）。 *PszText*的成员`TV_ITEM`为 0，如果取消了编辑。

在标签编辑期间，通常以响应[TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit)通知消息，可以获得一个指向用于标签编辑通过使用在编辑控件[GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol)成员函数。 您可以调用编辑控件的[SetLimitText](../mfc/reference/cedit-class.md#setlimittext)成员函数，以限制用户可以输入的文本或子类以截获和丢弃无效字符的编辑控件的量。 但请注意，仅显示编辑控件*后* **TVN_BEGINLABELEDIT**发送。

## <a name="see-also"></a>请参阅

[使用 CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[控件](../mfc/controls-mfc.md)


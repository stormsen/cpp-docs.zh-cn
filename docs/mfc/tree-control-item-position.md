---
title: 树控件项位置 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], item position
- item position in tree controls
- tree controls [MFC], item position
- position, CTreeCtrl items
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e24c21a8a44f09e9141b1763646d1a887bda158
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412088"
---
# <a name="tree-control-item-position"></a>树控件项位置

当项添加到树控件设置了项的初始位置 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 使用`InsertItem`成员函数。 成员函数调用指定的父项句柄并在其后插入新项的项的句柄。 第二个句柄必须标识给定父级的子项目或这些值之一： `TVI_FIRST`， `TVI_LAST`，或`TVI_SORT`。

当`TVI_FIRST`或`TVI_LAST`指定，则树控件将新项放置在开头或末尾的子项目的给定的父项的列表。 当`TVI_SORT`树控件将新项插入到按字母顺序对项标签的文本中的子项目列表的指定。

您可以通过调用放置于按字母顺序的子项目的父项的列表[SortChildren](../mfc/reference/ctreectrl-class.md#sortchildren)成员函数。 此函数包含一个参数，指定是否也按字母顺序排序的降序从给定的父项的子项目的所有级别。

[SortChildrenCB](../mfc/reference/ctreectrl-class.md#sortchildrencb)成员函数允许您根据您定义的条件的子项进行排序。 当调用此函数时，您指定的树控件，可以调用时需要确定两个子项的相对顺序的应用程序定义的回调函数。 回调函数接收两个 32 位应用程序定义的值进行比较的项和调用时指定一个第三个 32 位值`SortChildrenCB`。

## <a name="see-also"></a>请参阅

[使用 CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[控件](../mfc/controls-mfc.md)


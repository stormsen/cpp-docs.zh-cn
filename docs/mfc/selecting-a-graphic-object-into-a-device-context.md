---
title: 将图形对象选入设备上下文 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 406c4e7cd87b350f9317022dcf1821fa92ddf4af
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427662"
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>将图形对象选入设备上下文

本主题适用于在窗口的设备上下文中使用图形对象。 检查完[创建的图形对象](../mfc/one-stage-and-two-stage-construction-of-objects.md)，必须将它选入设备上下文来替代默认对象存储在此处：

[!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]

## <a name="lifetime-of-graphic-objects"></a>图形对象的生存期

返回的图形对象[SelectObject](../mfc/reference/cdc-class.md#selectobject)是"临时"。 也就是说，它将被删除[OnIdle](../mfc/reference/cwinapp-class.md#onidle)类的成员函数`CWinApp`的下次程序获取空闲时间。 只要您使用返回的对象`SelectObject`在单个函数而无需将控制权返还给主消息循环中，将有任何问题。

### <a name="what-do-you-want-to-know-more-about"></a>你想要了解更多信息

- [图形对象](../mfc/graphic-objects.md)

- [图形对象的一阶段和两阶段构建](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [设备上下文](../mfc/device-contexts.md)

- [在视图中绘制](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>请参阅

[图形对象](../mfc/graphic-objects.md)


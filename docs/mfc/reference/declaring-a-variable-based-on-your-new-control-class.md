---
title: 声明一个变量基于新控件类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.classes.control.variable
dev_langs:
- C++
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3cdf60f614b95c22b4b3c40b5528a7daf885bed
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388729"
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>声明基于新控件类的变量

创建 MFC 控件类后，可以声明其为基础的变量。 若要为新的变量提供上下文，必须打开对话框编辑器并编辑想要使用可重用控件的对话框。 此外，对话框中必须已有与之关联的类。 有关使用对话框编辑器的信息，请参阅[对话框编辑器](../../windows/dialog-editor.md)。

### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>若要声明变量基于可重用类

1. 在编辑对话框中，将从拖到对话框控件工具栏中拖动新控件的基类的类型相同的控件。

1. 将鼠标指针放在拖动的控件。

1. 在按住 CTRL 键，双击该控件。

     [添加成员变量](../../ide/add-member-variable-wizard.md)对话框随即出现。

1. 在中**访问**框中，选择正确的访问权限为您的控件。

1. 单击**控制变量**复选框。

1. 在中**变量名**框中，键入一个名称。

1. 下**类别**，单击**控制**。

1. 在中**控件 ID**列表中，选取你添加的控件。 **变量类型**列表中应显示正确的变量类型，并**控件类型**框应显示正确的控件类型。

9. 在中**注释**框中，添加你想要显示在代码中的注释。

10. 单击 **“确定”**。

## <a name="see-also"></a>请参阅

[将消息映射到函数](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[用代码向导添加功能](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[添加类](../../ide/adding-a-class-visual-cpp.md)<br/>
[添加成员函数](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[添加成员变量](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[重写虚函数](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC 消息处理程序](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[导航类结构](../../ide/navigating-the-class-structure-visual-cpp.md)

---
title: 对话框编辑器 （c + +） |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.dialog
- vc.editors.dialog.F1
dev_langs:
- C++
helpviewer_keywords:
- resource editors [C++], Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes [C++], editing
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c1fc2d9f816e5487f5d89f9c429db85f2592731f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439531"
---
# <a name="dialog-editor-c"></a>对话框编辑器 （c + +）

**对话框**编辑器允许您创建或编辑对话框资源。 通过双击对话框的.rc 文件中打开对话框编辑器**资源视图**窗口 (**视图** > **资源视图**)。 请注意，**资源视图**在 Express 版本中不可用。

制作新对话框（或对话框模板）的前期步骤之一就是将控件添加到对话框。 在中**对话框**编辑器中，您可以排列控件以适应特定的大小、 形状或对齐方式，也可以移动它们大约在对话框中正常运行。 删除控件也很容易。

可将对话框存储为模板以便重复使用。 也可在设计对话框和编辑实现它的代码之间进行轻松切换。

还可在对话框编辑器中编辑单个或多个控件的属性。 您可以更改 tab 键顺序，即，的顺序控件获得焦点**选项卡**按下键，也可以定义允许用户选择使用键盘控制的访问键 （组合键）。 有关预设的访问键列表，请参阅 [对话框编辑器的快捷键](../windows/accelerator-keys-for-the-dialog-editor.md)。

**对话框**编辑器还允许你使用自定义控件，包括 ActiveX 控件。 此外，可以编辑 [窗体视图](../mfc/reference/cformview-class.md)、 [记录视图](../data/record-views-mfc-data-access.md)或 [对话栏](../mfc/dialog-bars.md)。

从 Visual Studio 2015 开始，你可以使用对话框编辑器定义动态布局，指定控件如何移动和调整用户调整对话框大小时。 有关详细信息，请参阅 [Dynamic Layout](../mfc/dynamic-layout.md)。

- [创建新对话框](../windows/creating-a-new-dialog-box.md)

- [创建用户在运行时无法退出的对话框](../windows/creating-a-dialog-box-that-users-cannot-exit.md)

- [显示或隐藏对话框编辑器工具栏](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)

- [在对话框编辑器和代码之间切换](../windows/switching-between-dialog-box-controls-and-code.md)

- [对话框中的控件](../windows/controls-in-dialog-boxes.md)

- [添加对话框控件的事件处理程序](../windows/adding-event-handlers-for-dialog-box-controls.md)

- [测试对话框](../windows/testing-a-dialog-box.md)

- [对话框编辑器的快捷键](../windows/accelerator-keys-for-the-dialog-editor.md)

- [对话框编辑器疑难解答](../windows/troubleshooting-the-dialog-editor.md)

   > [!TIP]
   > 使用时**对话框**编辑器中的，在许多情况下，您可以单击鼠标右键以显示常用命令的快捷菜单。

有关将资源添加到托管项目的信息，请参阅[桌面应用中的资源](/dotnet/framework/resources/index)中 *.NET Framework 开发人员指南*。 有关手动将资源文件添加到托管项目、 访问资源、 显示静态资源和将资源字符串分配给属性的信息，请参阅[桌面应用中创建资源文件](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)。 全球化和本地化的托管应用中的资源的信息，请参阅[Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)。

## <a name="requirements"></a>要求

Win32

## <a name="see-also"></a>请参阅

[资源编辑器](../windows/resource-editors.md)<br/>
[控件](../mfc/controls-mfc.md)<br/>
[控件类](../mfc/control-classes.md)<br/>
[对话框类](../mfc/dialog-box-classes.md)<br/>
[对话框控件和变量类型](../ide/dialog-box-controls-and-variable-types.md)
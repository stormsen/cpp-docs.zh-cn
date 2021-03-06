---
title: 添加方法 (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Add Method Wizard [C++]
- methods [C++], adding
ms.assetid: 4ba4e45f-fa38-4d5e-af44-cbec0a7ab558
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b0082ef7df5ddcc698741ebd4f3fb5455b6614d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390703"
---
# <a name="adding-a-method--visual-c"></a>添加方法 (Visual C++)

可以使用[添加方法向导](../ide/add-method-wizard.md)，向项目中的接口添加方法。 如果项目包含与接口有关的类，向导也会修改此类。

### <a name="to-add-a-method-to-your-object"></a>向对象添加方法

1. 在类视图中，展开项目节点，显示想要向其添加方法的接口。

   > [!NOTE]
   > 也可以向位于库节点下的调度接口添加方法（除非该项目已特性化）。

1. 右键单击接口的名称。

1. 在快捷菜单上单击“添加”，然后单击“添加方法”。

1. 在添加方法向导中，提供创建方法的信息。

1. 在向导的 [IDL 特性](../ide/idl-attributes-add-method-wizard.md)页中，为此方法指定任何接口定义语言设置。

1. 单击“完成”以添加方法。

## <a name="see-also"></a>请参阅

[创建 COM 接口](../ide/creating-a-com-interface-visual-cpp.md)<br>
[编辑 COM 接口](../ide/editing-a-com-interface.md)
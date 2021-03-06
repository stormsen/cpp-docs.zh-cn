---
title: HLSL 属性页：常规 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EntryPointName
dev_langs:
- C++
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f29228fb7744f93014ba35b75ed5a42d6531cd28
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376988"
---
# <a name="hlsl-property-pages-general"></a>HLSL 属性页：常规

若要配置 HLSL 编译器 (fxc.exe) 的以下属性，请使用其“常规”属性页。 有关如何访问 HLSL 文件夹中的“常规”属性页，请参阅[使用项目属性](../ide/working-with-project-properties.md)。

## <a name="uielement-list"></a>UIElement 列表

- **附加包含目录**

   将一个或多个目录添加到包含路径。 使用分号来隔开目录。

该属性对应于“/I[path]”命令行参数。

- **入口点名称**

   为着色器指定入口点。 默认情况下，该值为 main。

该属性对应于“//E[name]”命令行参数。

- **禁用优化**

   若要启用优化，则为“是(/Od)”；否则为“否”。 默认情况下，“调试”配置的值为“是(/Od)”，而“发布”配置的值为“否”。

HLSL 编译器的“/Od”命令行参数隐式应用“/Gfp”命令行参数，但输出可能与通过显示传递“/Od”和“/Gfp”命令行参数生成的输出不同。

- **启用调试信息**

   若启用调试信息，则为“是(/Od)”；否则为“否”。 默认情况下，“调试”配置的值为“是(/Zi)”，而“发布”配置的值为“否”。

- **着色器类型**

   指定着色器类型。 不同种类的着色器实现图形管道的不同部分。 某些类型的着色器仅可用于较新的着色器模型（由“着色器模型”属性指定），例如，计算着色器在着色器模型 5 中引入。

   此属性对应于 HLSL 编译器的 **/T \[type]_\[model]** 命令行参数的 **\[type]** 部分。 “着色器模型”属性指定参数的“[model]”部分。

- **着色器模型**

   指定着色器模型。 不同的着色器模型具有不同的功能。 一般情况下，较新的着色器模型提供扩展功能，但需要更新式图形硬件来运行着色器代码。 某些类型的着色器（由“着色器类型”属性指定）仅可用于较新的着色器模型，例如，计算着色器在着色器模型 5 中引入。

   此属性对应于 HLSL 编译器的 **/T \[type]_\[model]** 命令行参数的 **\[model]** 部分。 “着色器类型”属性指定参数的“[type]”部分。

- **预处理器定义**

   添加一个或多个预处理器符号定义以应用于 HLSL 源代码文件。 使用分号来隔开符号定义。

   此属性对应于 HLSL 编译器的 /D \[definitions] 命令行参数。

## <a name="see-also"></a>请参阅

[“HLSL”属性页](../ide/hlsl-property-pages.md)<br>
[HLSL 属性页：高级](../ide/hlsl-property-pages-advanced.md)<br>
[HLSL 属性页：输出文件](../ide/hlsl-property-pages-output-files.md)
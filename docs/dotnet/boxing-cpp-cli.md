---
title: 装箱 (C + + CLI) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4c513b0148e2553440e02f9b0d255a0d5750e2d1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372507"
---
# <a name="boxing-ccli"></a>装箱 (C++/CLI)

装箱是将值类型转换为类型的过程`object`或由值类型实现任何接口类型。 当公共语言运行时 (CLR) 装箱值类型时，它包装中的值`System.Object`并将其存储在托管堆上。 取消装箱将从对象中提取值类型。 装箱是隐式的；取消装箱是显式的。

## <a name="related-articles"></a>相关文章

|标题|描述|
|-----------|-----------------|
|[如何：显式请求装箱](../dotnet/how-to-explicitly-request-boxing.md)|介绍如何显式请求装箱的变量上。|
|[如何：使用 gcnew 创建值类型和使用隐式装箱](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|演示如何使用`gcnew`创建可以在托管的垃圾回收堆放置一个装箱的值类型。|
|[如何：取消装箱](../dotnet/how-to-unbox.md)|演示如何取消装箱和修改值。|
|[标准转换和隐式装箱](../dotnet/standard-conversions-and-implicit-boxing.md)|显示的标准转换将选择由编译器通过需要进行装箱的转换。|
|[使用 C++/CLI (Visual C++) 进行 .NET 编程](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Visual C++ 文档中有关 .NET 编程的顶级文章。|
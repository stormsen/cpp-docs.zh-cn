---
title: 导入到使用 __declspec （dllimport） 的应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- __declspec
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08a406c8884cdcb9d4b2ead2e61d416ac580fd73
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704076"
---
# <a name="importing-into-an-application-using-declspecdllimport"></a>使用 __declspec(dllimport) 导入到应用程序中

使用 DLL 定义的公共符号的程序称为导入它们。 当创建标头文件，对于使用您的 Dll，生成的应用程序使用 **__declspec （dllimport)** 上的公共符号声明。 关键字 **__declspec （dllimport)** 无论导出使用.def 文件或使用的工作方式 **__declspec （dllexport)** 关键字。

若要使代码更具可读性，定义为宏 **__declspec （dllimport)** ，然后使用该宏来声明每个导入的符号：

```
#define DllImport   __declspec( dllimport )

DllImport int  j;
DllImport void func();
```

使用 **__declspec （dllimport)** 是函数声明上可选的但编译器会生成更高效的代码，如果使用此关键字。 但是，必须使用 **__declspec （dllimport)** 访问 DLL 的公共数据符号和对象的导入可执行文件。 请注意，您的 DLL 的用户仍需要链接导入库。

DLL 和客户端应用程序，可以使用相同的标头文件。 若要执行此操作，使用特殊的预处理器符号，指示是否正在生成 DLL 或生成客户端应用程序。 例如：

```
#ifdef _EXPORTING
   #define CLASS_DECLSPEC    __declspec(dllexport)
#else
   #define CLASS_DECLSPEC    __declspec(dllimport)
#endif

class CLASS_DECLSPEC CExampleA : public CObject
{ ... class definition ... };
```

## <a name="what-do-you-want-to-do"></a>你希望做什么？

- [初始化 DLL](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么？

- [导入和导出内联函数](../build/importing-and-exporting-inline-functions.md)

- [相互导入](../build/mutual-imports.md)

## <a name="see-also"></a>请参阅

[导入到应用程序中](../build/importing-into-an-application.md)
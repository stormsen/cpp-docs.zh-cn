---
title: "Windows 应用商店应用程序、Windows 运行时和 C 运行时 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Windows 应用商店应用程序、Windows 运行时和 C 运行时
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]应用是在 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 中执行的 [!INCLUDE[win8](../build/includes/win8_md.md)]中运行的程序。  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]是一个控制函数、变量以及可用于 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]应用的资源的可信环境。  但依据设计，[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]限制会阻止在 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]应用中使用大多数 C 运行库 \(CRT\) 功能。  
  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]不支持以下 CRT 功能：  
  
-   与不受支持的功能相关的大多数 CRT 函数。  
  
     例如，[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]应用无法使用 `exec` 和 `spawn` 系列的例程创建过程。  
  
     对于 CRT 函数在 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]应用中不受支持的情况，其参考文章中会进行说明。  
  
-   大多数多字节字符和字符串函数。  
  
     但是，支持 Unicode 和 ANSI 文本。  
  
-   控制台应用和命令行参数。  
  
     但是，传统桌面应用仍支持控制台和命令行参数。  
  
-   环境变量。  
  
-   当前工作目录的概念。  
  
-   静态链接到 CRT 且使用 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\/MT 或 [应用和 DLL](../build/reference/md-mt-ld-use-run-time-library.md) 编译器选项生成的 `/MTd`。  
  
     即，使用多线程、静态版本的 CRT 的应用。  
  
-   使用 [\/MDd](../build/reference/md-mt-ld-use-run-time-library.md) 编译器选项生成的应用。  
  
     即，多线程的特定于 DLL 的调试版本的 CRT。  此类应用在 [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)]中不受支持。  
  
 有关不适用于 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]应用的 CRT 函数的完整列表和替代函数的建议，请参阅[不支持 \/ZW 的 CRT 函数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)。  
  
## 请参阅  
 [兼容性](../c-runtime-library/compatibility.md)   
 [Windows 运行时不支持的 CRT 函数](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)   
 [按类别分的运行时例程](../c-runtime-library/run-time-routines-by-category.md)
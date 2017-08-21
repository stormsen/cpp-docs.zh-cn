---
title: "MFC 应用程序向导的数据库支持 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.database"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC 应用程序向导，数据库支持"
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# MFC 应用程序向导的数据库支持
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

此页提供允许指定项目的数据库支持级别（如果必要，外加数据源）的选项。  
  
 **数据库支持**  
 设置项目的数据库支持级别。  
  
|选项|说明|  
|--------|--------|  
|**无**|不提供数据库支持。  这是默认选项。|  
|**仅支持头文件**|为应用程序提供基本的数据库支持。<br /><br /> <ul><li>如果选择“客户端类型”下的 ODBC 支持，MFC 应用程序向导将在项目中包含头文件 AFXDB.H。  它将添加链接库，但不创建任何数据库特定的类。  可在以后创建记录集来检验并更新记录。</li><li>如果选择“客户端类型”下的 OLE DB 支持，则将包含下列头文件：<br /><br /> <ul><li>ATLBASE.H</li><li>AFXOLEDB.H</li><li>ATLPLUS.H</li></ul></li></ul>|  
|**不支持文件的数据库视图**|包含数据库头文件、链接库、记录视图和记录集。（仅对在[应用程序类型](../../mfc/reference/application-type-mfc-application-wizard.md)页中选择了“文档\/视图结构支持”选项的应用程序可用。）此选项包含文档支持，但不包含序列化支持。  如果选择包括数据库视图，则必须指定数据源。|  
|**支持文件的数据库视图**|包含数据库头文件、链接库、记录视图和记录集。（仅对在**“应用程序类型”**页中选择了“文档\/视图结构支持”选项的应用程序可用。）此选项支持文档序列化，比如可以用它来更新用户配置文件。  数据库应用程序通常以记录而非文件为基础进行操作，因此不需要序列化。  但是，序列化有一个特殊用处。  如果选择包括数据库视图，则必须指定数据源。|  
  
> [!NOTE]
>  在“数据库支持”下，如果选择“不支持文件的数据库视图”或者“支持文件的数据库视图”，则视图类的派生将因选择的“客户端类型”而异，如下所示：  
  
-   如果选择“客户端类型”下的 **ODBC**，则应用程序的视图类从 [CRecordView](../../mfc/reference/crecordview-class.md) 导出。  此类与 MFC 应用程序向导同时为您创建的 [CRecordset](../../mfc/reference/crecordset-class.md) 导出类关联。  此选项为您提供基于窗体的应用程序，在该应用程序中记录视图用于通过记录集查看和更新记录。  
  
-   如果选择“客户端类型”下的 **OLE DB**，则视图类从 [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md) 导出并且与 [CTable](../../data/oledb/ctable-class.md) 或 [CCommand](../../data/oledb/ccommand-class.md) 导出类关联。  
  
 **客户端类型**  
 指示项目使用 OLE DB 类还是 ODBC 类。  
  
|选项|说明|  
|--------|--------|  
|**OLE DB**|选择此选项后，单击**“数据源”**按钮将调用**“数据链接属性”**向导以帮助您创建 OLE DB 数据源连接。|  
|**ODBC**|选择此选项后，单击**“数据源”**按钮将调用“选择数据源”向导以帮助您创建 ODBC 数据源连接。|  
  
 **数据源**  
 单击**“数据源”**按钮，使用指定的驱动程序或提供程序以及数据库来设置数据源。  如果选择了“客户端类型”选项中的“OLE DB”，此按钮显示**“数据链接属性”**对话框。  如果选择了“客户端类型”选项下的 ODBC，则此按钮提供“选择数据源”对话框。  仅当选择在应用程序中包括数据库视图时，此选项才可用。  
  
|选项|说明|  
|--------|--------|  
|**“数据链接属性”** \(OLE DB\)|使用指定的 OLE DB 提供程序建立指定的数据源。  必须指定 OLE DB 提供程序、数据的位置、数据源、登录 ID 和（可选）密码。  有关此对话框的详细信息，请参见 [ATL OLE DB 使用者向导](../../atl/reference/atl-ole-db-consumer-wizard.md)中的“数据源”。|  
|“选择数据源” \(ODBC\)|使用指定的 ODBC 驱动程序建立指定的数据源。  必须选择数据源名称以选择数据源表。  向导将表的所有列绑定到 `CRecordset` 导出类的成员变量。  有关此对话框的详细信息，请参见 [MFC ODBC 使用者向导](../../mfc/reference/mfc-odbc-consumer-wizard.md)中的“数据源”。|  
  
> [!NOTE]
>  在以前的版本中，按住 Shift 单击**“数据源”**按钮将打开“文件打开”对话框，从中可以选择数据链接 \(.udl\) 文件。  不再支持该功能。  
  
 **生成特性化数据库类**  
 仅对 OLE DB 客户端可用。  指定生成项目中的数据库类是否使用特性。  
  
 **绑定所有列**  
 仅对 ODBC 客户端可用。  指定是否绑定选定表中的所有列。  如果选中此框，则绑定所有列；如果不选择此框，则不绑定任何列，必须在记录集类中手动绑定它们。  
  
 **类型**  
 仅对 ODBC 客户端可用。  指定记录集是动态集还是快照，详见下表。  
  
|选项|说明|  
|--------|--------|  
|**动态集**|指定记录集是动态集。  动态集是查询的结果，为查询数据库的数据提供索引视图。  动态集仅缓存原始数据的整数索引，因此比快照提供更好的性能。  索引直接指向作为查询结果找到的每个记录并指示记录是否被移除。  还可访问查询记录中的更新信息。|  
|快照|指定记录集为快照。  快照是查询的结果，并且是某一时间点数据库的概况。  作为查询结果找到的所有记录都被缓存，所以不会看到对原始记录所做的任何更改。|  
  
## 请参阅  
 [MFC 应用程序向导](../../mfc/reference/mfc-application-wizard.md)
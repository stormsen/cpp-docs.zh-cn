---
title: 以编程方式在 ODBC 数据源中创建表 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b4db77aae6050f5612c7da14c061e49db142669e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106007"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>数据源：以编程方式在 ODBC 数据源中创建表

本主题说明如何创建表以获取你的数据源，使用`ExecuteSQL`类的成员函数`CDatabase`，将该函数传递一个字符串，包含**CREATE TABLE** SQL 语句。  
  
有关在 MFC 中的 ODBC 数据源的常规信息，请参阅[数据源 (ODBC)](../../data/odbc/data-source-odbc.md)。 本主题[数据源： 以编程方式配置 ODBC 数据源](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md)介绍了如何创建数据源。  
  
数据源建立后，您可以轻松创建使用表`ExecuteSQL`成员函数和**CREATE TABLE** SQL 语句。 例如，如果您有`CDatabase`对象调用`myDB`，可以使用下面的 MFC 代码来创建表：  
  
```  
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",   
                         OfficeName TEXT(10))");  
```  
  
此代码示例创建名为"办公室"所维护的 Microsoft Access 数据源连接中的表`myDB`; 表中包含两个字段"OfficeID"和"OfficeName。"  
  
> [!NOTE]
>  中指定的字段类型**CREATE TABLE** SQL 语句可能因你使用的 ODBC 驱动程序。 Microsoft 查询程序 （随 Visual c + + 1.5） 是一种方法来发现什么类型的字段是可用于数据源。 在 Microsoft 查询中，单击**文件**，单击**表定义**，从数据源，选择一个表并查看中显示的类型**类型**组合框。 SQL 语法还存在是为了创建索引。  
  
## <a name="see-also"></a>请参阅  

[数据源 (ODBC)](../../data/odbc/data-source-odbc.md)
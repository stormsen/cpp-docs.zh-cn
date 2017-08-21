---
title: "不完整类型 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- void keyword [C], incomplete
- types [C], incomplete
- incomplete types
- unions, incomplete
- arrays [C], incomplete types
- void keyword [C]
- structures, incomplete
ms.assetid: 01bc0cf6-9fa7-458c-9371-ecbe54ea6aee
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: ebc73813c28f5ccd25b28cadf283412a204b57d3
ms.contentlocale: zh-cn
ms.lasthandoff: 05/18/2017

---
# <a name="incomplete-types"></a>不完整类型
不完整类型是一种用于描述标识符但缺少确定该标识符的大小所需的信息的类型。 “不完整类型”可以是：  
  
-   您尚未指定其成员的结构类型。  
  
-   您尚未指定其成员的联合类型。  
  
-   您尚未指定其维度的数组类型。  
  
 void 类型是无法完成的不完整类型。 若要完成不完整类型，请指定缺少的信息。 以下示例演示如何创建和完成不完整类型。  
  
-   若要创建不完整的结构类型，请声明结构类型而不指定其成员。 在本例中，`ps` 指针指向称为 `student` 的不完整的结构类型。  
  
    ```  
    struct student *ps;  
    ```  
  
-   若要完成不完整的结构类型，请在稍后在指定其成员的同一范围中声明相同的结构类型，如下所示：  
  
    ```  
    struct student  
    {  
        int num;  
    }                   /* student structure now completed */  
    ```  
  
-   若要创建不完整的数组类型，请声明数组类型而不指定其重复计数。 例如：  
  
    ```  
    char a[];  /* a has incomplete type */  
    ```  
  
-   若要完成不完整的数组类型，请在稍后在指定其重复计数的同一范围中声明相同的名称，如下所示：  
  
    ```  
    char a[25]; /* a now has complete type */  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [声明和类型](../c-language/declarations-and-types.md)
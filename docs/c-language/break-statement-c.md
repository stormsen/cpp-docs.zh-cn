---
title: "break 语句 (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- break
dev_langs:
- C++
helpviewer_keywords:
- break keyword [C]
ms.assetid: 015627c7-0924-49b2-a4d1-c77edf5eae6a
caps.latest.revision: 8
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
ms.openlocfilehash: 994f4b82a95fa6db187f35da63450775642bdf68
ms.contentlocale: zh-cn
ms.lasthandoff: 05/18/2017

---
# <a name="break-statement-c"></a>break 语句 (C)
`break` 语句将终止执行其所在位置最接近的外围 `do`、`for`、`switch` 或 `while` 语句。 控制权将传递给已终止语句后面的语句。  
  
## <a name="syntax"></a>语法  
 *jump-statement*:  
 `break;`  
  
 `break` 语句通常用于终止 `switch` 语句中的特定用例的处理。 缺少外围的迭代或 `switch` 语句会引发错误。  
  
 在嵌套语句中，`break` 语句只终止直接包围它的 `do`、`for`、`switch` 或 `while` 语句。 可以在嵌套结构外部的其他地方使用 `return` 或 `goto` 语句来移交控制权。  
  
 以下示例演示了 `break` 语句：  
  
```  
#include <stdio.h>  
int main() {  
   char c;  
   for(;;) {  
      printf_s( "\nPress any key, Q to quit: " );  
  
      // Convert to character value  
      scanf_s("%c", &c);  
      if (c == 'Q')  
          break;  
   }  
} // Loop exits only when 'Q' is pressed  
```  
  
## <a name="see-also"></a>另请参阅  
 [break 语句](../cpp/break-statement-cpp.md)
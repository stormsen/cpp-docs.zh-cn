---
title: "编译器错误 C3070 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3070
dev_langs:
- C++
helpviewer_keywords:
- C3070
ms.assetid: ac88584d-40a6-4176-90f3-2371c3c935f2
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 83855b5e27641b1684133d69ce8f6c4e1a3d5871
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3070"></a>编译器错误 C3070
“property”: 属性没有“set”方法  
  
 未定义属性的 set 访问器方法。 有关详细信息，请参阅[属性](../../windows/property-cpp-component-extensions.md)。  
  
 以下示例生成 C3070：  
  
```  
// C3070.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int size) {  
      m_data = gcnew array<int>(size);  
   }  
  
   property int % MyProp[int] {  
      int% get(int index) {   
         return m_data[index];   
      }  
   }  
  
   property int % MyProp2[int] {  
      int% get(int index) {   
         return m_data[index];  
      }  
      void set(int index, int % value) {}  
   }  
  
   property const int % MyProp3[int] {  
      const int% get(int index) {   
         return m_data[index];  
      }  
      void set(int index, const int % value) {}  
   }  
  
private:  
   array<int>^ m_data;  
};  
  
int main() {  
   R^ r = gcnew R(10);  
   r->MyProp[4] = 4;   // C3070  
  
   int value = 4;  
   r->MyProp2[4] = value;   // OK  
   r->MyProp3[4] = 4;   // OK  
}  
```
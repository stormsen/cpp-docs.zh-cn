---
title: '&lt;hash_set&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <hash_set>
- std.<hash_set>
- std::<hash_set>
dev_langs:
- C++
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: 22
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 3941ccdd426e88e93591e3e759fcf9219f79d8ab
ms.contentlocale: zh-cn
ms.lasthandoff: 04/29/2017

---
# <a name="lthashsetgt"></a>&lt;hash_set&gt;
> [!NOTE]
>  此标头已废弃不用。 替代项为 [<unordered_set>](../standard-library/unordered-set.md)。  
  
 定义容器模板类 hash_set 和 hash_multiset 及其支持的模板。  
  
## <a name="syntax"></a>语法  
  
```  
#include <hash_set>  
  
```  
  
## <a name="remarks"></a>备注  
  
### <a name="operators"></a>运算符  
  
|Hash_set 版本|Hash_multiset 版本|说明|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_set)](../standard-library/hash-set-operators.md#op_neq)|[operator!= (hash_multiset)](../standard-library/hash-set-operators.md#op_neq)|测试运算符左侧的 hash_set 或 hash_multiset 对象是否不等于右侧的 hash_set 或 hash_multiset 对象。|  
|[operator== (hash_set)](../standard-library/hash-set-operators.md#op_eq_eq)|[operator== (hash_multiset)](../standard-library/hash-set-operators.md#op_eq_eq)|测试运算符左侧的 hash_set 或 hash_multiset 对象是否等于右侧的 hash_set 或 hash_multiset 对象。|  
  
### <a name="specialized-template-functions"></a>专用化模板函数  
  
|Hash_set 版本|Hash_multiset 版本|说明|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_set)](../standard-library/hash-set-functions.md#swap)|[swap (hash_multiset)](../standard-library/hash-set-functions.md#swap_hash_multiset)|交换两个 hash_set 或 hash_multiset 的元素。|  
  
### <a name="classes"></a>类  
  
|||  
|-|-|  
|[hash_compare 类](../standard-library/hash-compare-class.md)|描述了一个对象，任何哈希关联容器（hash_map、hash_multimap、hash_set 或 hash_multiset）都可将该对象用作默认的 **Traits** 参数对象，以对其所包含的元素进行排序和哈希处理。|  
|[hash_set 类](../standard-library/hash-set-class.md)|用于存储和快速检索集合中的数据，此集合中包含的元素值是唯一的并且用作键值。|  
|[hash_multiset 类](../standard-library/hash-multiset-class.md)|用于存储和快速检索集合中的数据，此集合中包含的元素值是唯一的并且用作键值。|  
  
## <a name="see-also"></a>另请参阅  
 [头文件引用](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 标准库中的线程安全性](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 标准库参考](../standard-library/cpp-standard-library-reference.md)




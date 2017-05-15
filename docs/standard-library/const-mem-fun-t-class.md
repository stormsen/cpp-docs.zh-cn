---
title: "const_mem_fun_t 类 | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- const_mem_fun_t
- xfunctional/std::const_mem_fun_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun_t class
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
caps.latest.revision: 20
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: b68670f5c297bd4ec031985d5c16bb8f6da1cc14
ms.contentlocale: zh-cn
ms.lasthandoff: 04/19/2017

---
# <a name="constmemfunt-class"></a>const_mem_fun_t 类
一种适配器类，在使用引用自变量进行初始化的情况下，该类允许将不带任何自变量的 const 成员函数作为一元函数对象调用。  
  
## <a name="syntax"></a>语法  
  
```
template <class Result, class Type>
class const_mem_fun_t : public unary_function <Type *, Result>  
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type* Pleft) const;
 };
```  
  
#### <a name="parameters"></a>参数  
 `Pm`  
 一个指针，指向要转换为函数对象的 **Type** 类成员函数。  
  
 `Pleft`  
 要在其上调用 `Pm` 成员函数的对象。  
  
## <a name="return-value"></a>返回值  
 一个自适应一元函数。  
  
## <a name="remarks"></a>备注  
 模板类存储 `Pm` 的副本，它必须是专用成员对象中指向类 **Type** 的成员函数的指针。 它将其成员函数 `operator()` 定义为返回 ( `Pleft`->\* `Pm`)() **const**。  
  
## <a name="example"></a>示例  
 通常不直接使用 `const_mem_fun_t` 的构造函数；helper 函数 `mem_fun` 用于调整成员函数。 有关如何使用成员函数适配器的示例，请参阅 [mem_fun](../standard-library/functional-functions.md#mem_fun)。  
  
## <a name="requirements"></a>要求  
 **标头：**\<functional>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>另请参阅  
 [C++ 标准库中的线程安全性](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 标准库参考](../standard-library/cpp-standard-library-reference.md)




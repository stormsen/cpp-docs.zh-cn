---
title: is_compound 类 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_compound
dev_langs:
- C++
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8916d92abcfb05dbef68e8909b8a52a82c35af24
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106986"
---
# <a name="iscompound-class"></a>is_compound 类

测试指定的类型是否为基本类型。

## <a name="syntax"></a>语法

```cpp
template <class Ty>
struct is_compound;
```

### <a name="parameters"></a>参数

*Ty*<br/>
要查询的类型。

## <a name="remarks"></a>备注

类型谓词的实例将保留**false**如果的类型*Ty*是一种基本类型 (即，如果[is_fundamental](../standard-library/is-fundamental-class.md)\<Ty > 保存**true**);否则，它存储 **，则返回 true**。 因此，谓词 **，则返回 true**如果*Ty*是数组类型、 函数类型、 指向**void**或对象或函数、 引用、 类、 联合、 枚举，或指向非静态类成员的指针或*限定了 cv*其中之一的窗体。

## <a name="example"></a>示例

```cpp
// std__type_traits__is_compound.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_compound<trivial> == " << std::boolalpha
        << std::is_compound<trivial>::value << std::endl;
    std::cout << "is_compound<int[]> == " << std::boolalpha
        << std::is_compound<int[]>::value << std::endl;
    std::cout << "is_compound<int()> == " << std::boolalpha
        << std::is_compound<int()>::value << std::endl;
    std::cout << "is_compound<int&> == " << std::boolalpha
        << std::is_compound<int&>::value << std::endl;
    std::cout << "is_compound<void *> == " << std::boolalpha
        << std::is_compound<void *>::value << std::endl;
    std::cout << "is_compound<int> == " << std::boolalpha
        << std::is_compound<int>::value << std::endl;

    return (0);
    }

```

```Output
is_compound<trivial> == true
is_compound<int[]> == true
is_compound<int()> == true
is_compound<int&> == true
is_compound<void *> == true
is_compound<int> == false
```

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间：** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_class 类](../standard-library/is-class-class.md)<br/>

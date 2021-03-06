---
title: end 函数 |Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::end
dev_langs:
- C++
helpviewer_keywords:
- end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff953d33fb882bf65af101c422093ddbc1aedf2e
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105225"
---
# <a name="end-function"></a>end 函数

返回指向集合末尾以外的迭代器，该集合由指定的接口参数访问。

## <a name="syntax"></a>语法

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    end(
        IVector<T>^ v       );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    end(
        IVectorView<T>^ v
       );
template <typename T>
    ::Platform::Collections::InputIterator<T>
    end(
        IIterable<T>^ i
       );
```

#### <a name="parameters"></a>参数

*T*<br/>
模板类型参数。

*v*<br/>
向量的集合\<T > 或 VectorView\<T > 对象访问的 IVector\<T >，或 IVectorView\<T > 接口。

*i*<br/>
对象的 arbitraty Windows 运行时集合的访问的 IIterable\<T > 接口。

### <a name="return-value"></a>返回值

指向集合结尾之外的迭代器。

### <a name="remarks"></a>备注

前两个模板函数返回迭代器，第三个模板函数返回输入迭代器。

[返回的](../cppcx/platform-collections-vectorviewiterator-class.md) Platform::Collections::VectorViewIterator `end` 对象是存储 `VectorProxy<T>`类型的元素的代理迭代器。 不过，代理对象对于用户代码应该不可见。 有关更多信息，请参见 [集合 (C++/CX)](../cppcx/collections-c-cx.md)。

### <a name="requirements"></a>要求

**标头：** collection.h

**命名空间：** Windows::Foundation::Collections

## <a name="see-also"></a>请参阅

[Windows::Foundation::Collections Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)
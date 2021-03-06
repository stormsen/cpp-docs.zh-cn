---
title: VerifyInheritanceHelper 结构 |Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInheritanceHelper structure
- Microsoft::WRL::Details::VerifyInheritanceHelper::Verify method
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2a011b0583d8221ec49d16236add978ac647acc3
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788924"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper 结构

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
template <typename I, typename Base>
struct VerifyInheritanceHelper;

template <typename I>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>参数

*I*<br/>
一种类型。

*基本*<br/>
另一种类型。

## <a name="remarks"></a>备注

测试是否有一个接口派生自另一个接口。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

名称                                       | 描述
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[Verifyinheritancehelper:: Verify](#verify) | 测试当前的模板参数指定的两个接口，并确定是否派生自另一个接口。

## <a name="inheritance-hierarchy"></a>继承层次结构

`VerifyInheritanceHelper`

## <a name="requirements"></a>要求

**标头：** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="verify"></a>Verifyinheritancehelper:: Verify

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
static void Verify();
```

### <a name="remarks"></a>备注

测试当前的模板参数指定的两个接口，并确定是否派生自另一个接口。

如果不派生自另一个接口，则会发出错误。

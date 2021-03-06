---
title: 版本 （c + + COM 属性） |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.version
dev_langs:
- C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ee79fca8784ade6509cfc5854eaaa165b68edee0
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790537"
---
# <a name="version-c"></a>version (C++)

标识类的多个版本间的特定版本。

## <a name="syntax"></a>语法

```cpp
[ version("version") ]
```

### <a name="parameters"></a>参数

*version*<br/>
版本号`coclass`。 如果未指定，则将在.idl 文件中放置 1.0。

## <a name="remarks"></a>备注

**版本**c + + 属性具有相同的功能[版本](/windows/desktop/Midl/version)MIDL 特性并将传递给生成的.idl 文件。

## <a name="example"></a>示例

请参阅[可绑定](bindable.md)的示例使用的示例**版本**。

## <a name="requirements"></a>要求

### <a name="attribute-context"></a>特性上下文

|||
|-|-|
|**适用对象**|**类**，**结构**|
|**可重复**|否|
|**必需的特性**|**coclass**|
|**无效的特性**|无|

有关特性上下文的详细信息，请参阅[特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[编译器特性](compiler-attributes.md)<br/>
[类特性](class-attributes.md)  
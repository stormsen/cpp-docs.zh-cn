---
title: bad_function_call 类| Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::bad_function_call
dev_langs:
- C++
helpviewer_keywords:
- bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b6a450d26480a0e89a115efc5731725f8f8b913
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714189"
---
# <a name="badfunctioncall-class"></a>bad_function_call 类

报告错误的函数调用。

## <a name="syntax"></a>语法

```cpp
class bad_function_call : public std::exception {};
```

## <a name="remarks"></a>备注

该类描述引发的异常以指示在 [function 类](../standard-library/function-class.md)上调用 `operator()`

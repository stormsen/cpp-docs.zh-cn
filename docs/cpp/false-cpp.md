---
title: false （C++） |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- false_cpp
dev_langs:
- C++
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3cd5174ebacd04bd70fbcde29dcbdabb76911c75
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031517"
---
# <a name="false-c"></a>false (C++)

关键字是类型的变量的两个值之一[bool](../cpp/bool-cpp.md)或条件表达式 (条件表达式现**true**布尔表达式)。 例如，如果`i`类型的变量**bool**，则`i = false;`语句分配**false**到`i`。

## <a name="example"></a>示例

```cpp
// bool_false.cpp
#include <stdio.h>

int main()
{
    bool bb = true;
    printf_s("%d\n", bb);
    bb = false;
    printf_s("%d\n", bb);
}
```

```Output
1
0
```

## <a name="see-also"></a>请参阅

[关键字](../cpp/keywords-cpp.md)
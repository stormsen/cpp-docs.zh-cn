---
title: 编写异常处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling [C++], exception handlers
- exception handling [C++], exception handlers
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8956bb673c756224a886dede90cf23d84c3f20c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050965"
---
# <a name="writing-an-exception-handler"></a>编写异常处理程序

异常处理程序通常用于响应特定错误。 您可以使用异常处理语法筛选出您不知道如何处理的所有异常。 其他异常应该传递到为了查找特定异常而编写的其他处理程序（可能在运行库或操作系统中）。

异常处理程序使用 try-except 语句。

## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么？

- [在尝试-除非语句](../cpp/try-except-statement.md)

- [编写异常筛选器](../cpp/writing-an-exception-filter.md)

- [引发软件异常](../cpp/raising-software-exceptions.md)

- [硬件异常](../cpp/hardware-exceptions.md)

- [异常处理程序的限制](../cpp/restrictions-on-exception-handlers.md)

## <a name="see-also"></a>请参阅

[结构化异常处理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
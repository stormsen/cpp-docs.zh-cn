---
title: 编译器警告 （等级 1） C4276 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4276
dev_langs:
- C++
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40a6c85b460e9718a8816598afb016e9c7a493b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116017"
---
# <a name="compiler-warning-level-1-c4276"></a>编译器警告（等级 1）C4276

function： 不提供原型;假定无参数

执行的函数的地址时[__stdcall](../../cpp/stdcall.md)调用约定，您必须提供原型，以便编译器可以创建函数的修饰的名。 由于*函数*具有的原型，编译器创建的修饰的名时，假定函数没有任何参数。
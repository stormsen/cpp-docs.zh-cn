---
title: NMAKE 警告 U4011 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4011
dev_langs:
- C++
helpviewer_keywords:
- U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1038ee86f76789451565ab6799795c851c95a95
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118331"
---
# <a name="nmake-warning-u4011"></a>NMAKE 警告 U4011

目标： 并非所有从属项都可用;未生成目标

给定目标的依赖项不存在或已过期，并用于更新依赖项的命令返回非零退出代码。 /K 选项告诉 NMAKE 以继续处理生成的不相关的部分以及当 NMAKE 会话完成时发出的退出代码 1。

此警告会跟有警告[U4010](../../error-messages/tool-errors/nmake-warning-u4010.md)为未能创建或更新每个依赖项。
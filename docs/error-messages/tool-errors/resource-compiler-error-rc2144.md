---
title: 资源编译器错误 RC2144 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2144
dev_langs:
- C++
helpviewer_keywords:
- RC2144
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62f9eb2b25919a2336c36a459ef41eece447a490
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080488"
---
# <a name="resource-compiler-error-rc2144"></a>资源编译器错误 RC2144

主语言 ID 不是数字

主语言 ID 必须是十六进制语言 ID。 请参阅[语言和国家/地区字符串](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)中*运行时库参考*有关有效的语言 Id 的列表。

如果已使用工具添加资源并将其从 .RC 文件中删除，也可能发生此错误。 若要解决此问题，请在文本编辑器中打开 .RC 文件并手动清理任何未使用的资源。
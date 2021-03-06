---
title: include （) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- include()
dev_langs:
- C++
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83f6bf58138a1e36e1c36131a448b456eb691c27
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407577"
---
# <a name="include"></a>include()
**C + + 专用**  
  
禁用自动排除。  
  
## <a name="syntax"></a>语法  
  
```  
include("Name1"[,"Name2", ...])  
```  
  
### <a name="parameters"></a>参数  
*Name1*  
要强制包含的第一项。  
  
*Name2*  
要强行包含的第二项（如果需要）。  
  
## <a name="remarks"></a>备注  
 
类型库可能包含在系统标头文件或其他类型库中定义的项的定义。 `#import` 尝试通过自动排除此类项来避免多个定义错误。 如果已排除项，如所示[编译器警告 （等级 3） C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)，因此它们不应具有已，此属性可用于禁用自动排除。 此特性可采用任意数量的自变量，每个自变量都是要包含的类型库项的名称。  
  
**结束 c + + 专用**  
  
## <a name="see-also"></a>请参阅  
 
[#import 属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
---
title: 如何： 钉住指针和数组 |Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pointers, pinning
- arrays [C++], pinning
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7adf9d4d45b4acafd65adc27e28d8eb0639d32c8
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2018
ms.locfileid: "49327890"
---
# <a name="how-to-pin-pointers-and-arrays"></a>如何：钉住指针和数组

钉住在托管对象中定义的子对象能够钉住整个对象。  例如，如果数组的任何元素被钉住，则整个数组也被钉住。 没有用于声明钉住的数组的语言扩展。 若要钉住数组，请声明其元素类型的钉住指针，并钉住其中一个元素。

## <a name="example"></a>示例

### <a name="code"></a>代码

```cpp
// pin_ptr_array.cpp
// compile with: /clr
#include <stdio.h>
using namespace System;

int main() {
   array<Byte>^ arr = gcnew array<Byte>(4);
   arr[0] = 'C';
   arr[1] = '+';
   arr[2] = '+';
   arr[3] = '\0';
   pin_ptr<Byte> p = &arr[1];   // entire array is now pinned
   unsigned char * cp = p;

   printf_s("%s\n", cp); // bytes pointed at by cp
                         // will not move during call
}
```

```Output
++
```

## <a name="see-also"></a>请参阅

[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)
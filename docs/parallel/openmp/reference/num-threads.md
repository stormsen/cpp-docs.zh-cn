---
title: num_threads |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- num_threads
dev_langs:
- C++
helpviewer_keywords:
- num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27e39d7db36c121add3598387de52ecb878059b5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405263"
---
# <a name="numthreads"></a>num_threads

设置线程团队中的线程数。

## <a name="syntax"></a>语法

```
num_threads(num)
```

### <a name="parameters"></a>参数

*num*<br/>
线程数

## <a name="remarks"></a>备注

`num_threads`子句具有相同的功能[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)函数。

`num_threads` 适用于以下指令：

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [部分](../../../parallel/openmp/reference/sections-openmp.md)

有关详细信息，请参阅[2.3 parallel 构造](../../../parallel/openmp/2-3-parallel-construct.md)。

## <a name="example"></a>示例

请参阅[并行](../../../parallel/openmp/reference/parallel.md)有关的使用示例`num_threads`子句。

## <a name="see-also"></a>请参阅

[子句](../../../parallel/openmp/reference/openmp-clauses.md)
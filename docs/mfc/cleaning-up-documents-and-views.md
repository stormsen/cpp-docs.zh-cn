---
title: 清理文档和视图 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4325b0de10861fc76ee9ab816376f40ba0ba587
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437412"
---
# <a name="cleaning-up-documents-and-views"></a>清理文档和视图

关闭文档后，框架首先将调用其[DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)成员函数。 如果在文档操作期间分配堆上的任何内存，则 `DeleteContents` 是最佳的释放位置。

> [!NOTE]
>  您不应在文档的析构函数中释放文档数据。 在 SDI 应用程序中，可能重用文档对象。

您可以重写视图的析构函数以释放在堆上分配的任何内存。

## <a name="see-also"></a>请参阅

[初始化和清理文档和视图](../mfc/initializing-and-cleaning-up-documents-and-views.md)


---
title: DDX_DHtml 帮助器宏 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFXDHTML/DDX_DHtml_ElementValue
- AFXDHTML/DDX_DHtml_ElementInnerText
- AFXDHTML/DDX_DHtml_ElementInnerHtml
- AFXDHTML/DDX_DHtml_Anchor_Href
- AFXDHTML/DDX_DHtml_Anchor_Target
- AFXDHTML/DDX_DHtml_Img_Src
- AFXDHTML/DDX_DHtml_Frame_Src
- AFXDHTML/DDX_DHtml_IFrame_Src
dev_langs:
- C++
helpviewer_keywords:
- macros [MFC], exchanging data with HMTL pages
- DDX macros [MFC]
- HTML pages [MFC], helper macros
- DDX (dialog data exchange), DHtml helper macros
- macros [MFC], DDX_DHtml helpers
ms.assetid: c46302d2-ea43-4fea-bfc2-6f590d99f267
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a4dbf1b085ca5ffddd87396fc367bf19f2ad02e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383049"
---
# <a name="ddxdhtml-helper-macros"></a>DDX_DHtml 帮助器宏

DDX_DHtml 帮助器宏允许轻松访问常用的属性的 HTML 页上的控件。

### <a name="data-exchange-macros"></a>数据交换宏

|||
|-|-|
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|设置或检索选定控件的 Value 属性。|
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|设置或检索当前元素的开始和结束标记之间的文本。|
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|设置或检索当前元素的开始和结束标记之间的 HTML。|
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|设置或检索的目标 URL 或定位点。|
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|设置或检索的目标窗口或框架。|
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|设置或检索图像或文档中的视频剪辑的名称。|
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|设置或检索关联的帧的 URL。|
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|设置或检索关联的帧的 URL。|

## <a name="requirements"></a>要求

**标头：** afxdhtml.h

## <a name="ddx_dhtml_anchor_href"></a> DDX_DHtml_Anchor_Href

设置或检索的目标 URL 或定位点。



```
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>参数

*dx*<br/>
一个指向[CDataExchange](../../mfc/reference/cdataexchange-class.md)对象。

*name*<br/>
为 HTML 控件的 ID 参数指定值。

*var*<br/>
正在交换值。

## <a name="remarks"></a>备注

此宏将调用[CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)函数使用 DISPID_IHTMLANCHORELEMENT_HREF 调度 id。

## <a name="ddx_dhtml_anchor_target"></a>  DDX_DHtml_Anchor_Target

设置或检索的目标窗口或框架。

```
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>参数

*dx*<br/>
一个指向[CDataExchange](../../mfc/reference/cdataexchange-class.md)对象。

*name*<br/>
为 HTML 控件的 ID 参数指定值。

*var*<br/>
正在交换值。

## <a name="remarks"></a>备注

此宏将调用[CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)函数使用 DISPID_IHTMLANCHORELEMENT_TARGET 调度 id。

## <a name="ddx_dhtml_elementinnerhtml"></a>  DDX_DHtml_ElementInnerHtml

设置或检索当前元素的开始和结束标记之间的 HTML。



```
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>参数

*dx*<br/>
一个指向[CDataExchange](../../mfc/reference/cdataexchange-class.md)对象。

*name*<br/>
为 HTML 控件的 ID 参数指定值。

*var*<br/>
正在交换值。

## <a name="remarks"></a>备注

此宏将调用[CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)函数使用 DISPID_IHTMLELEMENT_INNERHTML 调度 id。


## <a name="ddx_dhtml_elementinnertext"></a>  DDX_DHtml_ElementInnerText

设置或检索当前元素的开始和结束标记之间的文本。



```
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>参数

*dx*<br/>
一个指向[CDataExchange](../../mfc/reference/cdataexchange-class.md)对象。

*name*<br/>
为 HTML 控件的 ID 参数指定值。

*var*<br/>
正在交换值。

## <a name="remarks"></a>备注

此宏将调用[CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)函数使用 DISPID_IHTMLELEMENT_INNERTEXT 调度 id。

## <a name="ddx_dhtml_elementvalue"></a> DDX_DHtml_ElementValue

设置或检索选定控件的 Value 属性。

```
DDX_DHtml_ElementValue(
    CDataExchange* dx,
    LPCTSTR name,
    var)
```

#### <a name="parameters"></a>参数

*dx*<br/>
一个指向[CDataExchange](../../mfc/reference/cdataexchange-class.md)对象。

*name*<br/>
为 HTML 控件的 ID 参数指定值。

*var*<br/>
正在交换值。 请参阅*值*中[CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)。

## <a name="remarks"></a>备注

运行具有 Value 属性的控件上时，才会成功此宏。 具有值属性的控件包括编辑框、 列表框和组合框。

此宏将调用[CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)函数使用 DISPID_A_VALUE 调度 id。

## <a name="ddx_dhtml_frame_src"></a> DDX_DHtml_Frame_Src

设置或检索关联的帧的 URL。

```
DDX_DHtml_Frame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>参数

*dx*<br/>
一个指向[CDataExchange](../../mfc/reference/cdataexchange-class.md)对象。

*name*<br/>
为 HTML 控件的 ID 参数指定值。

*var*<br/>
正在交换值。

## <a name="remarks"></a>备注

此宏将调用[CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)函数使用 DISPID_IHTMLFRAMEBASE_SRC 调度 id。

## <a name="ddx_dhtml_iframe_src"></a> DDX_DHtml_IFrame_Src

设置或检索关联的帧的 URL。



```
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>参数

*dx*<br/>
一个指向[CDataExchange](../../mfc/reference/cdataexchange-class.md)对象。

*name*<br/>
为 HTML 控件的 ID 参数指定值。

*var*<br/>
正在交换值。

## <a name="remarks"></a>备注

此宏将调用[CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)函数使用 DISPID_IHTMLFRAMEBASE_SRC 调度 id。

## <a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src

获取或检索的图像或文档中的视频剪辑的名称。

```
DDX_DHtml_Img_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>参数

*dx*<br/>
一个指向[CDataExchange](../../mfc/reference/cdataexchange-class.md)对象。

*name*<br/>
为 HTML 控件的 ID 参数指定值。

*var*<br/>
正在交换值。

## <a name="remarks"></a>备注

当使用 DDX_DHtml_Img_Src 宏来检索一个 IMAGE 元素的 src 属性，Internet Explorer 图像对象将返回图像源的完全转义的 URL。 例如，如果 DDX_DHtml_Img_Src 宏用于将一个 IMAGE 元素的 src 属性设置为字符串"一些有趣的图片"，检索该属性，Internet Explorer 时将返回字符串"res://d:\myapplication\myapp.exe/some%20interesting %20picture。"

此宏将调用[CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)函数使用 DISPID_IHTMLIMGELEMENT_SRC 调度 id。


## <a name="see-also"></a>请参阅

[CDHtmlDialog 类](../../mfc/reference/cdhtmldialog-class.md)

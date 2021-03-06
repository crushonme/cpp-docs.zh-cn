---
title: "CMFCToolTipCtrl 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetIconSize
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetParams
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawBorder
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawLabel
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnFillBackground
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetFixedWidth
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetHotRibbonButton
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetLocation
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetParams
dev_langs: C++
helpviewer_keywords:
- CMFCToolTipCtrl [MFC], GetIconSize
- CMFCToolTipCtrl [MFC], GetParams
- CMFCToolTipCtrl [MFC], OnDrawBorder
- CMFCToolTipCtrl [MFC], OnDrawDescription
- CMFCToolTipCtrl [MFC], OnDrawIcon
- CMFCToolTipCtrl [MFC], OnDrawLabel
- CMFCToolTipCtrl [MFC], OnDrawSeparator
- CMFCToolTipCtrl [MFC], OnFillBackground
- CMFCToolTipCtrl [MFC], SetDescription
- CMFCToolTipCtrl [MFC], SetFixedWidth
- CMFCToolTipCtrl [MFC], SetHotRibbonButton
- CMFCToolTipCtrl [MFC], SetLocation
- CMFCToolTipCtrl [MFC], SetParams
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
caps.latest.revision: "33"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ae37349599977b236f111530f170da746b44b425
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctooltipctrl-class"></a>CMFCToolTipCtrl 类
基于 [CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md)的扩展工具提示实现。 基于 `CMFCToolTipCtrl` 类的工具提示可显示图标、标签和说明。 可以使用渐变填充、自定义文本和边框颜色、粗体文本、圆角或气球样式来自定义可视外观。  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>语法  
  
```  
class CMFCToolTipCtrl : public CToolTipCtrl  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|默认构造函数。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[CMFCToolTipCtrl::GetIconSize](#geticonsize)|返回工具提示中的图标大小。|  
|[CMFCToolTipCtrl::GetParams](#getparams)|返回工具提示的显示设置。|  
|[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)|绘制工具提示的边框。|  
|[CMFCToolTipCtrl::OnDrawDescription](#ondrawdescription)||  
|[CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)|显示工具提示中的图标。|  
|[CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)|绘制工具提示标签或计算标签的大小。|  
|[CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)|绘制工具提示中标签和说明之间的分隔符。|  
|[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)|填充工具提示的背景。|  
|[CMFCToolTipCtrl::SetDescription](#setdescription)|设置将由工具提示显示的说明。|  
|[CMFCToolTipCtrl::SetFixedWidth](#setfixedwidth)||  
|[CMFCToolTipCtrl::SetHotRibbonButton](#sethotribbonbutton)||  
|[CMFCToolTipCtrl::SetLocation](#setlocation)||  
|[CMFCToolTipCtrl::SetParams](#setparams)|通过使用 `CMFCToolTipInfo` 对象指定工具提示的视觉外观。|  
  
## <a name="remarks"></a>备注  
 使用`CMFCToolTipCtrl`， `CMFCToolTipInfo`，和[CTooltipManager 类](../../mfc/reference/ctooltipmanager-class.md)对象以在你的应用程序中实现自定义工具提示。  
  
 例如，若要使用气球样式的工具提示，请按照下列步骤执行：  
  
 1. 使用[CWinAppEx 类](../../mfc/reference/cwinappex-class.md)方法以初始化应用程序中的工具提示管理器。  
  
 2. 创建 `CMFCToolTipInfo` 结构，以指定所需的视觉样式：  
  
```  
CMFCToolTipInfo params;  
    params.m_bBoldLabel = FALSE;  
    params.m_bDrawDescription = FALSE;  
    params.m_bDrawIcon = FALSE;  
    params.m_bRoundedCorners = TRUE;  
    params.m_bDrawSeparator = FALSE;  
    if (m_bCustomColors)  
 {  
    params.m_clrFill = RGB (255,
    255,
    255);

    params.m_clrFillGradient = RGB (228,
    228,
    240);

    params.m_clrText = RGB (61,
    83,
    80);

    params.m_clrBorder = RGB (144,
    149,
    168);

 }  
```  
3. 使用[CTooltipManager::SetTooltipParams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams)方法以通过使用中定义的样式设置应用程序中的所有工具提示的视觉样式`CMFCToolTipInfo`对象：  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMFCToolTipCtrl), &params);
```  
你也可以从 `CMFCToolTipCtrl` 派生新类以控制工具提示行为和呈现。 若要指定新的工具提示控制类，请使用 `CTooltipManager::SetTooltipParams` 方法：  
  
```  
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMyToolTipCtrl))  
```  
若要恢复默认的工具提示控件类并将工具提示外观重置回其默认状态，请指定运行时类中的 NULL 和 `SetTooltipParams` 的工具提示信息参数：  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    NULL,
    NULL);
```  
  
## <a name="example"></a>示例  
 下面的示例演示了如何构造 `CMFCToolTipCtrl` 对象、如何设置工具提示显示的说明以及如何设置工具提示控件的宽度。  
  
 [!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/cpp/cmfctooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)  
  
 [CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)  
  
## <a name="requirements"></a>惠?  
 **标头：** afxtooltipctrl.h  
  
##  <a name="cmfctooltipctrl"></a>CMFCToolTipCtrl::CMFCToolTipCtrl  

  
```  
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```  
  
### <a name="parameters"></a>参数  
 [in] `pParams`  
  
### <a name="remarks"></a>备注  
  
##  <a name="geticonsize"></a>CMFCToolTipCtrl::GetIconSize  
 返回工具提示中的图标大小。  
  
```  
virtual CSize GetIconSize();
```  
  
### <a name="return-value"></a>返回值  
 图标，以像素为单位的大小。  
  
##  <a name="getparams"></a>CMFCToolTipCtrl::GetParams  
 返回工具提示的显示设置。  
  
```  
const CMFCToolTipInfo& GetParams() const;  
```  
  
### <a name="return-value"></a>返回值  
 当前的工具提示显示设置，它们将存储在[CMFCToolTipInfo 类](../../mfc/reference/cmfctooltipinfo-class.md)对象。  
  
##  <a name="ondrawborder"></a>CMFCToolTipCtrl::OnDrawBorder  
 绘制工具提示的边框。  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>参数  
 `[in] pDC`  
 指向设备上下文的指针。  
  
 `[in] rect`  
 工具提示的绑定矩形。  
  
 `[in] clrLine`  
 边框颜色。  
  
### <a name="remarks"></a>备注  
 重写此方法在派生类自定义工具提示边框的外观。  
  
##  <a name="ondrawdescription"></a>CMFCToolTipCtrl::OnDrawDescription  

  
```  
virtual CSize OnDrawDescription(
    CDC* pDC,  
    CRect rect,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>参数  
 [in] `pDC`  
 [in] `rect`  
 [in] `bCalcOnly`  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
  
##  <a name="ondrawicon"></a>CMFCToolTipCtrl::OnDrawIcon  
 显示工具提示中的图标。  
  
```  
virtual BOOL OnDrawIcon(
    CDC* pDC,  
    CRect rectImage);
```  
  
### <a name="parameters"></a>参数  
 [in] `pDC`  
 一个指向设备上下文的指针。  
  
 [in] `rectImage`  
 图标的坐标。  
  
### <a name="return-value"></a>返回值  
 `TRUE`如果绘制图标。 否则为`FALSE`。  
  
### <a name="remarks"></a>备注  
 重写此方法在派生类以显示自定义图标。 你还必须重写[CMFCToolTipCtrl::GetIconSize](#geticonsize)启用工具提示以正确地计算文本和说明的布局。  
  
##  <a name="ondrawlabel"></a>CMFCToolTipCtrl::OnDrawLabel  
 绘制工具提示标签或计算标签的大小。  
  
```  
virtual CSize OnDrawLabel(
    CDC* pDC,  
    CRect rect,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>参数  
 `[in] pDC`  
 一个指向设备上下文的指针。  
  
 `[in] rect`  
 标签区域的绑定矩形。  
  
 `[in] bCalcOnly`  
 如果`TRUE`，将不绘制标签。  
  
### <a name="return-value"></a>返回值  
 标签，以像素为单位的大小。  
  
### <a name="remarks"></a>备注  
 如果你想要自定义工具提示标签的外观，重写此方法在派生类。  
  
##  <a name="ondrawseparator"></a>CMFCToolTipCtrl::OnDrawSeparator  
 绘制工具提示中标签和说明之间的分隔符。  
  
```  
virtual void OnDrawSeparator(
    CDC* pDC,  
    int x1,  
    int x2,  
    int y);
```  
  
### <a name="parameters"></a>参数  
 [in] `pDC`  
 一个指向设备上下文的指针。  
  
 [in] `x1`  
 分隔符的左端水平坐标。  
  
 [in] `x2`  
 分隔符的右端的水平坐标。  
  
 [in] `Y`  
 分隔符的垂直坐标。  
  
### <a name="remarks"></a>备注  
 默认实现从点绘制一条直线 (x1，y) 到点 (x2，y)。  
  
 重写此方法在派生类自定义分隔符的外观。  
  
##  <a name="onfillbackground"></a>CMFCToolTipCtrl::OnFillBackground  
 填充工具提示的背景。  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    CRect rect,  
    COLORREF& clrText,  
    COLORREF& clrLine);
```  
  
### <a name="parameters"></a>参数  
 `[in] pDC`  
 一个指向设备上下文的指针。  
  
 `[in] rect`  
 指定要填充的区域的边框。  
  
 `[in] clrText`  
 工具提示前景色。  
  
 `[in] clrLine`  
 边框和标签和说明之间的分隔符线的颜色。  
  
### <a name="remarks"></a>备注  
 默认实现填充指定的矩形`rect`用颜色或指定的最新调用模式[CMFCToolTipCtrl::SetParams](#setparams)。  
  
 如果你想要自定义工具提示的外观，重写此方法在派生类。  
  
##  <a name="setdescription"></a>CMFCToolTipCtrl::SetDescription  
 设置将由工具提示显示的说明。  
  
```  
virtual void SetDescription(const CString strDesrciption);
```  
  
### <a name="parameters"></a>参数  
 `[in] strDesrciption`  
 说明文本。  
  
### <a name="remarks"></a>备注  
 Description 文本将显示在该分隔符在工具提示。  
  
##  <a name="setfixedwidth"></a>CMFCToolTipCtrl::SetFixedWidth  

  
```  
void SetFixedWidth(
    int nWidthRegular,  
    int nWidthLargeImage);
```  
  
### <a name="parameters"></a>参数  
 [in] `nWidthRegular`  
 [in] `nWidthLargeImage`  
  
### <a name="remarks"></a>备注  
  
##  <a name="sethotribbonbutton"></a>CMFCToolTipCtrl::SetHotRibbonButton  

  
```  
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```  
  
### <a name="parameters"></a>参数  
 [in] `pRibbonButton`  
  
### <a name="remarks"></a>备注  
  
##  <a name="setlocation"></a>CMFCToolTipCtrl::SetLocation  

  
```  
void SetLocation(CPoint pt);
```  
  
### <a name="parameters"></a>参数  
 [in] `pt`  
  
### <a name="remarks"></a>备注  
  
##  <a name="setparams"></a>CMFCToolTipCtrl::SetParams  
 通过使用指定的工具提示的视觉外观[CMFCToolTipInfo 类](../../mfc/reference/cmfctooltipinfo-class.md)对象。  
  
```  
void SetParams(CMFCToolTipInfo* pParams);
```  
  
### <a name="parameters"></a>参数  
 `[in] pParams`  
 指向[CMFCToolTipInfo 类](../../mfc/reference/cmfctooltipinfo-class.md)包含显示参数的对象。  
  
### <a name="remarks"></a>备注  
 每当显示工具提示、 使用的颜色绘制和视觉样式`pParams`指定。 值`pParams`存储在受保护成员`m_Params`，重写的派生类来访问它[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)， [CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)， [CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)， [CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)，或[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)维护指定的外观。  
  
## <a name="see-also"></a>请参阅  
 [层次结构图](../../mfc/hierarchy-chart.md)   
 [类](../../mfc/reference/mfc-classes.md)   
 [CToolTipCtrl 类](../../mfc/reference/ctooltipctrl-class.md)   
 [CTooltipManager 类](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipInfo 类](../../mfc/reference/cmfctooltipinfo-class.md)   
 [CWinAppEx 类](../../mfc/reference/cwinappex-class.md)

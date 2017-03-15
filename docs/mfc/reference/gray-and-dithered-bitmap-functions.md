---
title: "灰色和抖色位图函数 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- gray and dithered bitmap functions
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: b8b6f43917dfe211f477b3dde0c94323015d18b2
ms.lasthandoff: 02/24/2017

---
# <a name="gray-and-dithered-bitmap-functions"></a>灰色和抖色位图函数
**灰色位图函数**  
  
 MFC 提供了两个函数为位图提供已禁用控件的外观。  
  
 ![版本灰色与原始图标版本之比较](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
|||  
|-|-|  
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|绘制灰色版本的位图。|  
|[AfxGetGrayBitmap](#afxgetgraybitmap)|复制灰色版本的位图。|  
  
 **抖色的位图函数**  
  
 MFC 还提供了两个函数以将位图背景替换为抖色样式。  
  
 ![抖色与原始图标版本比较](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
|||  
|-|-|  
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|绘制抖色背景位图。|  
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|复制抖色背景位图。|  
  
##  <a name="a-nameafxdrawgraybitmapa--afxdrawgraybitmap"></a><a name="afxdrawgraybitmap"></a>AfxDrawGrayBitmap  
 绘制灰色版本的位图。  
  
```   
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>参数  
 `pDC`  
 指向目标值 DC 的指针。  
  
 *x*  
 目标 x 坐标。  
  
 *y*  
 目标 y 坐标。  
  
 `rSrc`  
 源位图。  
  
 `crBackground`  
 新背景色（通常为灰色，如 COLOR_MENU）。  
  
### <a name="remarks"></a>备注  
 使用 `AfxDrawGrayBitmap` 绘制的位图将具有禁用控件的外观。  
  
 ![版本灰色与原始图标版本之比较](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCDocView #&191;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]  

### <a name="requirements"></a>要求  
 **标头:** afxwin.h  

##  <a name="a-nameafxgetgraybitmapa--afxgetgraybitmap"></a><a name="afxgetgraybitmap"></a>AfxGetGrayBitmap  
 复制灰色版本的位图。  
  
```   
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>参数  
 `rSrc`  
 源位图。  
  
 `pDest`  
 目标位图。  
  
 `crBackground`  
 新背景色（通常为灰色，如 COLOR_MENU）。  
  
### <a name="remarks"></a>备注  
 使用 `AfxGetGrayBitmap` 复制的位图将具有禁用控件的外观。  
  
 ![版本灰色与原始图标版本之比较](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCDocView #&193;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]  

### <a name="requirements"></a>要求  
 **标头:** afxwin.h  
  
##  <a name="a-nameafxdrawditheredbitmapa--afxdrawditheredbitmap"></a><a name="afxdrawditheredbitmap"></a>AfxDrawDitheredBitmap  
 绘制位图，并将其背景替换为递色 （棋盘格） 图案。  
  
```   
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>参数  
 `pDC`  
 指向目标值 DC 的指针。  
  
 *x*  
 目标 x 坐标。  
  
 *y*  
 目标 y 坐标。  
  
 `rSrc`  
 源位图。  
  
 `cr1`  
 两种递色中的一种，通常为白色。  
  
 `cr2`  
 另一种递色，通常为浅灰色 (COLOR_MENU)。  
  
### <a name="remarks"></a>备注  
 在具有两种颜色的目的地 DC 上绘制的源位图 (`cr1`和`cr2`) 棋盘格的图案替换位图的背景。 根据定义，源位图的背景指的是指位图的白色像素以及与位图左上角的像素颜色匹配的所有像素。  
  
 ![抖色与原始图标版本比较](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCDocView #&190;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]  

### <a name="requirements"></a>要求  
 **标头:** afxwin.h  


##  <a name="a-nameafxgetditheredbitmapa--afxgetditheredbitmap"></a><a name="afxgetditheredbitmap"></a>AfxGetDitheredBitmap  
 复制位图，并将其背景替换为递色（棋盘格）图案。  
  
```   
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>参数  
 `rSrc`  
 源位图。  
  
 `pDest`  
 目标位图。  
  
 `cr1`  
 两种递色中的一种，通常为白色。  
  
 `cr2`  
 另一种递色，通常为浅灰色 (COLOR_MENU)。  
  
### <a name="remarks"></a>备注  
 源位图复制到目标位图，并使用两种颜色 (`cr1`和`cr2`) 棋盘格的图案替换源位图的背景。 根据定义，源位图的背景指的是指位图的白色像素以及与位图左上角的像素颜色匹配的所有像素。  
  
 ![抖色与原始图标版本比较](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCDocView #&192;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]  

### <a name="requirements"></a>要求  
 **标头:** afxwin.h  
  
## <a name="see-also"></a>另请参阅  
 [宏和全局函数](../../mfc/reference/mfc-macros-and-globals.md)

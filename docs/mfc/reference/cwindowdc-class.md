---
title: "CWindowDC 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
dev_langs: C++
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9bc3219ff6570fab18b19f350f7dca3171ab4832
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="cwindowdc-class"></a>CWindowDC 类
从 `CDC`派生。  
  
## <a name="syntax"></a>语法  
  
```  
class CWindowDC : public CDC  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CWindowDC::CWindowDC](#cwindowdc)|构造 `CWindowDC` 对象。|  
  
### <a name="protected-data-members"></a>受保护的数据成员  
  
|name|描述|  
|----------|-----------------|  
|[CWindowDC::m_hWnd](#m_hwnd)|`HWND`此`CWindowDC`附加。|  
  
## <a name="remarks"></a>备注  
 调用 Windows 函数[GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx)在构造时和[ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx)在析构时。 这意味着，`CWindowDC`对象访问的整个屏幕区域[CWnd](../../mfc/reference/cwnd-class.md) （客户端和非工作区）。  
  
 有关详细信息使用`CWindowDC`，请参阅[设备上下文](../../mfc/device-contexts.md)。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## <a name="requirements"></a>惠?  
 标头： afxwin.h  
  
##  <a name="cwindowdc"></a>CWindowDC::CWindowDC  
 构造`CWindowDC`访问的整个屏幕区域 （客户端和非工作） 的对象`CWnd`指向对象`pWnd`。  
  
```  
explicit CWindowDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>参数  
 `pWnd`  
 窗口设备上下文对象将访问其工作区中。  
  
### <a name="remarks"></a>备注  
 构造函数调用 Windows 函数[GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947)。  
  
 异常 (类型的`CResourceException`) 如果则会引发 Windows`GetWindowDC`调用将失败。 设备上下文可能不可用，如果 Windows 已分配所有可用的设备上下文。 你的应用程序竞争可用在任何给定时间在 Windows 下的五个常见显示上下文。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CWindowDC::m_hWnd  
 `HWND`的`CWnd`指针用于构造`CWindowDC`对象。  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>备注  
 `m_hWnd`是一个受保护的类型变量`HWND`。  
  
### <a name="example"></a>示例  
  请参阅示例[CWindowDC::CWindowDC](#cwindowdc)。  
  
## <a name="see-also"></a>请参阅  
 [CDC 类](../../mfc/reference/cdc-class.md)   
 [层次结构图](../../mfc/hierarchy-chart.md)   
 [CDC 类](../../mfc/reference/cdc-class.md)

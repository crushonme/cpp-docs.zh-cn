---
title: "COleChangeSourceDialog 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
dev_langs: C++
helpviewer_keywords:
- COleChangeSourceDialog [MFC], COleChangeSourceDialog
- COleChangeSourceDialog [MFC], DoModal
- COleChangeSourceDialog [MFC], GetDisplayName
- COleChangeSourceDialog [MFC], GetFileName
- COleChangeSourceDialog [MFC], GetFromPrefix
- COleChangeSourceDialog [MFC], GetItemName
- COleChangeSourceDialog [MFC], GetToPrefix
- COleChangeSourceDialog [MFC], IsValidSource
- COleChangeSourceDialog [MFC], m_cs
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a9eccd25a175479c18a83b5d6ab96753a946e386
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="colechangesourcedialog-class"></a>COleChangeSourceDialog 类
用于 OLE“更改源”对话框。  
  
## <a name="syntax"></a>语法  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|构造 `COleChangeSourceDialog` 对象。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[COleChangeSourceDialog::DoModal](#domodal)|OLE 更改源对话框中显示。|  
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|获取完整的源的显示名称。|  
|[COleChangeSourceDialog::GetFileName](#getfilename)|源名称中获取文件名。|  
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|获取上一个源的前缀。|  
|[COleChangeSourceDialog::GetItemName](#getitemname)|源名称中获取的项名称。|  
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|获取新的源的前缀|  
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|指示源是否有效。|  
  
### <a name="public-data-members"></a>公共数据成员  
  
|名称|描述|  
|----------|-----------------|  
|[COleChangeSourceDialog::m_cs](#m_cs)|结构，它控制的对话框中的行为。|  
  
## <a name="remarks"></a>备注  
 创建类的对象`COleChangeSourceDialog`如果想要调用此对话框。 后`COleChangeSourceDialog`构造对象，则可以使用[m_cs](#m_cs)结构初始化的值或在对话框中的控件的状态。 `m_cs`结构属于类型[OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)。 有关使用此对话框类的详细信息，请参阅[DoModal](#domodal)成员函数。  
  
 有关详细信息，请参阅[OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK 中的结构。  
  
 关于 OLE 特定对话框的详细信息，请参阅文章[OLE 中的对话框](../../mfc/dialog-boxes-in-ole.md)。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## <a name="requirements"></a>惠?  
 **标头：** afxodlgs.h  
  
##  <a name="colechangesourcedialog"></a>COleChangeSourceDialog::COleChangeSourceDialog  
 此函数构造`COleChangeSourceDialog`对象。  
  
```  
explicit COleChangeSourceDialog(
    COleClientItem* pItem,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>参数  
 `pItem`  
 指向链接[COleClientItem](../../mfc/reference/coleclientitem-class.md)其源是要更新。  
  
 `pParentWnd`  
 指向父或所有者窗口对象 (类型的`CWnd`) 对话框对象所属。 如果它是**NULL**，对话框中的父窗口将设置为应用程序主窗口。  
  
### <a name="remarks"></a>备注  
 若要显示对话框中，调用[DoModal](#domodal)函数。  
  
 有关详细信息，请参阅[OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)结构和[OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) Windows SDK 中的函数。  
  
##  <a name="domodal"></a>COleChangeSourceDialog::DoModal  
 调用此函数可显示 OLE 更改源对话框。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>返回值  
 对话框中的完成状态。 以下值之一：  
  
- **IDOK**如果成功显示该对话框。  
  
- **IDCANCEL**如果用户已取消对话框。  
  
- **IDABORT**如果发生错误。 如果**IDABORT**是返回，调用[COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)成员函数以获取有关发生的错误类型详细信息。 有关可能的错误的列表，请参阅[OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) Windows SDK 中的函数。  
  
### <a name="remarks"></a>备注  
 如果你想要通过设置成员的初始化各种对话框控件[m_cs](#m_cs)结构，应执行此操作，然后再调`DoModal`，但在构造对话框对象之后。  
  
 如果`DoModal`返回**IDOK**，可调用成员函数来从对话框中检索用户输入的设置或信息。 以下列表命名了典型查询函数：  
  
- [GetFileName](#getfilename)  
  
- [GetDisplayName](#getdisplayname)  
  
- [GetItemName](#getitemname)  
  
##  <a name="getdisplayname"></a>COleChangeSourceDialog::GetDisplayName  
 调用此函数可检索链接的客户端项的完整显示名称。  
  
```  
CString GetDisplayName();
```  
  
### <a name="return-value"></a>返回值  
 完整源显示名称 (moniker) [COleClientItem](../../mfc/reference/coleclientitem-class.md)构造函数中指定。  
  
##  <a name="getfilename"></a>COleChangeSourceDialog::GetFileName  
 调用此函数可检索链接的客户端项的显示名称的文件标记部分。  
  
```  
CString GetFileName();
```  
  
### <a name="return-value"></a>返回值  
 源显示名称的文件标记部分[COleClientItem](../../mfc/reference/coleclientitem-class.md)构造函数中指定。  
  
### <a name="remarks"></a>备注  
 项名字对象以及文件名字对象提供完整的显示名称。  
  
##  <a name="getfromprefix"></a>COleChangeSourceDialog::GetFromPrefix  
 调用此函数可获取源的以前的前缀字符串。  
  
```  
CString GetFromPrefix();
```  
  
### <a name="return-value"></a>返回值  
 以前的源的前缀字符串。  
  
### <a name="remarks"></a>备注  
 调用此函数后，才[DoModal](#domodal)返回**IDOK**。  
  
 此值是直接来自**lpszFrom**的成员[OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)结构。  
  
 有关详细信息，请参阅[OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK 中的结构。  
  
##  <a name="getitemname"></a>COleChangeSourceDialog::GetItemName  
 调用此函数可检索链接的客户端项的显示名称的项标记部分。  
  
```  
CString GetItemName();
```  
  
### <a name="return-value"></a>返回值  
 源显示名称的项标记部分[COleClientItem](../../mfc/reference/coleclientitem-class.md)构造函数中指定。  
  
### <a name="remarks"></a>备注  
 项名字对象以及文件名字对象提供完整的显示名称。  
  
##  <a name="gettoprefix"></a>COleChangeSourceDialog::GetToPrefix  
 调用此函数可获取新的前缀字符串的源。  
  
```  
CString GetToPrefix();
```  
  
### <a name="return-value"></a>返回值  
 新的源的前缀字符串。  
  
### <a name="remarks"></a>备注  
 调用此函数后，才[DoModal](#domodal)返回**IDOK**。  
  
 此值是直接来自**lpszTo**的成员[OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)结构。  
  
 有关详细信息，请参阅[OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK 中的结构。  
  
##  <a name="m_cs"></a>COleChangeSourceDialog::m_cs  
 此数据成员是类型的结构[OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)。  
  
```  
OLEUICHANGESOURCE m_cs;  
```  
  
### <a name="remarks"></a>备注  
 `OLEUICHANGESOURCE`用于控制 OLE 更改源对话框中的行为。 此结构的成员可以直接修改。  
  
 有关详细信息，请参阅[OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK 中的结构。  
  
##  <a name="isvalidsource"></a>COleChangeSourceDialog::IsValidSource  
 调用此函数可确定新的源是否有效。  
  
```  
BOOL IsValidSource();
```  
  
### <a name="return-value"></a>返回值  
 非零，如果新的源是有效的否则为 0。  
  
### <a name="remarks"></a>备注  
 调用此函数后，才[DoModal](#domodal)返回**IDOK**。  
  
 有关详细信息，请参阅[OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK 中的结构。  
  
## <a name="see-also"></a>请参阅  
 [COleDialog 类](../../mfc/reference/coledialog-class.md)   
 [层次结构图](../../mfc/hierarchy-chart.md)   
 [COleDialog 类](../../mfc/reference/coledialog-class.md)

---
title: "COleUpdateDialog 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleUpdateDialog
dev_langs:
- C++
helpviewer_keywords:
- Update dialog
- links [C++], updating
- updating OLE links
- OLE dialog boxes, Edit Link
- OLE link updating
- COleUpdateDialog class
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 8066a8dc9e572c14e9423af62d340e249351ac11
ms.lasthandoff: 02/24/2017

---
# <a name="coleupdatedialog-class"></a>COleUpdateDialog 类
用于 OLE“编辑链接”对话框的特例，当你只需要更新文档中现有的链接对象或嵌入对象时才可使用。  
  
## <a name="syntax"></a>语法  
  
```  
class COleUpdateDialog : public COleLinksDialog  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|说明|  
|----------|-----------------|  
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|构造 `COleUpdateDialog` 对象。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|说明|  
|----------|-----------------|  
|[COleUpdateDialog::DoModal](#domodal)|显示**编辑链接**在更新模式下的对话框。|  
  
## <a name="remarks"></a>备注  
 有关特定于 OLE 的对话框的详细信息，请参阅文章[OLE 中的对话框](../../mfc/dialog-boxes-in-ole.md)。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
 `COleUpdateDialog`  
  
## <a name="requirements"></a>要求  
 **标头︰** afxodlgs.h  
  
##  <a name="a-namecoleupdatedialoga--coleupdatedialogcoleupdatedialog"></a><a name="coleupdatedialog"></a>COleUpdateDialog::COleUpdateDialog  
 构造 `COleUpdateDialog` 对象。  
  
```  
explicit COleUpdateDialog(
    COleDocument* pDoc,  
    BOOL bUpdateLinks = TRUE,  
    BOOL bUpdateEmbeddings = FALSE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>参数  
 `pDoc`  
 指向包含可能需要更新的链接的文档。  
  
 *bUpdateLinks*  
 确定是否要更新链接的对象的标志。  
  
 *bUpdateEmbeddings*  
 确定是否要更新嵌入的对象的标志。  
  
 `pParentWnd`  
 指向父或所有者窗口对象 (类型的`CWnd`) 对话框对象所属。 如果它是**NULL**，对话框中的父窗口都将设置为主应用程序窗口中。  
  
### <a name="remarks"></a>备注  
 此函数只构造`COleUpdateDialog`对象。 若要显示对话框中，调用[DoModal](../../mfc/reference/colelinksdialog-class.md#domodal)。 此类应使用而不是`COleLinksDialog`如果想要更新仅现有链接项或嵌入项。  
  
##  <a name="a-namedomodala--coleupdatedialogdomodal"></a><a name="domodal"></a>COleUpdateDialog::DoModal  
 编辑链接对话框框中显示更新模式。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>返回值  
 对话框中的完成状态。 以下值之一：  
  
- **IDOK**如果成功返回对话框。  
  
- **IDCANCEL**如果无当前文档中的链接或嵌入项需要更新。  
  
- **IDABORT**是否发生了错误。 如果**IDABORT**是返回，调用[COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)成员函数以获取有关发生的错误类型的详细信息。 有关可能出现的错误的列表，请参阅[OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) ，此功能在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="remarks"></a>备注  
 用户未选择取消按钮，将更新所有链接和/或嵌入。  
  
## <a name="see-also"></a>另请参阅  
 [MFC 示例 OCLIENT](../../visual-cpp-samples.md)   
 [COleLinksDialog 类](../../mfc/reference/colelinksdialog-class.md)   
 [层次结构图](../../mfc/hierarchy-chart.md)   
 [COleLinksDialog 类](../../mfc/reference/colelinksdialog-class.md)

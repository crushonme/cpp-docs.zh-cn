---
title: "COleControlSite 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleControlSite
dev_langs:
- C++
helpviewer_keywords:
- COleControlSite class
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9bae18342fe5f6aeac939c854f578cf47636fa63
ms.lasthandoff: 02/24/2017

---
# <a name="colecontrolsite-class"></a>COleControlSite 类
提供自定义客户端控件接口支持。  
  
## <a name="syntax"></a>语法  
  
```  
class COleControlSite : public CCmdTarget  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|说明|  
|----------|-----------------|  
|[COleControlSite::COleControlSite](#colecontrolsite)|构造 `COleControlSite` 对象。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|说明|  
|----------|-----------------|  
|[COleControlSite::BindDefaultProperty](#binddefaultproperty)|将所承载的控件的默认属性绑定到数据源。|  
|[COleControlSite::BindProperty](#bindproperty)|将所承载的控件属性绑定到数据源。|  
|[COleControlSite::CreateControl](#createcontrol)|创建托管的 ActiveX 控件。|  
|[COleControlSite::DestroyControl](#destroycontrol)|销毁所承载的控件。|  
|[COleControlSite::DoVerb](#doverb)|执行所承载控件的指定的动词。|  
|[COleControlSite::EnableDSC](#enabledsc)|使数据源控件站点。|  
|[COleControlSite::EnableWindow](#enablewindow)|使控件站点。|  
|[COleControlSite::FreezeEvents](#freezeevents)|指定控件所在位置接受事件。|  
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|检索所承载的控件的默认按钮代码。|  
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|检索控件的标识符。|  
|[COleControlSite::GetEventIID](#geteventiid)|检索用于托管控件的事件接口的 ID。|  
|[COleControlSite::GetExStyle](#getexstyle)|检索控件所在位置的扩展的样式。|  
|[COleControlSite::GetProperty](#getproperty)|检索所承载的控件的特定属性。|  
|[COleControlSite::GetStyle](#getstyle)|检索控件所在位置的样式。|  
|[COleControlSite::GetWindowText](#getwindowtext)|检索所承载的控件的文本。|  
|[COleControlSite::InvokeHelper](#invokehelper)|调用所承载的控件的特定方法。|  
|[COleControlSite::InvokeHelperV](#invokehelperv)|调用和参数的变量列表所承载的控件的特定方法。|  
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|确定控件是否为窗口中的默认按钮。|  
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|检查控件所在位置的可见状态。|  
|[COleControlSite::ModifyStyle](#modifystyle)|修改当前扩展样式的控件站点。|  
|[COleControlSite::ModifyStyleEx](#modifystyleex)|修改控件站点的当前样式。|  
|[COleControlSite::MoveWindow](#movewindow)|更改控件所在的位置。|  
|[COleControlSite::QuickActivate](#quickactivate)|快速激活所承载的控件。|  
|[COleControlSite::SafeSetProperty](#safesetproperty)|设置的属性或方法的控件而不会引发异常的机会。|  
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|在窗口中设置的默认按钮。|  
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|检索控件的标识符。|  
|[COleControlSite::SetFocus](#setfocus)|将焦点设置到控件站点。|  
|[COleControlSite::SetProperty](#setproperty)|设置托管控件的特定属性。|  
|[COleControlSite::SetPropertyV](#setpropertyv)|设置托管控件的特定属性和参数的变量列表。|  
|[COleControlSite::SetWindowPos](#setwindowpos)|设置控件所在的位置。|  
|[COleControlSite::SetWindowText](#setwindowtext)|设置托管控件的文本。|  
|[COleControlSite::ShowWindow](#showwindow)|显示或隐藏控件站点。|  
  
### <a name="protected-methods"></a>受保护的方法  
  
|名称|描述|  
|----------|-----------------|  
|[COleControlSite::GetControlInfo](#getcontrolinfo)|检索键盘信息和用于承载控件的助记键。|  
  
### <a name="public-data-members"></a>公共数据成员  
  
|名称|说明|  
|----------|-----------------|  
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|确定所承载的控件是否是无窗口控件。|  
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|包含处理控件的键盘上的信息。|  
|[COleControlSite::m_dwEventSink](#m_dweventsink)|控件的连接点的 cookie。|  
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|所承载的控件杂项状态。|  
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|`IPropertyNotifySink`控件的 cookie。|  
|[COleControlSite::m_dwStyle](#m_dwstyle)|所承载控件的样式。|  
|[COleControlSite::m_hWnd](#m_hwnd)|控件所在位置的句柄。|  
|[COleControlSite::m_iidEvents](#m_iidevents)|所承载的控件的事件接口 ID。|  
|[COleControlSite::m_nID](#m_nid)|所承载控件的 ID。|  
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|一个指向`IOleInPlaceActiveObject`所承载控件的对象。|  
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|所承载控件的容器。|  
|[COleControlSite::m_pInPlaceObject](#m_pinplaceobject)|一个指向`IOleInPlaceObject`所承载控件的对象。|  
|[COleControlSite::m_pObject](#m_pobject)|一个指向`IOleObjectInterface`控件的接口。|  
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|一个指向`IOleInPlaceObjectWindowless`控件的接口。|  
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|指向所承载的控件的窗口对象的指针。|  
|[COleControlSite::m_rect](#m_rect)|控件所在位置的尺寸。|  
  
## <a name="remarks"></a>备注  
 此支持是嵌入的 ActiveX 控件获取有关位置和其显示的站点、 其名字对象，其用户界面、 其环境属性和提供其容器的其他资源的范围信息的主要方式。 `COleControlSite`完全实现[IOleControlSite](http://msdn.microsoft.com/library/windows/desktop/ms688502)， [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586)， [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706)， [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)， **IBoundObjectSite**， **INotifyDBEvents**， [IRowSetNotify](../../data/oledb/irowsetnotifyimpl-class.md)接口。 此外，还实现 IDispatch 接口 （提供对环境属性和事件接收器的支持）。  
  
 若要创建 ActiveX 控件站点使用`COleControlSite`，从派生类`COleControlSite`。 在您`CWnd`的容器 （例如，您对话框中） 的派生的类重写**CWnd::CreateControlSite**函数。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlSite`  
  
## <a name="requirements"></a>要求  
 **标头︰** afxocc.h  
  
##  <a name="a-namebinddefaultpropertya--colecontrolsitebinddefaultproperty"></a><a name="binddefaultproperty"></a>COleControlSite::BindDefaultProperty  
 将调用对象的默认简单绑定的属性，作为类型库中的标记绑定到基础数据源控件的数据源、 用户名、 密码和 SQL 属性定义的游标。  
  
```  
virtual void BindDefaultProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    LPCTSTR szFieldName,  
    CWnd* pDSCWnd);
```  
  
### <a name="parameters"></a>参数  
 `dwDispID`  
 指定**DISPID**上要绑定到数据源控件的数据绑定控件的属性。  
  
 `vtProp`  
 指定要绑定的属性的类型 — 例如， `VT_BSTR`， **VT_VARIANT**，依次类推。  
  
 `szFieldName`  
 该属性将绑定到该数据源控件提供的游标中指定的列的名称。  
  
 `pDSCWnd`  
 一个指向`CWnd`-承载数据源控件的属性将绑定到的派生的对象。  
  
### <a name="remarks"></a>备注  
 `CWnd`对象对其调用此函数必须是数据绑定控件。  
  
##  <a name="a-namebindpropertya--colecontrolsitebindproperty"></a><a name="bindproperty"></a>COleControlSite::BindProperty  
 将调用对象的简单绑定的属性，作为类型库中的标记绑定到基础数据源控件的数据源、 用户名、 密码和 SQL 属性定义的游标。  
  
```  
virtual void BindProperty(
    DISPID dwDispId,  
    CWnd* pWndDSC);
```  
  
### <a name="parameters"></a>参数  
 *dwDispId*  
 指定**DISPID**上要绑定到数据源控件的数据绑定控件的属性。  
  
 `pWndDSC`  
 一个指向`CWnd`-承载数据源控件的属性将绑定到的派生的对象。  
  
### <a name="remarks"></a>备注  
 `CWnd`对象对其调用此函数必须是数据绑定控件。  
  
##  <a name="a-namecolecontrolsitea--colecontrolsitecolecontrolsite"></a><a name="colecontrolsite"></a>COleControlSite::COleControlSite  
 构造一个新`COleControlSite`对象。  
  
```  
explicit COleControlSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>参数  
 `pCtrlCont`  
 指向控件的容器 （这表示承载 AtiveX 控件的窗口） 的指针。  
  
### <a name="remarks"></a>备注  
 调用此函数[COccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer)函数。 有关自定义创建的容器的详细信息，请参阅[COccManager::CreateSite](../../mfc/reference/coccmanager-class.md#createsite)。  
  
##  <a name="a-namecreatecontrola--colecontrolsitecreatecontrol"></a><a name="createcontrol"></a>COleControlSite::CreateControl  
 创建 ActiveX 控件，由托管`COleControlSite`对象。  
  
```  
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    UINT nID,  
    CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL);

 
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const POINT* ppt,  
    const SIZE* psize,  
    UINT nID,  
    CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>参数  
 `pWndCtrl`  
 指向表示控件的窗口对象的指针。  
  
 `clsid`  
 控件的唯一类 ID。  
  
 `lpszWindowName`  
 指向要在控件中显示的文本指针。 设置 winodw Caption 或 Text 属性的值 （如果有）。  
  
 `dwStyle`  
 窗口样式。 下列出的可用样式**备注**部分。  
  
 `rect`  
 指定控件的大小和位置。 它可为`CRect`对象或`RECT`结构。  
  
 `nID`  
 指定控件的子窗口 id。  
  
 `pPersist`  
 一个指向`CFile`包含该控件的持久状态。 默认值是**NULL**，指示该控件而不还原其状态从任何持久性存储区初始化自身。 如果不是**NULL**，它应为一个指向`CFile`-派生的对象，它包含控件的持久性数据的流或存储形式。 无法在客户端上一个激活过程中保存此数据。 `CFile`可以包含其他数据，但必须具有它在调用的时间设置为持久性数据的第一个字节的读写指针`CreateControl`。  
  
 `bStorage`  
 指示是否在数据`pPersist`应解释为`IStorage`或`IStream`数据。 如果在数据`pPersist`是一种存储，`bStorage`应**TRUE**。 如果在数据`pPersist`是一个流`bStorage`应**FALSE**。 默认值是**FALSE**。  
  
 `bstrLicKey`  
 可选的许可证密钥数据。 仅用于创建需要运行时许可证密钥的控件需要此数据。 如果该控件支持授权，则必须提供创建控件以成功的许可密钥。 默认值是**NULL**。  
  
 `ppt`  
 一个指向**点**结构，其中包含该控件的左上角。 控件的大小由值*psize*。 `ppt`和*psize*值是一种可选方法指定大小和位置 opf 控件。  
  
 *psize*  
 一个指向**大小**结构，其中包含该控件的大小。 窗口左上角的值由`ppt`。 `ppt`和*psize*值是一种可选方法指定大小和位置 opf 控件。  
  
### <a name="return-value"></a>返回值  
 标准 `HRESULT` 值。  
  
### <a name="remarks"></a>备注  
 Windows 的一个子集`dwStyle`支持标志`CreateControl`:  
  
- **WS_VISIBLE**创建初始可见的窗口。 如果您希望控件立即，像普通窗口可见，则必须填写。  
  
- **WS_DISABLED**创建最初处于禁用状态的窗口。 禁用的窗口无法从用户接收输入。 如果该控件具有 Enabled 属性可以设置。  
  
- `WS_BORDER`使用细线边框创建窗口。 如果控件具有 borderstyle 属性可以设置。  
  
- **WS_GROUP**指定一组控件的第一个控件。 用户可以通过使用箭头键键盘焦点从一个控件组中更改为下一步。 使用定义的所有控件**WS_GROUP**样式后的第一个控件属于同一个组。 使用下一个控件**WS_GROUP**样式组结束和开始下一个组。  
  
- **WS_TABSTOP**指定当用户按 TAB 键可以接收键盘焦点的控件。 按 TAB 键将键盘焦点更改到下一个控件的**WS_TABSTOP**样式。  
  
 使用第二个重载以创建默认大小的控件。  
  
##  <a name="a-namedestroycontrola--colecontrolsitedestroycontrol"></a><a name="destroycontrol"></a>COleControlSite::DestroyControl  
 销毁`COleControlSite`对象。  
  
```  
virtual BOOL DestroyControl();
```  
  
### <a name="return-value"></a>返回值  
 非零，如果成功，否则为 0。  
  
### <a name="remarks"></a>备注  
 一旦完成，该对象从内存中释放，且任何指向对象不再有效。  
  
##  <a name="a-namedoverba--colecontrolsitedoverb"></a><a name="doverb"></a>COleControlSite::DoVerb  
 执行指定的谓词。  
  
```  
virtual HRESULT DoVerb(
    LONG nVerb,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>参数  
 `nVerb`  
 指定要执行的谓词。 它可以包括以下项之一︰  
  
|值|含义|符号|  
|-----------|-------------|------------|  
|0|主谓词|`OLEIVERB_PRIMARY`|  
|-1|次要谓词|（无）|  
|1|显示要编辑的对象。|`OLEIVERB_SHOW`|  
|-2|编辑一个单独的窗口中的项。|`OLEIVERB_OPEN`|  
|-3|隐藏对象。|`OLEIVERB_HIDE`|  
|-4|控件被就地激活。|`OLEIVERB_UIACTIVATE`|  
|-5|控件被就地激活，而无需附加用户界面元素。|**OLEIVERB_INPLACEACTIVATE**|  
|-7|显示控件的属性。|**OLEIVERB_PROPERTIES**|  
  
 `lpMsg`  
 指针，指向导致要激活的项的消息。  
  
### <a name="return-value"></a>返回值  
 标准 `HRESULT` 值。  
  
### <a name="remarks"></a>备注  
 通过控件的直接调用此函数`IOleObject`接口，以执行指定的谓词。 如果此函数调用后，引发了异常`HRESULT`返回错误代码。  
  
 有关详细信息，请参阅[IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="a-nameenabledsca--colecontrolsiteenabledsc"></a><a name="enabledsc"></a>COleControlSite::EnableDSC  
 使数据源控件站点。  
  
```  
virtual void EnableDSC();
```  
  
### <a name="remarks"></a>备注  
 由框架来启用和初始化数据源控件所在位置调用。 重写此函数可提供自定义的行为。  
  
##  <a name="a-nameenablewindowa--colecontrolsiteenablewindow"></a><a name="enablewindow"></a>COleControlSite::EnableWindow  
 启用或禁用鼠标和键盘输入到控件站点。  
  
```  
virtual BOOL EnableWindow(BOOL bEnable);
```  
  
### <a name="parameters"></a>参数  
 `bEnable`  
 指定是启用还是禁用窗口︰ **TRUE**窗口输入是若要启用，否则如果**FALSE**。  
  
### <a name="return-value"></a>返回值  
 非零，如果以前禁用窗口中，否则为 0。  
  
##  <a name="a-namefreezeeventsa--colecontrolsitefreezeevents"></a><a name="freezeevents"></a>COleControlSite::FreezeEvents  
 指定控件所在位置是否将处理或忽略从另一控件激发的事件。  
  
```  
void FreezeEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>参数  
 `bFreeze`  
 指定控件所在位置是否希望停止接受事件。 如果该控件不接受事件，则非零值否则为零。  
  
### <a name="remarks"></a>备注  
 如果`bFreeze`是**TRUE**，控制站点请求要停止 fring 事件的控件。 如果`bFreeze`是**FALSE**，控制站点请求要继续激发事件的控件。  
  
> [!NOTE]
>  该控件不需要停止激发事件，如果请求控件站点。 它可以继续激发，但是控件所在位置时将忽略所有后续事件。  
  
##  <a name="a-namegetcontrolinfoa--colecontrolsitegetcontrolinfo"></a><a name="getcontrolinfo"></a>COleControlSite::GetControlInfo  
 检索有关控件的键盘助记键和键盘行为的信息。  
  
```  
void GetControlInfo();
```  
  
### <a name="remarks"></a>备注  
 信息存储在[COleControlSite::m_ctlInfo](#m_ctlinfo)。  
  
##  <a name="a-namegetdefbtncodea--colecontrolsitegetdefbtncode"></a><a name="getdefbtncode"></a>COleControlSite::GetDefBtnCode  
 确定控件是否为默认按钮。  
  
```  
DWORD GetDefBtnCode();
```  
  
### <a name="return-value"></a>返回值  
 可以是以下值之一：  
  
- **DLGC_DEFPUSHBUTTON**控件是在对话框中的默认按钮。  
  
- **DLGC_UNDEFPUSHBUTTON**控件不是对话框中的默认按钮。  
  
- **0**控件不是一个按钮。  
  
##  <a name="a-namegetdlgctrlida--colecontrolsitegetdlgctrlid"></a><a name="getdlgctrlid"></a>COleControlSite::GetDlgCtrlID  
 检索控件的标识符。  
  
```  
virtual int GetDlgCtrlID() const;  
```  
  
### <a name="return-value"></a>返回值  
 控件的对话框项标识符。  
  
##  <a name="a-namegeteventiida--colecontrolsitegeteventiid"></a><a name="geteventiid"></a>COleControlSite::GetEventIID  
 检索指向控件的默认事件接口的指针。  
  
```  
BOOL GetEventIID(IID* piid);
```  
  
### <a name="parameters"></a>参数  
 `piid`  
 一个指向接口 id。  
  
### <a name="return-value"></a>返回值  
 非零，如果成功，否则为 0。 如果成功，`piid`包含控件的默认事件接口的接口 ID。  
  
##  <a name="a-namegetexstylea--colecontrolsitegetexstyle"></a><a name="getexstyle"></a>COleControlSite::GetExStyle  
 检索窗口的扩展的样式。  
  
```  
virtual DWORD GetExStyle() const;  
```  
  
### <a name="return-value"></a>返回值  
 控制窗口的扩展样式。  
  
### <a name="remarks"></a>备注  
 若要检索的常规样式，请调用[COleControlSite::GetStyle](#getstyle)。  
  
##  <a name="a-namegetpropertya--colecontrolsitegetproperty"></a><a name="getproperty"></a>COleControlSite::GetProperty  
 获取由指定的控件属性`dwDispID`。  
  
```  
virtual void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>参数  
 `dwDispID`  
 标识查找控件的默认设置的属性的调度 ID`IDispatch`接口来检索。  
  
 `vtProp`  
 指定要检索的属性的类型。 有关可能的值，请参阅备注部分[COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)。  
  
 `pvProp`  
 将接收的属性值的变量的地址。 它必须与指定的类型匹配`vtProp`。  
  
### <a name="remarks"></a>备注  
 通过返回的值`pvProp`。  
  
##  <a name="a-namegetstylea--colecontrolsitegetstyle"></a><a name="getstyle"></a>COleControlSite::GetStyle  
 检索控件所在位置的样式。  
  
```  
virtual DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>返回值  
 窗口的样式。  
  
### <a name="remarks"></a>备注  
 有关可能的值的列表，请参阅[Windows 样式](../../mfc/reference/window-styles.md)。 若要检索控件所在位置的扩展的样式，请调用[COleControlSite::GetExStyle](#getexstyle)。  
  
##  <a name="a-namegetwindowtexta--colecontrolsitegetwindowtext"></a><a name="getwindowtext"></a>COleControlSite::GetWindowText  
 检索控件的当前文本。  
  
```  
virtual void GetWindowText(CString& str) const;  
```  
  
### <a name="parameters"></a>参数  
 `str`  
 对引用`CString`对象，其中包含该控件的当前文本。  
  
### <a name="remarks"></a>备注  
 如果该控件支持标题常用属性，则返回此值。 如果不支持标题常用属性，则返回的 Text 属性的值。  
  
##  <a name="a-nameinvokehelpera--colecontrolsiteinvokehelper"></a><a name="invokehelper"></a>COleControlSite::InvokeHelper  
 调用方法或属性指定`dwDispID`，通过指定的上下文中`wFlags`。  
  
```  
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>参数  
 `dwDispID`  
 标识属性或方法，在该控件上找到的调度 ID`IDispatch`接口，以调用。  
  
 `wFlags`  
 描述对 idispatch:: Invoke 的调用的上下文的标志。 以尽可能高`wFlags`值，请参阅`IDispatch::Invoke`中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `vtRet`  
 指定返回值的类型。 有关可能的值，请参阅备注部分[COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)。  
  
 `pvRet`  
 将接收属性值或返回值的变量的地址。 它必须与 `vtRet`指定的类型匹配。  
  
 `pbParamInfo`  
 指向以 null 结尾的字符串的指针，该字符串由指定 `pbParamInfo`后面的参数类型的字节组成。 有关可能的值，请参阅备注部分[COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)。  
  
 *...*  
 具有 `pbParamInfo`中指定的类型的参数的变量列表。  
  
### <a name="remarks"></a>备注  
 `pbParamInfo` 参数指定传递到方法或属性的参数的类型。 变量参数列表是由表示...语法声明中。  
  
 此函数将转换的参数**VARIANTARG**值，然后调用**idispatch:: Invoke**在控件上的方法。 如果调用**idispatch:: Invoke**失败，此函数将引发异常。 如果返回状态代码**idispatch:: Invoke**是`DISP_E_EXCEPTION`，此函数将引发**COleDispatchException**对象中，否则为它将引发`COleException`。  
  
##  <a name="a-nameinvokehelperva--colecontrolsiteinvokehelperv"></a><a name="invokehelperv"></a>COleControlSite::InvokeHelperV  
 调用方法或属性指定`dwDispID`，通过指定的上下文中`wFlags`。  
  
```  
virtual void InvokeHelperV(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo,  
    va_list argList);
```  
  
### <a name="parameters"></a>参数  
 `dwDispID`  
 标识属性或方法，在该控件上找到的调度 ID`IDispatch`接口，以调用。  
  
 `wFlags`  
 描述对 idispatch:: Invoke 的调用的上下文的标志。  
  
 `vtRet`  
 指定返回值的类型。 有关可能的值，请参阅备注部分[COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)。  
  
 `pvRet`  
 将接收属性值或返回值的变量的地址。 它必须与 `vtRet`指定的类型匹配。  
  
 `pbParamInfo`  
 指向以 null 结尾的字符串的指针，该字符串由指定 `pbParamInfo`后面的参数类型的字节组成。 有关可能的值，请参阅备注部分[COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)。  
  
 `argList`  
 变量参数列表指向的指针。  
  
### <a name="remarks"></a>备注  
 `pbParamInfo` 参数指定传递到方法或属性的参数的类型。 可以使用传递的方法或属性正在被调用的额外参数*va_list*参数。  
  
 通常情况下，调用此函数`COleControlSite::InvokeHelper`。  
  
##  <a name="a-nameisdefaultbuttona--colecontrolsiteisdefaultbutton"></a><a name="isdefaultbutton"></a>COleControlSite::IsDefaultButton  
 确定控件是否为默认按钮。  
  
```  
BOOL IsDefaultButton();
```  
  
### <a name="return-value"></a>返回值  
 如果该控件为非零默认按钮在窗口上，否则为零。  
  
##  <a name="a-nameiswindowenableda--colecontrolsiteiswindowenabled"></a><a name="iswindowenabled"></a>COleControlSite::IsWindowEnabled  
 确定是否启用控件站点。  
  
```  
virtual BOOL IsWindowEnabled() const;  
```  
  
### <a name="return-value"></a>返回值  
 非零如果已启用该控件，否则为零。  
  
### <a name="remarks"></a>备注  
 从控件的已启用常用属性检索的值。  
  
##  <a name="a-namembiswindowlessa--colecontrolsitembiswindowless"></a><a name="m_biswindowless"></a>COleControlSite::m_bIsWindowless  
 确定对象是否是无窗口控件。  
  
```  
BOOL m_bIsWindowless;  
```  
  
### <a name="remarks"></a>备注  
 非零如果控件具有没有任何窗口，否则为零。  
  
##  <a name="a-namemctlinfoa--colecontrolsitemctlinfo"></a><a name="m_ctlinfo"></a>COleControlSite::m_ctlInfo  
 有关如何由控件处理键盘输入的信息。  
  
```  
CONTROLINFO m_ctlInfo;  
```  
  
### <a name="remarks"></a>备注  
 此信息存储在[CONTROLINFO](http://msdn.microsoft.com/library/windows/desktop/ms680734)结构。  
  
##  <a name="a-namemdweventsinka--colecontrolsitemdweventsink"></a><a name="m_dweventsink"></a>COleControlSite::m_dwEventSink  
 包含从控件的事件接收器的连接点的 cookie。  
  
```  
DWORD m_dwEventSink;  
```  
  
##  <a name="a-namemdwmiscstatusa--colecontrolsitemdwmiscstatus"></a><a name="m_dwmiscstatus"></a>COleControlSite::m_dwMiscStatus  
 包含有关控件的其他信息。  
  
```  
DWORD m_dwMiscStatus;  
```  
  
### <a name="remarks"></a>备注  
 有关详细信息，请参阅[OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="a-namemdwpropnotifysinka--colecontrolsitemdwpropnotifysink"></a><a name="m_dwpropnotifysink"></a>COleControlSite::m_dwPropNotifySink  
 包含[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) cookie。  
  
```  
DWORD m_dwPropNotifySink;  
```  
  
##  <a name="a-namemdwstylea--colecontrolsitemdwstyle"></a><a name="m_dwstyle"></a>COleControlSite::m_dwStyle  
 包含控件的窗口样式。  
  
```  
DWORD m_dwStyle;  
```  
  
##  <a name="a-namemhwnda--colecontrolsitemhwnd"></a><a name="m_hwnd"></a>COleControlSite::m_hWnd  
 包含`HWND`的控件，或**NULL**如果控件处于无窗口。  
  
```  
HWND m_hWnd;  
```  
  
##  <a name="a-namemiideventsa--colecontrolsitemiidevents"></a><a name="m_iidevents"></a>COleControlSite::m_iidEvents  
 包含控件的默认事件接收器接口的接口 ID。  
  
```  
IID m_iidEvents;  
```  
  
##  <a name="a-namemnida--colecontrolsitemnid"></a><a name="m_nid"></a>COleControlSite::m_nID  
 包含控件的对话框项 id。  
  
```  
UINT m_nID;  
```  
  
##  <a name="a-namempactiveobjecta--colecontrolsitempactiveobject"></a><a name="m_pactiveobject"></a>COleControlSite::m_pActiveObject  
 包含[IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299)控件的接口。  
  
```  
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;  
```  
  
##  <a name="a-namempctrlconta--colecontrolsitempctrlcont"></a><a name="m_pctrlcont"></a>COleControlSite::m_pCtrlCont  
 包含控件的容器 （表示该窗体）。  
  
```  
COleControlContainer* m_pCtrlCont;  
```  
  
##  <a name="a-namempinplaceobjecta--colecontrolsitempinplaceobject"></a><a name="m_pinplaceobject"></a>COleControlSite::m_pInPlaceObject  
 包含`IOleInPlaceObject` [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646)控件的接口。  
  
```  
LPOLEINPLACEOBJECT m_pInPlaceObject;  
```  
  
##  <a name="a-namempobjecta--colecontrolsitempobject"></a><a name="m_pobject"></a>COleControlSite::m_pObject  
 包含**IOleObjectInterface**控件的接口。  
  
```  
LPOLEOBJECT m_pObject;  
```  
  
##  <a name="a-namempwindowlessobjecta--colecontrolsitempwindowlessobject"></a><a name="m_pwindowlessobject"></a>COleControlSite::m_pWindowlessObject  
 包含`IOleInPlaceObjectWindowless` [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304)控件的接口。  
  
```  
IOleInPlaceObjectWindowless* m_pWindowlessObject;  
```  
  
##  <a name="a-namempwndctrla--colecontrolsitempwndctrl"></a><a name="m_pwndctrl"></a>COleControlSite::m_pWndCtrl  
 包含一个指向`CWnd`对象，表示控件本身。  
  
```  
CWnd* m_pWndCtrl;  
```  
  
##  <a name="a-namemrecta--colecontrolsitemrect"></a><a name="m_rect"></a>COleControlSite::m_rect  
 包含控件的控件，相对于容器的窗口边界。  
  
```  
CRect m_rect;  
```  
  
##  <a name="a-namemodifystylea--colecontrolsitemodifystyle"></a><a name="modifystyle"></a>COleControlSite::ModifyStyle  
 修改控件的样式。  
  
```  
virtual BOOL ModifyStyle(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>参数  
 `dwRemove`  
 将删除从当前的窗口样式的样式。  
  
 `dwAdd`  
 要添加从当前的窗口样式的样式。  
  
 `nFlags`  
 窗口定位标志。 有关可能的值的列表，请参阅[SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) ，此功能在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>返回值  
 如果更改样式，否则为零，非零值。  
  
### <a name="remarks"></a>备注  
 控件的股票 Enabled 属性将进行相应修改以匹配的设置**WS_DISABLED**。 控件的常用的边框样式属性将进行相应修改以匹配的请求的设置`WS_BORDER`。 所有其他样式是直接应用于控件的窗口句柄，如果不存在。  
  
 修改控件的窗口样式。 可以通过使用按位 OR 组合样式，以添加或删除 (| | |) 运算符。 请参阅[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) ，此功能在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]有关可用的窗口样式信息。  
  
 如果`nFlags`不为零，`ModifyStyle`调用 Win32 函数`SetWindowPos`，并通过组合重绘的窗口`nFlags`与以下四个标志︰  
  
- `SWP_NOSIZE`保留当前的大小。  
  
- `SWP_NOMOVE`保持当前的位置。  
  
- `SWP_NOZORDER`保留当前的 Z 顺序。  
  
- `SWP_NOACTIVATE`不会激活窗口中。  
  
 若要修改一个窗口的扩展样式，请调用[ModifyStyleEx](#modifystyleex)。  
  
##  <a name="a-namemodifystyleexa--colecontrolsitemodifystyleex"></a><a name="modifystyleex"></a>COleControlSite::ModifyStyleEx  
 修改控件的扩展的样式。  
  
```  
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>参数  
 `dwRemove`  
 若要从当前的窗口样式删除扩展的样式。  
  
 `dwAdd`  
 若要从当前的窗口样式添加扩展的样式。  
  
 `nFlags`  
 窗口定位标志。 有关可能的值的列表，请参阅[SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) ，此功能在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>返回值  
 如果更改样式，否则为零，非零值。  
  
### <a name="remarks"></a>备注  
 控件的常用外观属性将进行相应修改以匹配的设置**WS_EX_CLIENTEDGE**。 所有其他扩展的窗口样式是直接应用于控件的窗口句柄，如果不存在。  
  
 修改扩展控件站点对象的样式窗口。 可以通过使用按位 OR 组合样式，以添加或删除 (| | |) 运算符。 请参阅[CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) ，此功能在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]有关可用的窗口样式信息。  
  
 如果`nFlags`不为零，`ModifyStyleEx`调用 Win32 函数`SetWindowPos`，并通过组合重绘的窗口`nFlags`与以下四个标志︰  
  
- `SWP_NOSIZE`保留当前的大小。  
  
- `SWP_NOMOVE`保持当前的位置。  
  
- `SWP_NOZORDER`保留当前的 Z 顺序。  
  
- `SWP_NOACTIVATE`不会激活窗口中。  
  
 若要修改一个窗口的扩展样式，请调用[ModifyStyle](#modifystyle)。  
  
##  <a name="a-namemovewindowa--colecontrolsitemovewindow"></a><a name="movewindow"></a>COleControlSite::MoveWindow  
 更改控件的位置。  
  
```  
virtual void MoveWindow(
    int x,  
    int y,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>参数  
 *x*  
 窗口的左侧新位置。  
  
 *y*  
 窗口顶部的新位置。  
  
 `nWidth`  
 新窗口的宽度  
  
 `nHeight`  
 新窗口的高度。  
  
##  <a name="a-namequickactivatea--colecontrolsitequickactivate"></a><a name="quickactivate"></a>COleControlSite::QuickActivate  
 快速激活所包含的控件。  
  
```  
virtual BOOL QuickActivate();
```  
  
### <a name="return-value"></a>返回值  
 非零控制站点处于激活状态，否则为零。  
  
### <a name="remarks"></a>备注  
 仅当用户重写控件的创建过程，应调用此函数。  
  
 `IPersist*::Load`和`IPersist*::InitNew`快速激活发生后，应调用的方法。 该控件应在快速激活过程中建立其连接到容器的接收器。 但是，这些连接不是实时直到`IPersist*::Load`或`IPersist*::InitNew`已调用。  
  
##  <a name="a-namesafesetpropertya--colecontrolsitesafesetproperty"></a><a name="safesetproperty"></a>COleControlSite::SafeSetProperty  
 设置指定的控件属性`dwDispID`。  
  
```  
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>参数  
 `dwDispID`  
 标识属性或方法，在该控件上找到的调度 ID`IDispatch`接口，以设置。  
  
 `vtProp`  
 指定要设置属性的类型。 有关可能的值，请参阅备注部分[COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)。  
  
 *...*  
 由 `vtProp`指定的类型的单个参数。  
  
### <a name="return-value"></a>返回值  
 如果成功，则不为零，否则为零。  
  
### <a name="remarks"></a>备注  
  
> [!NOTE]
>  与不同`SetProperty`和`SetPropertyV`，如果 （例如，尝试设置不存在的属性） 遇到错误，不会引发异常。  
  
##  <a name="a-namesetdefaultbuttona--colecontrolsitesetdefaultbutton"></a><a name="setdefaultbutton"></a>COleControlSite::SetDefaultButton  
 将控件设置为默认按钮。  
  
```  
void SetDefaultButton(BOOL bDefault);
```  
  
### <a name="parameters"></a>参数  
 `bDefault`  
 非零，如果该控件应会成为默认按钮;否则为零。  
  
### <a name="remarks"></a>备注  
  
> [!NOTE]
>  该控件必须具有**OLEMISC_ACTSLIKEBUTTON**设置状态位。  
  
##  <a name="a-namesetdlgctrlida--colecontrolsitesetdlgctrlid"></a><a name="setdlgctrlid"></a>COleControlSite::SetDlgCtrlID  
 更改控件的对话框项标识符的值。  
  
```  
virtual int SetDlgCtrlID(int nID);
```  
  
### <a name="parameters"></a>参数  
 `nID`  
 新的标识符值。  
  
### <a name="return-value"></a>返回值  
 如果成功上, 一个对话框项窗口; 的标识符否则为 0。  
  
### <a name="remarks"></a>备注  
  
##  <a name="a-namesetfocusa--colecontrolsitesetfocus"></a><a name="setfocus"></a>COleControlSite::SetFocus  
 将焦点移到控件。  
  
```  
virtual CWnd* SetFocus();  
virtual CWnd* SetFocus(LPMSG lpmsg);
```  
  
### <a name="parameters"></a>参数  
 *lpmsg*  
 一个指向[MSG 结构](../../mfc/reference/msg-structure1.md)。 此结构包含 Windows 消息触发`SetFocus`当前控件站点中包含的控件的请求。  
  
### <a name="return-value"></a>返回值  
 指向以前具有焦点的窗口的指针。  
  
##  <a name="a-namesetpropertya--colecontrolsitesetproperty"></a><a name="setproperty"></a>COleControlSite::SetProperty  
 设置指定的控件属性`dwDispID`。  
  
```  
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>参数  
 `dwDispID`  
 标识属性或方法，在该控件上找到的调度 ID`IDispatch`接口，以设置。  
  
 `vtProp`  
 指定要设置属性的类型。 有关可能的值，请参阅备注部分[COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)。  
  
 *...*  
 由 `vtProp`指定的类型的单个参数。  
  
### <a name="remarks"></a>备注  
 如果`SetProperty`在遇到错误，则引发异常。  
  
 异常的类型是由尝试设置属性或方法的返回值确定的。 如果返回值是`DISP_E_EXCEPTION`、 **COleDispatchExcpetion**则引发该异常; 否则为`COleException`。  
  
##  <a name="a-namesetpropertyva--colecontrolsitesetpropertyv"></a><a name="setpropertyv"></a>COleControlSite::SetPropertyV  
 设置指定的控件属性`dwDispID`。  
  
```  
virtual void SetPropertyV(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    va_list argList);
```  
  
### <a name="parameters"></a>参数  
 `dwDispID`  
 标识属性或方法，在该控件上找到的调度 ID`IDispatch`接口，以设置。  
  
 `vtProp`  
 指定要设置属性的类型。 有关可能的值，请参阅备注部分[COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)。  
  
 `argList`  
 指向参数列表的指针。  
  
### <a name="remarks"></a>备注  
 为方法或属性正在被调用的额外参数可以是 passeed 使用*arg_list*参数。 如果`SetProperty`在遇到错误，则引发异常。  
  
 异常的类型是由尝试设置属性或方法的返回值确定的。 如果返回值是`DISP_E_EXCEPTION`、 **COleDispatchExcpetion**则引发该异常; 否则为`COleException`。  
  
##  <a name="a-namesetwindowposa--colecontrolsitesetwindowpos"></a><a name="setwindowpos"></a>COleControlSite::SetWindowPos  
 设置大小、 位置和控件所在位置的 Z 顺序。  
  
```  
virtual BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>参数  
 `pWndInsertAfter`  
 指向窗口的指针。  
  
 *x*  
 窗口的左侧新位置。  
  
 *y*  
 窗口顶部的新位置。  
  
 `cx`  
 新窗口的宽度  
  
 `cy`  
 新窗口的高度。  
  
 `nFlags`  
 指定的窗口大小调整和定位标志。 有关可能的值，请参阅备注部分[SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>返回值  
 非零如果成功，否则为零。  
  
##  <a name="a-namesetwindowtexta--colecontrolsitesetwindowtext"></a><a name="setwindowtext"></a>COleControlSite::SetWindowText  
 设置控件所在位置的文本。  
  
```  
virtual void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>参数  
 `lpszString`  
 指向以 null 结尾的字符串用作新的标题或控件文本指针。  
  
### <a name="remarks"></a>备注  
 此函数首先尝试设置标题常用属性。 如果不支持标题常用属性，则将改为设置 Text 属性。  
  
##  <a name="a-nameshowwindowa--colecontrolsiteshowwindow"></a><a name="showwindow"></a>COleControlSite::ShowWindow  
 设置窗口的显示状态。  
  
```  
virtual BOOL ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>参数  
 `nCmdShow`  
 指定控件所在位置的显示方式。 它必须是下列值之一︰  
  
- **SW_HIDE**隐藏此窗口，并将激活传递到另一个窗口。  
  
- **SW_MINIMIZE**最小化窗口，并激活系统的列表中的顶级窗口。  
  
- **SW_RESTORE**激活，并且显示窗口。 如果该窗口已最小化，则最大化，Windows 会将其还原到其原始大小和位置。  
  
- **SW_SHOW**激活窗口，并将其显示在其当前大小和位置。  
  
- **SW_SHOWMAXIMIZED**激活窗口，并将其显示为最大化的窗口。  
  
- **SW_SHOWMINIMIZED**激活窗口，并将其显示为图标。  
  
- **SW_SHOWMINNOACTIVE**窗口中显示为图标。 当前处于活动状态窗口将保持活动状态。  
  
- **SW_SHOWNA**显示其当前状态中的窗口。 当前处于活动状态窗口将保持活动状态。  
  
- **SW_SHOWNOACTIVATE**显示窗口中的最新的大小和位置。 当前处于活动状态窗口将保持活动状态。  
  
- **SW_SHOWNORMAL**激活，并且显示窗口。 如果该窗口已最小化，则最大化，Windows 会将其还原到其原始大小和位置。  
  
### <a name="return-value"></a>返回值  
 如果该窗口是以前可见，则非零值如果以前隐藏的窗口为 0。  
  
## <a name="see-also"></a>另请参阅  
 [CCmdTarget 类](../../mfc/reference/ccmdtarget-class.md)   
 [层次结构图](../../mfc/hierarchy-chart.md)   
 [COleControlContainer 类](../../mfc/reference/colecontrolcontainer-class.md)

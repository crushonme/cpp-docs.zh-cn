---
title: "CComVariant 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComVariant
- ATL::CComVariant
- CComVariant
dev_langs:
- C++
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
caps.latest.revision: 26
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
ms.openlocfilehash: 4b01ca9da3d216603ea7efad228735edd1becbd3
ms.lasthandoff: 02/24/2017

---
# <a name="ccomvariant-class"></a>CComVariant 类
此类包装`VARIANT`提供了一个指示存储的数据类型成员的类型。  
  
## <a name="syntax"></a>语法  
  
```  
cpp
class CComVariant : public tagVARIANT  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|说明|  
|----------|-----------------|  
|[CComVariant::CComVariant](#ccomvariant)|构造函数。|  
|[CComVariant:: ~ CComVariant](#dtor)|析构函数。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|说明|  
|----------|-----------------|  
|[CComVariant::Attach](#attach)|将附加**VARIANT**到`CComVariant`对象。|  
|[CComVariant::ChangeType](#changetype)|将转换`CComVariant`对象传递给新的类型。|  
|[CComVariant::Clear](#clear)|清除`CComVariant`对象。|  
|[CComVariant::Copy](#copy)|副本**VARIANT**到`CComVariant`对象。|  
|[CComVariant::CopyTo](#copyto)|中的内容复制`CComVariant`对象。|  
|[CComVariant::Detach](#detach)|分离基础**VARIANT**从`CComVariant`对象。|  
|[CComVariant::GetSize](#getsize)|内容的字节数以返回大小`CComVariant`对象。|  
|[CComVariant::ReadFromStream](#readfromstream)|加载**VARIANT**流中。|  
|[CComVariant::SetByRef](#setbyref)|初始化`CComVariant`对象并设置**vt**成员**VT_BYREF**。|  
|[CComVariant::WriteToStream](#writetostream)|将保存基础**VARIANT**到流。|  
  
### <a name="public-operators"></a>公共运算符  
  
|||  
|-|-|  
|[CComVariant::operator](#operator_lt)|指示是否`CComVariant`对象是早于指定**VARIANT**。|  
|[CComVariant::operator&1;>](#operator_gt)|指示是否`CComVariant`对象是否大于指定**VARIANT**。|  
|[运算符 ！ =](#operator_neq)|指示是否`CComVariant`对象不等于指定**VARIANT**。|  
|[运算符 =](#operator_eq)|将一个值赋给`CComVariant`对象。|  
|[运算符 = =](#operator_eq_eq)|指示是否`CComVariant`对象等于指定**VARIANT**。|  
  
## <a name="remarks"></a>备注  
 `CComVariant`包装`VARIANT and VARIANTARG`类型，其中包含一个联合和一个指示存储在联合中的数据的类型成员。 **VARIANT**s 通常使用在自动化中。  
  
 `CComVariant`派生自**VARIANT**键入，以便它可以是任何位置使用**VARIANT**可用。 例如，可以使用**V_VT**宏来提取的一种`CComVariant`或可以访问**vt**成员直接就像可以与**VARIANT**。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `tagVARIANT`  
  
 `CComVariant`  
  
## <a name="requirements"></a>要求  
 **标头︰** atlcomcli.h  
  
##  <a name="a-nameattacha--ccomvariantattach"></a><a name="attach"></a>CComVariant::Attach  
 安全地清除的当前内容`CComVariant`对象，请将复制的内容`pSrc`到此对象，然后设置变体类型的`pSrc`到`VT_EMPTY`。  
  
```
HRESULT Attach(VARIANT* pSrc);
```  
  
### <a name="parameters"></a>参数  
 `pSrc`  
 [in]指向[VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)要附加到该对象。  
  
### <a name="return-value"></a>返回值  
 标准 `HRESULT` 值。  
  
### <a name="remarks"></a>备注  
 所保存的数据的所有权`pSrc`转移到`CComVariant`对象。  
  
##  <a name="a-nameccomvarianta--ccomvariantccomvariant"></a><a name="ccomvariant"></a>CComVariant::CComVariant  
 每个构造函数会处理的安全初始化`CComVariant`对象通过调用`VariantInit`Win32 函数或通过设置对象的值和根据传递的参数的类型。  
  
```
CComVariant() throw();
CComVariant(const CComVariant& varSrc);
CComVariant(const VARIANT& varSrc);
CComVariant(LPCOLESTR lpszSrc);
CComVariant(LPCSTR lpszSrc);
CComVariant(bool bSrc);
CComVariant(BYTE nSrc) throw();
CComVariant(int nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned int  nSrc, VARTYPE vtSrc = VT_UI4) throw();
CComVariant(shor  nSrc) throw();
CComVariant(unsigned short nSrc) throw();
CComVariant(long  nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned long  nSrc) throw();
CComVariant(LONGLONG  nSrc) throw();
CComVariant(ULONGLONG  nSrc) throw();
CComVariant(float  fltSrc) throw();
CComVariant(double  dblSrc, VARTYPE vtSrc = VT_R8) throw();
CComVariant(CY  cySrc) throw();
CComVariant(IDispatch* pSrc) throw();
CComVariant(IUnknown* pSrc) throw();
CComVariant(const SAFEARRAY* pSrc);
CComVariant(char  cSrc) throw();
CComVariant(const CComBSTR& bstrSrc);
```  
  
### <a name="parameters"></a>参数  
 *varSrc*  
 [in]`CComVariant`或`VARIANT`用来初始化`CComVariant`对象。 源变体的内容复制到目标而不进行转换。  
  
 `lpszSrc`  
 [in]用于初始化字符串`CComVariant`对象。 您可以将传递以零结尾宽 (Unicode) 字符的字符串到**LPCOLESTR**版本的构造函数或非 ANSI 字符串到`LPCSTR`版本。 在任一情况下，此字符串将转换为 Unicode`BSTR`使用分配**SysAllocString**。 一种`CComVariant`对象将被`VT_BSTR`。  
  
 `bSrc`  
 [in]`bool`用来初始化`CComVariant`对象。 `bool`参数转换为**VARIANT_BOOL**之前存储。 一种`CComVariant`对象将被`VT_BOOL`。  
  
 `nSrc`  
 [in]`int`，**字节**，**短**，**长**， **LONGLONG**， **ULONGLONG**，**无符号短**， `unsigned long`，或`unsigned int`用来初始化`CComVariant`对象。 The type of the `CComVariant` object will be `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**, **VT_UI4**, or **VT_UI4**, respectively.  
  
 `vtSrc`  
 [in]该变量的类型。 当第一个参数是`int`，有效类型是`VT_I4`和**VT_INT**。 当第一个参数是**长**，有效类型是`VT_I4`和`VT_ERROR`。 当第一个参数是**double**，有效类型是`VT_R8`和`VT_DATE`。 当第一个参数是`unsigned int`，有效类型是**VT_UI4**和**VT_UINT**。  
  
 `fltSrc`  
 [in]**Float**用来初始化`CComVariant`对象。 一种`CComVariant`对象将被`VT_R4`。  
  
 `dblSrc`  
 [in]**Double**用来初始化`CComVariant`对象。 一种`CComVariant`对象将被`VT_R8`。  
  
 `cySrc`  
 [in]**CY**用来初始化`CComVariant`对象。 一种`CComVariant`对象将被`VT_CY`。  
  
 `pSrc`  
 [in]`IDispatch`或**IUnknown**指针用于初始化`CComVariant`对象。 `AddRef`将在接口指针上调用。 一种`CComVariant`对象将被**VT_DISPATCH**或**VT_UNKNOWN**分别。  
  
 或者， **SAFERRAY**指针用于初始化`CComVariant`对象。 一份**SAFEARRAY**存储在`CComVariant`对象。 一种`CComVariant`将此对象的原始类型的组合**SAFEARRAY**和**VT_ARRAY**。  
  
 `cSrc`  
 [in]`char`用来初始化`CComVariant`对象。 一种`CComVariant`对象将被**VT_I1**。  
  
 `bstrSrc`  
 [in]BSTR 用来初始化`CComVariant`对象。 一种`CComVariant`对象将被`VT_BSTR`。  
  
### <a name="remarks"></a>备注  
 通过调用的析构函数管理清理[CComVariant::Clear](#clear)。  
  
##  <a name="a-namedtora--ccomvariantccomvariant"></a><a name="dtor"></a>CComVariant:: ~ CComVariant  
 析构函数。  
  
```
~CComVariant() throw();
```  
  
### <a name="remarks"></a>备注  
 此方法通过调用管理清理[CComVariant::Clear](#clear)。  
  
##  <a name="a-namechangetypea--ccomvariantchangetype"></a><a name="changetype"></a>CComVariant::ChangeType  
 将转换`CComVariant`对象传递给新的类型。  
  
```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```  
  
### <a name="parameters"></a>参数  
 `vtNew`  
 [in]新类型`CComVariant`对象。  
  
 `pSrc`  
 [in]一个指向`VARIANT`其值将转换为新类型。 默认值是**NULL**，这意味着`CComVariant`将就地转换对象。  
  
### <a name="return-value"></a>返回值  
 标准 `HRESULT` 值。  
  
### <a name="remarks"></a>备注  
 如果传递的值`pSrc`，`ChangeType`将使用此**VARIANT**作为转换的源。 否则为`CComVariant`对象将成为源。  
  
##  <a name="a-namecleara--ccomvariantclear"></a><a name="clear"></a>CComVariant::Clear  
 清除`CComVariant`对象通过调用`VariantClear`Win32 函数。  
  
```
HRESULT Clear();
```  
  
### <a name="return-value"></a>返回值  
 标准 `HRESULT` 值。  
  
### <a name="remarks"></a>备注  
 析构函数自动调用**清除**。  
  
##  <a name="a-namecopya--ccomvariantcopy"></a><a name="copy"></a>CComVariant::Copy  
 释放`CComVariant`对象，然后将其分配一份指定**VARIANT**。  
  
```
HRESULT Copy(const VARIANT* pSrc);
```  
  
### <a name="parameters"></a>参数  
 `pSrc`  
 [in]一个指向[VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)要复制。  
  
### <a name="return-value"></a>返回值  
 标准 `HRESULT` 值。  
  
##  <a name="a-namecopytoa--ccomvariantcopyto"></a><a name="copyto"></a>CComVariant::CopyTo  
 中的内容复制`CComVariant`对象。  
  
```
HRESULT CopyTo(BSTR* pstrDest);
```  
  
### <a name="parameters"></a>参数  
 *pstrDest*  
 指向`BSTR`中将接收的内容的副本`CComVariant`对象。  
  
### <a name="return-value"></a>返回值  
 标准 `HRESULT` 值。  
  
### <a name="remarks"></a>备注  
 **CComVariant**对象的类型必须是`VT_BSTR`。  
  
##  <a name="a-namedetacha--ccomvariantdetach"></a><a name="detach"></a>CComVariant::Detach  
 分离基础**VARIANT**从`CComVariant`对象，并将该对象的类型设置为`VT_EMPTY`。  
  
```
HRESULT Detach(VARIANT* pDest);
```  
  
### <a name="parameters"></a>参数  
 `pDest`  
 [out]返回基础`VARIANT`对象值。  
  
### <a name="return-value"></a>返回值  
 标准 `HRESULT` 值。  
  
### <a name="remarks"></a>备注  
 请注意，内容`VARIANT`所引用的`pDest`自动将所赋的值和类型调用前清除**CComVariant**对象。  
  
##  <a name="a-namegetsizea--ccomvariantgetsize"></a><a name="getsize"></a>CComVariant::GetSize  
 对于简单的固定大小`VARIANT`s，此方法返回`sizeof`基础数据类型加上`sizeof(VARTYPE)`。  
  
```
ULONG GetSize() const;
```  
  
### <a name="return-value"></a>返回值  
 以字节为单位的当前内容的大小`CComVariant`对象。  
  
### <a name="remarks"></a>备注  
 如果`VARIANT`包含类型的接口指针`GetSize`查询`IPersistStream`或`IPersistStreamInit`。 如果成功，，则返回值是个返回的值的低 32 位`GetSizeMax`加上`sizeof``CLSID`和`sizeof(VARTYPE)`。 如果接口指针为`NULL`，`GetSize`返回`sizeof``CLSID`加上`sizeof(VARTYPE)`。 如果总大小大于`ULONG_MAX`，`GetSize`返回`sizeof(VARTYPE)`指示错误。  
  
 在所有其他情况下，临时`VARIANT`类型的`VT_BSTR`强制从当前`VARIANT`。 此长度`BSTR`作为字符串的长度再加上字符串本身长度的大小加上加上的 null 字符的大小计算`sizeof(VARTYPE)`。 如果`VARIANT`不能强制转换为`VARIANT`类型的`VT_BSTR`，`GetSize`返回`sizeof(VARTYPE)`。  
  
 此方法返回的大小与使用的字节数的数目匹配[CComVariant::WriteToStream](#writetostream)成功的情况下。  
  
##  <a name="a-nameoperatoreqa--ccomvariantoperator-"></a><a name="operator_eq"></a>CComVariant::operator =  
 将分配一个值，并相应类型设置为`CComVariant`对象。  
  
```
CComVariant& operator=(const CComVariant& varSrc);
CComVariant& operator=(const VARIANT& varSrc);
CComVariant& operator=(const CComBSTR& bstrSrc);
CComVariant& operator=(LPCOLESTR lpszSrc);
CComVariant& operator=(LPCSTR lpszSrc);
CComVariant& operator=(bool bSrc);
CComVariant& operator=(BYTE nSrc) throw();
CComVariant& operator=int nSrc) throw();
CComVariant& operator=(unsigned int nSrc) throw();
CComVariant& operator=(short nSrc) throw();
CComVariant& operator=(unsigned short nSrc) throw();
CComVariant& operator=(long nSrc) throw();
CComVariant& operator=(unsigned long nSrc) throw();
CComVariant& operator=(LONGLONG nSrc) throw();
CComVariant& operator=(ULONGLONG nSrc) throw();
CComVariant& operator=(float fltSrc) throw();
CComVariant& operator=(double dblSrc) throw();
CComVariant& operator=(CY cySrc) throw();
CComVariant& operator=(IDispatch* pSrc) throw();
CComVariant& operator=(IUnknown* pSrc) throw();
CComVariant& operator=(const SAFEARRAY* pSrc);
CComVariant& operator=(char cSrc) throw();
```  
  
### <a name="parameters"></a>参数  
 *varSrc*  
 [in]`CComVariant`或[VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)要分配给`CComVariant`对象。 源变体的内容复制到目标而不进行转换。  
  
 `bstrSrc`  
 [in]要分配给的 BSTR`CComVariant`对象。 一种`CComVariant`对象将被`VT_BSTR`。  
  
 `lpszSrc`  
 [in]要分配给字符串`CComVariant`对象。 您可以将传递以零结尾宽 (Unicode) 字符的字符串到**LPCOLESTR**版本将运算符或对非 ANSI 字符串`LPCSTR`版本。 在任一情况下，此字符串将转换为 Unicode`BSTR`使用分配**SysAllocString**。 一种`CComVariant`对象将被`VT_BSTR`。  
  
 `bSrc`  
 [in]`bool`要分配给`CComVariant`对象。 `bool`参数转换为**VARIANT_BOOL**之前存储。 一种`CComVariant`对象将被`VT_BOOL`。  
  
 `nSrc`  
 [in]The `int`, **BYTE**, **short**, **long**, **LONGLONG**, **ULONGLONG**, **unsigned short**, `unsigned long`, or `unsigned int` to be assigned to the `CComVariant` object. The type of the `CComVariant` object will be `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**, **VT_UI4**, or **VT_UI4**, respectively.  
  
 `fltSrc`  
 [in]**Float**要分配给`CComVariant`对象。 一种`CComVariant`对象将被`VT_R4`。  
  
 `dblSrc`  
 [in]**Double**要分配给`CComVariant`对象。 一种`CComVariant`对象将被`VT_R8`。  
  
 `cySrc`  
 [in]**CY**要分配给`CComVariant`对象。 一种`CComVariant`对象将被`VT_CY`。  
  
 `pSrc`  
 [in]`IDispatch`或**IUnknown**指针分配给`CComVariant`对象。 `AddRef`将在接口指针上调用。 一种`CComVariant`对象将被**VT_DISPATCH**或**VT_UNKNOWN**分别。  
  
 或者， **SAFEARRAY**指针分配给`CComVariant`对象。 一份**SAFEARRAY**存储在`CComVariant`对象。 一种`CComVariant`将此对象的原始类型的组合**SAFEARRAY**和**VT_ARRAY**。  
  
 `cSrc`  
 [in]要分配给 char`CComVariant`对象。 一种`CComVariant`对象将被**VT_I1**。  
  
##  <a name="a-nameoperatoreqeqa--ccomvariantoperator-"></a><a name="operator_eq_eq"></a>CComVariant::operator = =  
 指示是否`CComVariant`对象等于指定**VARIANT**。  
  
```
bool operator==(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>备注  
 返回**true**如果值和类型*varSrc*相等的值和类型，分别`CComVariant`对象。 否则为**false**。 该运算符使用用户的默认区域设置来执行比较。  
  
 该运算符只变体类型的值进行比较。 它将比较字符串、 整数和浮点型的点，但不是数组或记录。  
  
##  <a name="a-nameoperatorneqa--ccomvariantoperator-"></a><a name="operator_neq"></a>CComVariant::operator ！ =  
 指示是否`CComVariant`对象不等于指定**VARIANT**。  
  
```
bool operator!=(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>备注  
 返回**true**如果的值或类型*varSrc*是否不等于值或键入，分别`CComVariant`对象。 否则为**false**。 该运算符使用用户的默认区域设置来执行比较。  
  
 该运算符只变体类型的值进行比较。 它将比较字符串、 整数和浮点型的点，但不是数组或记录。  
  
##  <a name="a-nameoperatorlta--ccomvariantoperator-lt"></a><a name="operator_lt"></a>CComVariant::operator&lt;  
 指示是否`CComVariant`对象是早于指定**VARIANT**。  
  
```
bool operator<(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>备注  
 返回**true**如果的值`CComVariant`对象小于的值*varSrc*。 否则为**false**。 该运算符使用用户的默认区域设置来执行比较。  
  
##  <a name="a-nameoperatorgta--ccomvariantoperator-gt"></a><a name="operator_gt"></a>CComVariant::operator&gt;  
 指示是否`CComVariant`对象是否大于指定**VARIANT**。  
  
```
bool operator>(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>备注  
 返回**true**如果的值`CComVariant`对象参数的值大于*varSrc*。 否则为**false**。 该运算符使用用户的默认区域设置来执行比较。  
  
##  <a name="a-namereadfromstreama--ccomvariantreadfromstream"></a><a name="readfromstream"></a>CComVariant::ReadFromStream  
 设置基础**VARIANT**到**VARIANT**包含在指定的流。  
  
```
HRESULT ReadFromStream(IStream* pStream);
```  
  
### <a name="parameters"></a>参数  
 `pStream`  
 [in]一个指向[IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)上包含数据的流接口。  
  
### <a name="return-value"></a>返回值  
 标准 `HRESULT` 值。  
  
### <a name="remarks"></a>备注  
 **ReadToStream**要求对以前调用[WriteToStream](#writetostream)。  
  
##  <a name="a-namesetbyrefa--ccomvariantsetbyref"></a><a name="setbyref"></a>CComVariant::SetByRef  
 初始化`CComVariant`对象并设置**vt**成员**VT_BYREF**。  
  
```
template < typename T >
void SetByRef(T* pT) throw();
```  
  
### <a name="parameters"></a>参数  
 `T`  
 一种**VARIANT**，例如， `BSTR`， `int`，或`char`。  
  
 *pT*  
 用于初始化的指针`CComVariant`对象。  
  
### <a name="remarks"></a>备注  
 `SetByRef`是一个函数模板，初始化`CComVariant`对象与指针*pT* ，并设置**vt**成员**VT_BYREF**。 例如:   
  
 [!code-cpp[NVC_ATL_Utilities #&76;](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]  
  
##  <a name="a-namewritetostreama--ccomvariantwritetostream"></a><a name="writetostream"></a>CComVariant::WriteToStream  
 将保存基础**VARIANT**到流。  
  
```
HRESULT WriteToStream(IStream* pStream);
```  
  
### <a name="parameters"></a>参数  
 `pStream`  
 [in]一个指向[IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)流上的接口。  
  
### <a name="return-value"></a>返回值  
 标准 `HRESULT` 值。  
  
## <a name="see-also"></a>另请参阅  
 [类概述](../../atl/atl-class-overview.md)
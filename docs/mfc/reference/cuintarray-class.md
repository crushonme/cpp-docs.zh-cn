---
title: "CUIntArray 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUIntArray
dev_langs:
- C++
helpviewer_keywords:
- INT
- UINT
- indexed arrays
- arrays [C++], indexed
- WORD data type
- CUIntArray class
ms.assetid: d71f3d8f-ef9f-4e48-9b69-7782c0e2ddf7
caps.latest.revision: 23
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
ms.openlocfilehash: 901ec011c6371b9c6a58ed71343480fe9a6ffe88
ms.lasthandoff: 02/24/2017

---
# <a name="cuintarray-class"></a>CUIntArray 类
支持无符号整数数组。  
  
## <a name="syntax"></a>语法  
  
```  
class CUIntArray : public CObject  
```  
  
## <a name="members"></a>成员  
 成员函数`CUIntArray`类似于类的成员函数[CObArray](../../mfc/reference/cobarray-class.md)。 由于此相似性，因此你可以使用 `CObArray` 参考文档获取成员函数细节。 无论您在何处`CObject`指针作为函数参数或返回值，替换**UINT**。  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 例如，转换为  
  
 `UINT CUIntArray::GetAt( int <nIndex> ) const;`  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|构造一个空数组。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|说明|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|向数组的末尾添加一个元素；根据需要扩展该数组。|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|将另一个数组追加到该数组中；根据需要扩展该数组。|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|将另一个数组复制到该数组；根据需要扩展该数组。|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|在该数组中返回对元素指针的临时引用。|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|若高于当前的上限，则将释放所有未使用的内存。|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|返回给定索引位置处的值。|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|获取此数组中的元素数。|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|允许访问该数组中的元素。 可以是**NULL**。|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|获取此数组中的元素数。|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|返回最大的有效索引。|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|在指定索引处插入一个元素（或另一个数组中的所有元素）。|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|确定数组是否为空。|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|从此数组中移除所有元素。|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|移除特定索引处的元素。|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|设置给定索引的值；不允许对该数组进行扩展。|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|设置给定索引的值；根据需要扩展该数组。|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|设置要在该数组中包含的元素数。|  
  
### <a name="public-operators"></a>公共运算符  
  
|名称|说明|  
|----------|-----------------|  
|[CObArray::operator]](../../mfc/reference/cobarray-class.md#operator_at)|设置或获取位于指定索引处的元素。|  
  
## <a name="remarks"></a>备注  
 无符号的整数，或**UINT**，从字和双字中的不同的物理大小**UINT**可能会根据目标操作环境更改。 一个**UINT**双字的大小相同。  
  
 `CUIntArray`集成了[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)宏来支持运行时类型访问和转储到[CDumpContext](../../mfc/reference/cdumpcontext-class.md)对象。 如果您需要单独的无符号的整数的元素进行转储，必须将转储上下文的深度设置为 1 或更高。 无符号的整数数组无法序列化。  
  
> [!NOTE]
>  在使用数组之前，先使用 `SetSize` 建立其大小并为其分配内存。 如果不使用 `SetSize`，则向数组添加元素会导致它经常重新分配和复制。 经常重新分配和复制会降低效率而且会产生内存碎片。  
  
 有关详细信息使用`CUIntArray`，请参阅文章[集合](../../mfc/collections.md)。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CUIntArray`  
  
## <a name="requirements"></a>要求  
 **标头︰** afxcoll.h  
  
## <a name="see-also"></a>另请参阅  
 [CObject 类](../../mfc/reference/cobject-class.md)   
 [层次结构图](../../mfc/hierarchy-chart.md)




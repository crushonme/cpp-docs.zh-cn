---
title: "Crowsetimpl:: Getcolumninfo |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetColumnInfo
- CRowsetImpl.GetColumnInfo
- CRowsetImpl::GetColumnInfo
dev_langs: C++
helpviewer_keywords: GetColumnInfo method
ms.assetid: 9ef76525-f996-4c6f-81b9-68eb260350ef
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: acfc7e4afa0036c6f6e66aaef65305fc05ef6d14
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetimplgetcolumninfo"></a>CRowsetImpl::GetColumnInfo
检索特定客户端请求的列信息。  
  
## <a name="syntax"></a>语法  
  
```  
  
      static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(  
   T* pv,  
   ULONG* pcCols   
);  
```  
  
#### <a name="parameters"></a>参数  
 `pv`  
 [in]对用户的指针`CRowsetImpl`派生类。  
  
 `pcCols`  
 [in]返回列的指针 （输出） 的数字。  
  
## <a name="return-value"></a>返回值  
 指向静态**ATLCOLUMNINFO**结构。  
  
## <a name="remarks"></a>备注  
 此方法是高级的替代。  
  
 若要为特定的客户端请求检索列信息的多个基实现类调用此方法。 通常情况下，将调用此方法`IColumnsInfoImpl`。 如果你重写此方法，则必须放在方法中的版本你`CRowsetImpl`-派生类。 由于该方法可能会放置在非模板化类中，你必须更改`pv`到相应`CRowsetImpl`-派生类。  
  
 下面的示例演示**GetColumnInfo 的**使用情况。 在此示例中， **CMyRowset**是`CRowsetImpl`-派生类。 若要重写`GetColumnInfo`对于此类的所有实例，请将中的以下方法**CMyRowset**类定义：  
  
 [!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]  
  
## <a name="requirements"></a>惠?  
 **标头：** atldb.h  
  
## <a name="see-also"></a>请参阅  
 [CRowsetImpl 类](../../data/oledb/crowsetimpl-class.md)
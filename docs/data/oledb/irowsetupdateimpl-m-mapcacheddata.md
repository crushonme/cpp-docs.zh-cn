---
title: "Irowsetupdateimpl:: M_mapcacheddata |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl.m_mapCachedData
- IRowsetUpdateImpl::m_mapCachedData
- m_mapCachedData
dev_langs: C++
helpviewer_keywords: m_mapCachedData
ms.assetid: 65131743-8580-48c8-bb22-68f17c9dfa13
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c3b48a309d10d232eb311b66602e61ff727cdef7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetupdateimplmmapcacheddata"></a>IRowsetUpdateImpl::m_mapCachedData
包含该延迟操作的原始数据的映射。  
  
## <a name="syntax"></a>语法  
  
```  
  
      CAtlMap<   
   HROW hRow,    
   Storage* pData   
>   
m_mapCachedData;  
```  
  
#### <a name="parameters"></a>参数  
 `hRow`  
 数据行的句柄。  
  
 `pData`  
 指向要缓存的数据的指针。 类型的数据为*存储*（用户记录类）。 请参阅*存储*中的模板自变量[IRowsetUpdateImpl 类](../../data/oledb/irowsetupdateimpl-class.md)。  
  
## <a name="requirements"></a>惠?  
 **标头：** atldb.h  
  
## <a name="see-also"></a>请参阅  
 [IRowsetUpdateImpl 类](../../data/oledb/irowsetupdateimpl-class.md)
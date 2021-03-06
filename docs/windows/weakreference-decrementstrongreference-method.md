---
title: "Weakreference:: Decrementstrongreference 方法 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
dev_langs: C++
helpviewer_keywords: DecrementStrongReference method
ms.assetid: 97d70d9f-41b8-4f8d-a6fa-4137cc4f9029
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bda6de03ce17db7ebac751865686c3e74a26d0d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="weakreferencedecrementstrongreference-method"></a>WeakReference::DecrementStrongReference 方法
支持 WRL 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```  
ULONG DecrementStrongReference();  
```  
  
## <a name="remarks"></a>备注  
 递减当前 WeakReference 对象的强引用计数。  
  
 当强引用计数变为零时，强引用设置为`nullptr`。  
  
## <a name="return-value"></a>返回值  
 递减的强引用计数。  
  
## <a name="requirements"></a>惠?  
 **标头：** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>请参阅  
[WeakReference 类](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details 命名空间](../windows/microsoft-wrl-details-namespace.md)
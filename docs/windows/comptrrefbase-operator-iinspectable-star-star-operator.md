---
title: "Comptrrefbase:: Operator IInspectable * * 运算符 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
dev_langs: C++
helpviewer_keywords: operator IInspectable** operator
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d83580537a81b1c75f44e32e6aa43b2b014c8373
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="comptrrefbaseoperator-iinspectable-operator"></a>ComPtrRefBase::operator IInspectable** 运算符

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
operator IInspectable**() const;
```

## <a name="remarks"></a>备注

将当前强制转换[ptr_](../windows/comptrrefbase-ptr-data-member.md)对指针到-a-指针-到的数据成员 IInspectable 接口。

如果当前 ComPtrRefBase 不派生自 IInspectable，则会发出错误。

此强制转换为可用才**&#95; &#95;WRL_CLASSIC_COM &#95; &#95;**定义。

## <a name="requirements"></a>惠?

**标头：** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>请参阅

[ComPtrRefBase 类](../windows/comptrrefbase-class.md)   
[Microsoft::WRL::Details 命名空间](../windows/microsoft-wrl-details-namespace.md)
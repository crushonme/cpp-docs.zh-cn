---
title: "CUserException 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CUserException
dev_langs: C++
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4613f2ba06ffa697df219172b98a5cf193c1f3b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="cuserexception-class"></a>CUserException 类
引发后将终止最终用户操作。  
  
## <a name="syntax"></a>语法  
  
```  
class CUserException : public CSimpleException  
```  
  
## <a name="remarks"></a>备注  
 使用`CUserException`如果想要使用 throw/catch 异常机制来特定于应用程序的异常。 类名中的"用户"可以解释为"我的用户执行了异常，我需要处理。"  
  
 A`CUserException`调用全局函数后，就会引发`AfxMessageBox`以通知用户，操作失败。 当你编写异常处理程序时，处理异常，专门因为用户通常已通知失败。 在某些情况下，框架会引发此异常。 引发`CUserException`你自己，向用户发出警报，然后调用全局函数`AfxThrowUserException`。  
  
 在下面的示例中，包含可能会失败的操作的函数提醒用户，并引发`CUserException`。 调用函数捕捉到异常，并且专门对其进行处理：  
  
 [!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]  
  
 有关详细信息使用`CUserException`，请参阅文章[异常处理 (MFC)](../../mfc/exception-handling-in-mfc.md)。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## <a name="requirements"></a>惠?  
 **标头:** afxwin.h  
  
## <a name="see-also"></a>请参阅  
 [层次结构图](../../mfc/hierarchy-chart.md)   
 [CException 类](../../mfc/reference/cexception-class.md)

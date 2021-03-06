---
title: "访问 ODBC 和 SQL |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- API calls [C++], calling DAO or ODBC directly
- Windows API [C++], calling from MFC
- ODBC API functions [C++]
- ODBC API functions [C++], calling from MFC
- SQL [C++], calling ODBC API functions
- ODBC [C++], API functions
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 25e9533752e47e5cf3ea50e594a23b99e19355ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="access-to-odbc-and-sql"></a>访问 ODBC 和 SQL
Microsoft 基础类库封装许多 Windows API 调用，并仍可在直接调用任何 Windows API 函数。 数据库类为你提供了相同的灵活性方面 ODBC API。 尽管数据库类可使您减少了 ODBC 的复杂性，你可以直接从任何位置调用 ODBC API 函数在程序中。  
  
 同样，数据库类使您无需大量使用[SQL](../../data/odbc/sql.md)，但如果你愿意，你可以直接使用 SQL。 可以通过传递的自定义 SQL 语句 （或默认语句设置部分） 自定义记录集对象当打开记录集。 你还可以使用直接 SQL 调用[ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)类的成员函数[CDatabase](../../mfc/reference/cdatabase-class.md)。  
  
 有关详细信息，请参阅[ODBC： 直接调用 ODBC API 函数](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)和[SQL： 进行直接 SQL 调用 (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)。  
  
## <a name="see-also"></a>请参阅  
 [ODBC 和 MFC](../../data/odbc/odbc-and-mfc.md)
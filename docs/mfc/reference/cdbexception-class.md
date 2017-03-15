---
title: "CDBException 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBException
dev_langs:
- C++
helpviewer_keywords:
- CDBException class
- exceptions [C++], database
- database exceptions [C++]
- ODBC classes [C++], exceptions
- errors [C++], database
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
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
ms.openlocfilehash: fc3bf7be273bf509dd1ee79fb42e69050070e830
ms.lasthandoff: 02/24/2017

---
# <a name="cdbexception-class"></a>CDBException 类
表示由数据库类引起的异常条件。  
  
## <a name="syntax"></a>语法  
  
```  
class CDBException : public CException  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-data-members"></a>公共数据成员  
  
|名称|说明|  
|----------|-----------------|  
|[CDBException::m_nRetCode](#m_nretcode)|包含开放式数据库连接 (ODBC) 返回代码类型的**某一 RETCODE**。|  
|[CDBException::m_strError](#m_strerror)|包含在字母数字术语描述错误的字符串。|  
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|包含描述该错误由 ODBC 返回的错误代码方面的字符串。|  
  
## <a name="remarks"></a>备注  
 类包含两个公共数据成员可以使用以确定该异常的原因或显示一条描述异常的文本消息。 `CDBException`对象构造，并由数据库类的成员函数引发。  
  
> [!NOTE]
>  此类是一个 MFC 的开放式数据库连接 (ODBC) 类。 如果您改为使用较新的数据访问对象 (DAO) 类，使用[CDaoException](../../mfc/reference/cdaoexception-class.md)相反。 DAO 类的所有名称都有"CDao"作为前缀。 有关详细信息，请参阅文章[概述︰ 数据库编程](../../data/data-access-programming-mfc-atl.md)。  
  
 异常的不正常执行涉及外部程序的控制，如数据源的条件的情况下，或网络 I/O 错误。 您可能希望在正常的过程中执行您的程序中看到的错误通常不考虑异常。  
  
 您可以访问这些对象的作用域内**捕获**表达式。 您可以引发`CDBException`对象从您自己的代码与`AfxThrowDBException`全局函数。  
  
 有关常规，或有关中的异常处理`CDBException`对象，请参阅文章[异常处理 (MFC)](../../mfc/exception-handling-in-mfc.md)和[异常︰ 数据库异常](../../mfc/exceptions-database-exceptions.md)。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## <a name="requirements"></a>要求  
 **标头︰** afxdb.h  
  
##  <a name="a-namemnretcodea--cdbexceptionmnretcode"></a><a name="m_nretcode"></a>CDBException::m_nRetCode  
 包含 ODBC 错误代码类型的**某一 RETCODE**由 ODBC 应用程序编程接口 (API) 函数返回。  
  
### <a name="remarks"></a>备注  
 这种类型包括按 ODBC 定义的 SQL 前缀代码和 AFX_SQL 前缀代码，由数据库类定义。 有关`CDBException`，此成员将包含下列值之一︰  
  
- **AFX_SQL_ERROR_API_CONFORMANCE**打印机的驱动程序`CDatabase::OpenEx`或`CDatabase::Open`调用不符合所需的 ODBC API 一致性级别 1 ( **SQL_OAC_LEVEL1**)。  
  
- **AFX_SQL_ERROR_CONNECT_FAIL**与数据源的连接失败。 您传递**NULL** `CDatabase`指向记录集构造函数和创建连接的后续尝试基于`GetDefaultConnect`失败。  
  
- **AFX_SQL_ERROR_DATA_TRUNCATED**请求更多的数据不是您所提供的存储。 有关提高的提供的数据存储信息`CString`或`CByteArray`数据类型，请参阅`nMaxLength`参数[RFX_Text](http://msdn.microsoft.com/library/de3c7581-d26c-40cb-81f3-c492ef4809f6)和[RFX_Binary](http://msdn.microsoft.com/library/908ff945-3ad0-43a1-9932-cdcdc8b14915)下"宏和全局函数。"  
  
- **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED**调用`CRecordset::Open`请求动态集失败。 驱动程序不支持动态记录集。  
  
- **AFX_SQL_ERROR_EMPTY_COLUMN_LIST**尝试打开一个表 (或您提供可能不会标识为过程调用或**选择**语句)，但没有列中的记录字段交换 (RFX) 函数调用中标识您`DoFieldExchange`重写。  
  
- **AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH**中 RFX 函数类型您`DoFieldExchange`替代不在记录集中的列数据类型兼容。  
  
- **AFX_SQL_ERROR_ILLEGAL_MODE**您调用`CRecordset::Update`而无需以前调用`CRecordset::AddNew`或`CRecordset::Edit`。  
  
- **AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED**无法满足您的更新锁记录的请求，因为 ODBC 驱动程序不支持锁定。  
  
- **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED**您调用`CRecordset::Update`或**删除**没有唯一键的表和已更改的多个记录。  
  
- **AFX_SQL_ERROR_NO_CURRENT_RECORD**您尝试编辑或删除以前已删除的记录。 您必须在某一删除操作后滚动到新的当前记录。  
  
- **AFX_SQL_ERROR_NO_POSITIONED_UPDATES**您的请求的动态集可能不会完成，因为 ODBC 驱动程序不支持定位更新。  
  
- **AFX_SQL_ERROR_NO_ROWS_AFFECTED**您调用`CRecordset::Update`或**删除**，但操作开始时可能无法再找到该记录。  
  
- **AFX_SQL_ERROR_ODBC_LOAD_FAILED**尝试加载 ODBC。DLL 失败;Windows 找不到或无法加载此 DLL。 此错误是致命错误。  
  
- **AFX_SQL_ERROR_ODBC_V2_REQUIRED**由于级别 2 符合 ODBC 驱动程序是必需的无法满足你的动态集请求。  
  
- **AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY**试图向下滚动失败，因为数据源不支持向后滚动。  
  
- **AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED**调用`CRecordset::Open`请求快照失败。 驱动程序不支持快照。 (这应只情况发生时 ODBC 游标库 â €"ODBCCURS。DLL â €"不存在。）  
  
- **AFX_SQL_ERROR_SQL_CONFORMANCE**打印机的驱动程序`CDatabase::OpenEx`或`CDatabase::Open`调用不符合所需的"最小值"的 ODBC SQL 一致性级别 ( **SQL_OSC_MINIMUM**)。  
  
- **AFX_SQL_ERROR_SQL_NO_TOTAL** ODBC 驱动程序无法将指定的总大小`CLongBinary`数据值。 该操作可能失败，因为不会预分配全局内存块。  
  
- **AFX_SQL_ERROR_RECORDSET_READONLY**试图更新只读的记录集，或者数据源是只读的。 可以使用该记录执行任何更新操作或`CDatabase`与之关联的对象。  
  
- **SQL_ERROR**函数失败。 由 ODBC 函数返回的错误消息**SQLError**存储在**m_strError**数据成员。  
  
- **SQL_INVALID_HANDLE**函数失败，由于无效的环境句柄、 连接句柄或语句句柄。 这指示编程错误。 无附加信息可从 ODBC 函数**SQLError**。  
  
 由 ODBC 定义的 SQL 前缀代码。 AFXDB 中定义的由 AFX 前缀代码。H、 在 MFC\INCLUDE 中找到。  
  
##  <a name="a-namemstrerrora--cdbexceptionmstrerror"></a><a name="m_strerror"></a>CDBException::m_strError  
 包含描述导致了异常的错误的字符串。  
  
### <a name="remarks"></a>备注  
 该字符串在字母数字术语中描述的错误。 有关详细信息和示例，请参阅**m_strStateNativeOrigin**。  
  
##  <a name="a-namemstrstatenativeorigina--cdbexceptionmstrstatenativeorigin"></a><a name="m_strstatenativeorigin"></a>CDBException::m_strStateNativeOrigin  
 包含描述导致了异常的错误的字符串。  
  
### <a name="remarks"></a>备注  
 该字符串采用的窗体"状态: %s，本机: %ld，来源: %s"，其中的格式代码，按顺序，将替换为描述的值︰  
  
-   **SQLSTATE**、 以 null 结尾的字符串，包含在中返回的五个字符的错误代码*szSqlState* ODBC 函数的参数**SQLError**。 **SQLSTATE**附录 A 列出了值[ODBC 错误代码](https://msdn.microsoft.com/library/ms714687.aspx)，请在*ODBC 程序员参考*。 示例:"S0022"。  
  
-   返回特定于数据源中，本机错误代码，以*pfNativeError*参数**SQLError**函数。 示例︰ 207。  
  
-   在中返回的错误消息文本*szErrorMsg*参数**SQLError**函数。 此消息包含多个用括号括起来的名称。 向用户从其源传递错误，因为每个 ODBC 组件 （数据源、 驱动程序，驱动程序管理器） 将追加其自己的名称。 此信息可帮助找出错误的来源。 示例: [Microsoft] [ODBC SQL Server Driver] [SQL Server]  
  
 框架解释的错误字符串，并将其组件都进入**m_strStateNativeOrigin**; 如果**m_strStateNativeOrigin**包含信息的多个错误，这些错误由换行符分隔。 框架将放入的字母数字错误文本**m_strError**。  
  
 有关用于对此字符串组成的代码的其他信息，请参阅[SQLError](https://msdn.microsoft.com/library/ms716312.aspx) ，此功能在*ODBC 程序员参考*。  
  
### <a name="example"></a>示例  
  ODBC︰ 从"状态︰ S0022、 本机︰&207;、 原点: [Microsoft] [ODBC SQL Server Driver] [SQL Server] 无效的列名称 ColName"  
  
 在**m_strStateNativeOrigin**:"状态︰ S0022、 本机︰&207;、 原点: [Microsoft] [ODBC SQL Server Driver] [SQL Server]"  
  
 在**m_strError**:"无效的列 ColName name"  
  
## <a name="see-also"></a>另请参阅  
 [CException 类](../../mfc/reference/cexception-class.md)   
 [层次结构图](../../mfc/hierarchy-chart.md)   
 [CDatabase 类](../../mfc/reference/cdatabase-class.md)   
 [CRecordset 类](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange 类](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::Update](../../mfc/reference/crecordset-class.md#update)   
 [CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)   
 [CException 类](../../mfc/reference/cexception-class.md)

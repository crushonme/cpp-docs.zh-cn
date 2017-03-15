---
title: "CAtlTransactionManager 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlTransactionManager
- atltransactionmanager/ATL::CAtlTransactionManager
dev_langs:
- C++
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
caps.latest.revision: 25
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
ms.openlocfilehash: bc6162eaf1a4c8c3848a32e861019ff50e4f850c
ms.lasthandoff: 02/24/2017

---
# <a name="catltransactionmanager-class"></a>CAtlTransactionManager 类
CAtlTransactionManager 类提供了对内核事务管理器 (KTM) 函数的包装。  
  
> [!IMPORTANT]
>  不能在 Windows 运行时中执行的应用程序中使用此类及其成员。  
  
## <a name="syntax"></a>语法  
  
```
class CAtlTransactionManager;
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[~ CAtlTransactionManager](#dtor)|CAtlTransactionManager 析构函数。|  
|[CAtlTransactionManager](#catltransactionmanager)|CAtlTransactionManager 构造函数。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|说明|  
|----------|-----------------|  
|[关闭](#close)|关闭其中一个的事务句柄。|  
|[提交](#commit)|该事务被提交请求。|  
|[创建](#create)|创建的事务句柄。|  
|[CreateFile](#createfile)|创建或打开文件、 文件流或事务处理操作的目录。|  
|[DeleteFile](#deletefile)|作为事务处理操作中删除现有文件。|  
|[FindFirstFile](#findfirstfile)|目录中搜索的文件或子目录作为事务处理操作。|  
|[GetFileAttributes](#getfileattributes)|事务处理操作的形式检索指定的文件或目录的文件系统属性。|  
|[GetFileAttributesEx](#getfileattributesex)|事务处理操作的形式检索指定的文件或目录的文件系统属性。|  
|[GetHandle](#gethandle)|返回事务句柄。|  
|[IsFallback](#isfallback)|确定是否启用回退调用。|  
|[MoveFile](#movefile)|将移动现有的文件或目录，包括其子项，作为事务处理操作。|  
|[RegCreateKeyEx](#regcreatekeyex)|创建指定的注册表项并将其与事务相关联。 如果键已存在，该函数将打开它。|  
|[RegDeleteKey](#regdeletekey)|事务处理操作的形式从注册表的指定特定于平台的视图中删除子项和它的值。|  
|[RegOpenKeyEx](#regopenkeyex)|打开指定的注册表项并将其与事务相关联。|  
|[回滚](#rollback)|事务被回滚的请求。|  
|[SetFileAttributes](#setfileattributes)|将文件或目录的属性设置为事务处理操作。|  
  
### <a name="protected-data-members"></a>受保护的数据成员  
  
|名称|说明|  
|----------|-----------------|  
|[m_bFallback](#m_bfallback)|`TRUE`如果支持这种回退;`FALSE`否则为。|  
|[m_hTransaction](#m_htransaction)|事务句柄。|  
  
## <a name="remarks"></a>备注  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)  
  
## <a name="requirements"></a>要求  
 **标头︰** atltransactionmanager.h  
  
##  <a name="a-namedtora--catltransactionmanager"></a><a name="dtor"></a>~ CAtlTransactionManager  
 CAtlTransactionManager 析构函数。  
  
```
virtual ~CAtlTransactionManager();
```  
  
### <a name="remarks"></a>备注  
 在正常处理中，已自动提交事务，并关闭。 如果异常展开期间调用的析构函数，则回滚该事务并将其关闭。  
  
##  <a name="a-namecatltransactionmanagera--catltransactionmanager"></a><a name="catltransactionmanager"></a>CAtlTransactionManager  
 CAtlTransactionManager 构造函数。  
  
```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```  
  
### <a name="parameters"></a>参数  
 `bFallback`  
 `TRUE`指示支持回退。 如果事务处理的函数失败，类会自动调用"非事务性"函数。 `FALSE`指示没有"回退"的调用。  
  
 `bAutoCreateTransaction`  
 `TRUE`指示在构造函数中自动创建的事务处理。 `FALSE`指示不是。  
  
### <a name="remarks"></a>备注  
  
##  <a name="a-nameclosea--close"></a><a name="close"></a>关闭  
 关闭事务句柄。  
  
```
inline BOOL Close();
```  
  
### <a name="return-value"></a>返回值  
 如果成功，则为 `TRUE`；否则为 `FALSE`。  
  
### <a name="remarks"></a>备注  
 此包装器将调用`CloseHandle`函数。 自动的析构函数中调用该方法。  
  
##  <a name="a-namecommita--commit"></a><a name="commit"></a>提交  
 该事务被提交请求。  
  
```
inline BOOL Commit();
```  
  
### <a name="return-value"></a>返回值  
 如果成功，则为 `TRUE`；否则为 `FALSE`。  
  
### <a name="remarks"></a>备注  
 此包装器将调用`CommitTransaction`函数。 自动的析构函数中调用该方法。  
  
##  <a name="a-namecreatea--create"></a><a name="create"></a>创建  
 创建的事务句柄。  
  
```
inline BOOL Create();
```  
  
### <a name="return-value"></a>返回值  
 如果成功，则为 `TRUE`；否则为 `FALSE`。  
  
### <a name="remarks"></a>备注  
 此包装器将调用`CreateTransaction`函数。 检查其用于  
  
##  <a name="a-namecreatefilea--createfile"></a><a name="createfile"></a>CreateFile  
 创建或打开文件、 文件流或事务处理操作的目录。  
  
```
inline HANDLE CreateFile(
  LPCTSTR lpFileName,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes,
    HANDLE hTemplateFile);
```  
  
### <a name="parameters"></a>参数  
 `lpFileName`  
 要创建或打开的对象的名称。  
  
 `dwDesiredAccess`  
 对该对象，可归纳如下读取、 写入、 二者，还是均不 （零） 的访问。 最常使用的值为 GENERIC_READ 和 / 或 GENERIC_WRITE，︰ GENERIC_READ |GENERIC_WRITE。  
  
 `dwShareMode`  
 一个对象，它可以是读取、 写入、 同时，删除，所有这些，或无共享模式︰ 0、 FILE_SHARE_DELETE、 FILE_SHARE_READ、 FILE_SHARE_WRITE。  
  
 `lpSecurityAttributes`  
 指向一个 SECURITY_ATTRIBUTES 结构，其中包含可选的安全描述符，并且还确定可以由子进程继承返回的句柄的指针。 该参数可以是`NULL`。  
  
 `dwCreationDisposition`  
 要对存在，并且不存在的文件执行的操作。 此参数必须是不能结合使用的以下值之一︰ CREATE_ALWAYS、 CREATE_NEW、 OPEN_ALWAYS、 OPEN_EXISTING 或 TRUNCATE_EXISTING。  
  
 `dwFlagsAndAttributes`  
 文件属性和标志中。 此参数可以包括可用的文件属性 （FILE_ATTRIBUTE_ *） 中的任意组合。 所有其他文件属性重写 FILE_ATTRIBUTE_NORMAL。 此参数还可以包含标志的组合 (FILE_FLAG_\*) 控制缓冲行为，访问模式，以及其他特殊用途的标志。 它们与任何 FILE_ATTRIBUTE_ 结合\*值。  
  
 `hTemplateFile`  
 GENERIC_READ 访问权限的模板文件有效句柄。 模板文件中提供的文件属性和为其创建的文件的扩展的属性。 此参数可以为 `NULL`。  
  
### <a name="return-value"></a>返回值  
 返回可用来访问该对象的句柄。  
  
### <a name="remarks"></a>备注  
 此包装器将调用`CreateFileTransacted`函数。  
  
##  <a name="a-namedeletefilea--deletefile"></a><a name="deletefile"></a>DeleteFile  
 作为事务处理操作中删除现有文件。  
  
```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>参数  
 `lpFileName`  
 要删除的文件的名称。  
  
### <a name="remarks"></a>备注  
 此包装器将调用`DeleteFileTransacted`函数。  
  
##  <a name="a-namefindfirstfilea--findfirstfile"></a><a name="findfirstfile"></a>FindFirstFile  
 目录中搜索的文件或子目录作为事务处理操作。  
  
```
inline HANDLE FindFirstFile(
  LPCTSTR lpFileName,
  WIN32_FIND_DATA* pNextInfo);
```  
  
### <a name="parameters"></a>参数  
 `lpFileName`  
 目录或路径和要搜索的文件名称。 此参数可以包含通配符，如星号 （*） 或一个问号 （）。  
  
 `pNextInfo`  
 指向接收找到的文件或子目录的相关信息的 WIN32_FIND_DATA 结构的指针。  
  
### <a name="return-value"></a>返回值  
 如果函数成功，返回值是在后续调用中使用的搜索句柄`FindNextFile`或`FindClose`。 如果函数失败，或找不到文件中的搜索字符串从`lpFileName`参数，则返回值为 INVALID_HANDLE_VALUE。  
  
### <a name="remarks"></a>备注  
 此包装器将调用`FindFirstFileTransacted`函数。  
  
##  <a name="a-namegetfileattributesa--getfileattributes"></a><a name="getfileattributes"></a>GetFileAttributes  
 事务处理操作的形式检索指定的文件或目录的文件系统属性。  
  
```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>参数  
 `lpFileName`  
 文件或目录的名称。  
  
### <a name="remarks"></a>备注  
 此包装器将调用`GetFileAttributesTransacted`函数。  
  
##  <a name="a-namegetfileattributesexa--getfileattributesex"></a><a name="getfileattributesex"></a>GetFileAttributesEx  
 事务处理操作的形式检索指定的文件或目录的文件系统属性。  
  
```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```  
  
### <a name="parameters"></a>参数  
 `lpFileName`  
 文件或目录的名称。  
  
 `fInfoLevelId`  
 要检索的属性信息的级别。  
  
 `lpFileInformation`  
 指向接收的属性信息的缓冲区的指针。 到此缓冲区中存储的属性信息的类型的值由`fInfoLevelId`。 如果`fInfoLevelId`参数是 GetFileExInfoStandard，则此参数指向 WIN32_FILE_ATTRIBUTE_DATA 结构。  
  
### <a name="remarks"></a>备注  
 此包装器将调用`GetFileAttributesTransacted`函数。  
  
##  <a name="a-namegethandlea--gethandle"></a><a name="gethandle"></a>GetHandle  
 返回事务句柄。  
  
```
HANDLE GetHandle() const;
```  
  
### <a name="return-value"></a>返回值  
 返回一个类的事务句柄。 返回`NULL`如果`CAtlTransactionManager`未附加到一个句柄。  
  
### <a name="remarks"></a>备注  
  
##  <a name="a-nameisfallbacka--isfallback"></a><a name="isfallback"></a>IsFallback  
 确定是否启用回退调用。  
  
```
BOOL IsFallback() const;
```  
  
### <a name="return-value"></a>返回值  
 返回`TRUE`是该类支持回退调用。 否则为 `FALSE`。  
  
### <a name="remarks"></a>备注  
  
##  <a name="a-namembfallbacka--mbfallback"></a><a name="m_bfallback"></a>m_bFallback  
 `TRUE`如果支持这种回退;`FALSE`否则为。  
  
```
BOOL m_bFallback;
```  
  
### <a name="remarks"></a>备注  
  
##  <a name="a-namemhtransactiona--mhtransaction"></a><a name="m_htransaction"></a>m_hTransaction  
 事务句柄。  
  
```
HANDLE m_hTransaction;
```  
  
### <a name="remarks"></a>备注  
  
##  <a name="a-namemovefilea--movefile"></a><a name="movefile"></a>MoveFile  
 将移动现有的文件或目录，包括其子项，作为事务处理操作。  
  
```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```  
  
### <a name="parameters"></a>参数  
 `lpOldFileName`  
 当前的现有文件或本地计算机上的目录名称。  
  
 `lpNewFileName`  
 文件或目录的新名称。 不能已存在此名称。 一个新的文件可能在不同的文件系统或驱动器上。 一个新的目录必须位于同一个驱动器上。  
  
### <a name="remarks"></a>备注  
 此包装器将调用`MoveFileTransacted`函数。  
  
##  <a name="a-nameregcreatekeyexa--regcreatekeyex"></a><a name="regcreatekeyex"></a>RegCreateKeyEx  
 创建指定的注册表项并将其与事务相关联。 如果键已存在，该函数将打开它。  
  
```
inline LSTATUS RegCreateKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD dwReserved,
    LPTSTR lpClass,
    DWORD dwOptions,
    REGSAM samDesired,
    CONST LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    PHKEY phkResult,
    LPDWORD lpdwDisposition);
```  
  
### <a name="parameters"></a>参数  
 `hKey`  
 打开注册表项句柄。  
  
 `lpSubKey`  
 此函数将打开或创建的子项的名称。  
  
 `dwReserved`  
 此参数是保留，必须为零。  
  
 `lpClass`  
 此密钥的用户定义的类。 可能会忽略此参数。 此参数可以为 NULL。  
  
 `dwOptions`  
 此参数可以为下列值之一︰ REG_OPTION_BACKUP_RESTORE、 REG_OPTION_NON_VOLATILE 或 REG_OPTION_VOLATILE。  
  
 `samDesired`  
 一个指定密钥的访问权限的掩码。  
  
 `lpSecurityAttributes`  
 指向 SECURITY_ATTRIBUTES 结构，它确定是否可以由子进程继承返回的句柄的指针。 如果`lpSecurityAttributes`是`NULL`，不能继承句柄。  
  
 `phkResult`  
 指向一个变量来接收已打开或创建密钥的句柄的指针。 如果密钥不是预定义的注册表项之一，调用`RegCloseKey`函数使用此句柄之后。  
  
 `lpdwDisposition`  
 指向一个变量来接收下列处置值之一︰ REG_CREATED_NEW_KEY 或 REG_OPENED_EXISTING_KEY。  
  
### <a name="return-value"></a>返回值  
 如果函数成功，返回值将为 ERROR_SUCCESS。 如果函数失败，则返回值是在 Winerror.h 中定义的非零错误代码。  
  
### <a name="remarks"></a>备注  
 此包装器将调用`RegCreateKeyTransacted`函数。  
  
##  <a name="a-nameregdeletekeya--regdeletekey"></a><a name="regdeletekey"></a>RegDeleteKey  
 事务处理操作的形式从注册表的指定特定于平台的视图中删除子项和它的值。  
  
```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```  
  
### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|`hKey`|打开注册表项句柄。|  
|`lpSubKey`|要删除的密钥的名称。|  
  
### <a name="return-value"></a>返回值  
 如果函数成功，返回值将为 ERROR_SUCCESS。 如果函数失败，则返回值是在 Winerror.h 中定义的非零错误代码。  
  
### <a name="remarks"></a>备注  
 此包装器将调用`RegDeleteKeyTransacted`函数。  
  
##  <a name="a-nameregopenkeyexa--regopenkeyex"></a><a name="regopenkeyex"></a>RegOpenKeyEx  
 打开指定的注册表项并将其与事务相关联。  
  
```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```  
  
### <a name="parameters"></a>参数  
 `hKey`  
 打开注册表项句柄。  
  
 `lpSubKey`  
 要打开的注册表子项的名称。  
  
 `ulOptions`  
 此参数是保留，必须为零。  
  
 `samDesired`  
 一个指定密钥的访问权限的掩码。  
  
 `phkResult`  
 指向一个变量来接收已打开或创建密钥的句柄的指针。 如果密钥不是预定义的注册表项之一，调用`RegCloseKey`函数使用此句柄之后。  
  
### <a name="return-value"></a>返回值  
 如果函数成功，返回值将为 ERROR_SUCCESS。 如果函数失败，返回值是在 Winerror.h 中定义的非零错误代码  
  
### <a name="remarks"></a>备注  
 此包装器将调用`RegOpenKeyTransacted`函数。  
  
##  <a name="a-namerollbacka--rollback"></a><a name="rollback"></a>回滚  
 事务被回滚的请求。  
  
```
inline BOOL Rollback();
```  
  
### <a name="return-value"></a>返回值  
 如果成功，则为 `TRUE`；否则为 `FALSE`。  
  
### <a name="remarks"></a>备注  
 此包装器将调用`RollbackTransaction`函数。  
  
##  <a name="a-namesetfileattributesa--setfileattributes"></a><a name="setfileattributes"></a>SetFileAttributes  
 将文件或目录的属性设置为事务处理操作。  
  
```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```  
  
### <a name="parameters"></a>参数  
 `lpFileName`  
 文件或目录的名称。  
  
 `dwAttributes`  
 要为文件设置的文件属性。 有关详细信息，请参阅[SetFileAttributesTransacted](http://go.microsoft.com/fwlink/linkid=158699)。  
  
### <a name="remarks"></a>备注  
 此包装器将调用`SetFileAttributesTransacted`函数。  
  
## <a name="see-also"></a>另请参阅  
 [ATL COM 桌面组件](../../atl/atl-com-desktop-components.md)

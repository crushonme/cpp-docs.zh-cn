---
title: "_CrtDoForAllClientObjects | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtDoForAllClientObjects
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
dev_langs: C++
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dff8b99d6378928583cea0c5eec7d69130c56557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects
为堆中的所有 `_CLIENT_BLOCK` 类型调用应用程序提供的函数（仅限调试版本）。  
  
## <a name="syntax"></a>语法  
  
```  
void _CrtDoForAllClientObjects(   
   void ( * pfn )( void *, void * ),  
   void *context  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pfn`  
 指向应用程序提供的函数回调函数的指针。 此函数的第一个参数指向数据。 第二个参数是传递给对 `_CrtDoForAllClientObjects`的调用的上下文指针。  
  
 `context`  
 指向要传递给应用程序提供的函数的应用程序提供的上下文的指针。  
  
## <a name="remarks"></a>备注  
 `_CrtDoForAllClientObjects` 在堆链接列表中搜索具有 `_CLIENT_BLOCK` 类型的内存块，当找到此类型的块时，将调用应用程序提供的函数。 找到的块和 `context` 参数将作为参数传递给应用程序提供的函数。 在调试过程中，应用程序可以通过显式调用调试堆函数以分配内存并指定向块分配 `_CLIENT_BLOCK` 块类型，来跟踪一组特定分配。 然后，可以在泄露检测和内存状态报告期间，单独跟踪并分别报告这些块。  
  
 如果未出现 `_CRTDBG_ALLOC_MEM_DF` 标志的 [_CRTDBG_ALLOC_MEM_DF](../../c-runtime-library/crtdbgflag.md) 位域，则会立即返回 `_CrtDoForAllClientObjects` 。 未定义 [_DEBUG](../../c-runtime-library/debug.md) 时，会在预处理过程中删除对 `_CrtDoForAllClientObjects` 的调用。  
  
 有关 `_CLIENT_BLOCK` 类型以及其他调试函数如何使用它的详细信息，请参阅 [Types of blocks on the debug heap](/visualstudio/debugger/crt-debug-heap-details)的调用的上下文指针。 有关如何在基堆的调试版本中分配、初始化和管理内存块的信息，请参阅 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)。  
  
 如果 `pfn` 为 `NULL`，则会调用无效的参数处理程序，如 [Parameter Validation](../../c-runtime-library/parameter-validation.md)的调用的上下文指针。 如果允许执行继续，则将 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 设置为 `EINVAL` 并返回该函数。  
  
## <a name="requirements"></a>惠?  
  
|例程所返回的值|必需的标头|  
|-------------|---------------------|  
|`_CrtDoForAllClientObjects`|\<crtdbg.h>、\<errno.h>|  
  
 有关更多兼容性信息，请参见“简介”中的 [兼容性](../../c-runtime-library/compatibility.md) 。  
  
 **库：** 仅限通用 C 运行时库的调试版本。  
  
## <a name="see-also"></a>请参阅  
 [调试例程](../../c-runtime-library/debug-routines.md)   
 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)   
 [堆状态报告函数](/visualstudio/debugger/crt-debug-heap-details)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)
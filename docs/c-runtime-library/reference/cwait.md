---
title: "_cwait | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _cwait
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords: _cwait
dev_langs: C++
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 817b8ef39758a47fe28a3a2e2320ae7384a2bc86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="cwait"></a>_cwait
请等待，直到另一个进程终止。  
  
> [!IMPORTANT]
>  此 API 不能用于在 Windows 运行时中执行的应用程序。 有关详细信息，请参阅 [/ZW 不支持的 CRT 函数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)。  
  
## <a name="syntax"></a>语法  
  
```  
intptr_t _cwait(   
   int *termstat,  
   intptr_t procHandle,  
   int action   
);  
```  
  
#### <a name="parameters"></a>参数  
 `termstat`  
 指向将存储指定进程的结果代码的缓冲区的指针或 NULL。  
  
 `procHandle`  
 要等待的进程的句柄（即在 `_cwait` 可以返回之前必须终止的进程）。  
  
 `action`  
 NULL：Windows 操作系统应用程序将忽略它；对于其他应用程序：要在 `procHandle` 上执行的操作代码。  
  
## <a name="return-value"></a>返回值  
 成功完成指定的进程后，将返回指定进程的句柄并将 `termstat` 设置为由该指定的进程返回的结果代码。 否则为返回-1 并设置`errno`，如下所示。  
  
|“值”|描述|  
|-----------|-----------------|  
|`ECHILD`|指定的进程不存在、`procHandle` 无效或调用 [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx) 或 [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx) API 失败。|  
|`EINVAL`|`action` 无效。|  
  
 有关这些代码及其他返回代码的详细信息，请参阅 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。  
  
## <a name="remarks"></a>备注  
 `_cwait` 函数等待由 `procHandle` 提供的指定进程的进程 ID 终止。 传递给 `_cwait` 的 `procHandle` 的值应该是由对创建指定进程的 [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) 函数的调用返回的值。 如果进程 ID 在调用 `_cwait` 前终止，则 `_cwait` 将立即返回。 任何进程都可使用 `_cwait` 等待任何其他已知的存在有效句柄 (`procHandle`) 的进程。  
  
 `termstat` 指向将存储指定进程的返回代码的缓冲区。 `termstat` 的值指示是否通过调用 Windows [ExitProcess](http://msdn.microsoft.com/library/windows/desktop/ms682658.aspx) API 正常终止了指定进程。 如果指定进程调用 `ExitProcess` 或 `exit`、从 `_exit` 中返回，或到达 `main` 的末尾，则将在内部调用 `main`。 有关通过 `termstat` 传回的值的详细信息，请参阅 [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx)。 如果使用 `_cwait` 的 NULL 值调用 `termstat`，则不会存储指定进程的返回代码。  
  
 因为这些环境中没有实现父子关系，因此 Windows 操作系统会忽略 `action` 参数。  
  
 除非 `procHandle` 是 -1 或 -2（当前进程或线程的句柄），否则将关闭句柄。 因此，在这种情况下，请不要使用返回的句柄。  
  
## <a name="requirements"></a>惠?  
  
|例程所返回的值|必需的标头|可选标头|  
|-------------|---------------------|---------------------|  
|`_cwait`|\<process.h>|\<errno.h>|  
  
 有关更多兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="example"></a>示例  
  
```C  
// crt_cwait.c  
// compile with: /c  
// This program launches several processes and waits  
// for a specified process to finish.  
  
#define _CRT_RAND_S  
  
#include <windows.h>  
#include <process.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <time.h>  
  
// Macro to get a random integer within a specified range  
#define getrandom( min, max ) (( (rand_s (&number), number) % (int)((( max ) + 1 ) - ( min ))) + ( min ))  
  
struct PROCESS  
{  
   int     nPid;  
   char    name[40];  
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };  
  
int main( int argc, char *argv[] )  
{  
   int termstat, c;  
   unsigned int number;  
  
   srand( (unsigned)time( NULL ) );    // Seed randomizer  
  
   // If no arguments, this is the calling process  
   if ( argc == 1 )  
   {  
      // Spawn processes in numeric order  
      for ( c = 0; c < 4; c++ ) {  
         _flushall();  
         process[c].nPid = _spawnl( _P_NOWAIT, argv[0], argv[0],   
                                    process[c].name, NULL );  
      }  
  
      // Wait for randomly specified process, and respond when done   
      c = getrandom( 0, 3 );  
      printf( "Come here, %s.\n", process[c].name );  
      _cwait( &termstat, process[c].nPid, _WAIT_CHILD );  
      printf( "Thank you, %s.\n", process[c].name );  
  
   }  
   // If there are arguments, this must be a spawned process   
   else  
   {  
      // Delay for a period that's determined by process number  
      Sleep( (argv[1][0] - 'A' + 1) * 1000L );  
      printf( "Hi, Dad. It's %s.\n", argv[1] );  
   }  
}  
```  
  
```Output  
Hi, Dad. It's Ann.  
Come here, Ann.  
Thank you, Ann.  
Hi, Dad. It's Beth.  
Hi, Dad. It's Carl.  
Hi, Dad. It's Dave.  
```  
  
## <a name="see-also"></a>请参阅  
 [进程和环境控制](../../c-runtime-library/process-and-environment-control.md)   
 [_spawn、_wspawn 函数](../../c-runtime-library/spawn-wspawn-functions.md)
---
title: "_getdrive | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _getdrive
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getdrive
- getdrive
dev_langs: C++
helpviewer_keywords:
- current disk drive
- getdrive function
- disk drives
- _getdrive function
ms.assetid: e40631a0-8f1a-4897-90ac-e1037ff30bca
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 05862a7506b58b7038b3e079cbc48d72175a4ba5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="getdrive"></a>_getdrive
获取当前磁盘驱动器。  
  
> [!IMPORTANT]
>  此 API 不能用于在 Windows 运行时中执行的应用程序。 有关详细信息，请参阅 [/ZW 不支持的 CRT 函数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)。  
  
## <a name="syntax"></a>语法  
  
```  
int _getdrive( void );  
```  
  
## <a name="return-value"></a>返回值  
 返回当前（默认）驱动器（1=A，2=B，依此类推）。 无错误返回。  
  
## <a name="requirements"></a>惠?  
  
|例程所返回的值|必需的标头|  
|-------------|---------------------|  
|`_getdrive`|\<direct.h>|  
  
 有关更多兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="example"></a>示例  
  
```  
// crt_getdrive.c  
// compile with: /c  
// Illustrates drive functions including:  
//    _getdrive       _chdrive        _getdcwd  
//  
  
#include <stdio.h>  
#include <direct.h>  
#include <stdlib.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch, drive, curdrive;  
   static char path[_MAX_PATH];  
  
   // Save current drive.  
   curdrive = _getdrive();  
  
   printf( "Available drives are:\n" );  
  
   // If we can switch to the drive, it exists.  
   for( drive = 1; drive <= 26; drive++ )  
   {  
      if( !_chdrive( drive ) )  
      {  
         printf( "%c:", drive + 'A' - 1 );  
         if( _getdcwd( drive, path, _MAX_PATH ) != NULL )  
            printf( " (Current directory is %s)", path );  
         putchar( '\n' );  
      }  
   }  
  
   // Restore original drive.  
   _chdrive( curdrive );  
}  
```  
  
```Output  
Available drives are:  
A: (Current directory is A:\)  
C: (Current directory is C:\)  
E: (Current directory is E:\testdir\bin)  
F: (Current directory is F:\)  
G: (Current directory is G:\)  
```  
  
## <a name="see-also"></a>请参阅  
 [目录控制](../../c-runtime-library/directory-control.md)   
 [_chdrive](../../c-runtime-library/reference/chdrive.md)   
 [_getcwd、_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdcwd、_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)
---
title: "_isatty | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _isatty
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords: _isatty
dev_langs: C++
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e3c845cf9fc1fec0031ebca94e65ef82445fdff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="isatty"></a>_isatty
确定一个文件描述符是否与字符设备相关联。  
  
## <a name="syntax"></a>语法  
  
```  
  
      int _isatty(  
int fd   
);  
```  
  
#### <a name="parameters"></a>参数  
 `fd`  
 引用设备以进行测试的文件说明符。  
  
## <a name="return-value"></a>返回值  
 如果描述符与字符设备相关联，则 `_isatty` 会返回一个非零值。 否则，`_isatty` 返回 0。  
  
## <a name="remarks"></a>备注  
 `_isatty` 函数将确定 `fd` 是否与字符设备（终端、控制台、打印机或串行端口）相关联。  
  
 此函数验证 `fd` 参数。 如果 `fd` 是错误的文件指针，则调用无效的参数处理程序，如[参数验证](../../c-runtime-library/parameter-validation.md)中所述。 如果允许执行继续，则该函数将返回 0 并将 `errno` 设置为 `EBADF`。  
  
## <a name="requirements"></a>惠?  
  
|例程所返回的值|必需的标头|  
|-------------|---------------------|  
|`_isatty`|\<io.h>|  
  
 有关更多兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="libraries"></a>库  
 [C 运行时库](../../c-runtime-library/crt-library-features.md)的所有版本。  
  
## <a name="example"></a>示例  
  
```  
// crt_isatty.c  
/* This program checks to see whether  
 * stdout has been redirected to a file.  
 */  
  
#include <stdio.h>  
#include <io.h>  
  
int main( void )  
{  
   if( _isatty( _fileno( stdout ) ) )  
      printf( "stdout has not been redirected to a file\n" );  
   else  
      printf( "stdout has been redirected to a file\n");  
}  
```  
  
## <a name="sample-output"></a>示例输出  
  
```  
stdout has not been redirected to a file  
```  
  
## <a name="see-also"></a>请参阅  
 [文件处理](../../c-runtime-library/file-handling.md)
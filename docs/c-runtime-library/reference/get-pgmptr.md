---
title: "_get_pgmptr | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_pgmptr
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_pgmptr
- _get_pgmptr
dev_langs:
- C++
helpviewer_keywords:
- get_pgmptr function
- _get_pgmptr function
- pgmptr global variable
- _pgmptr global variable
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7dffbed5be8284949e7dbe20b35f64898ae98729
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2018
---
# <a name="getpgmptr"></a>_get_pgmptr
获取 `_pgmptr` 全局变量的当前值。  
  
## <a name="syntax"></a>语法  
  
```  
errno_t _get_pgmptr(   
   char **pValue   
);  
```  
  
#### <a name="parameters"></a>参数  
 [out] `pValue`  
 指向要填充 `_pgmptr` 变量当前值的字符串的指针。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回零；如果失败，则返回错误代码。 如果 `pValue` 为 `NULL`，则将调用无效参数处理程序，如[参数验证](../../c-runtime-library/parameter-validation.md)中所述。 如果允许执行继续，则该函数将 `errno` 设置为 `EINVAL` 并返回 `EINVAL`。  
  
## <a name="remarks"></a>备注  
 只能调用`_get_pgmptr`如果你的程序包含窄的入口点，例如`main()`或`WinMain()`。 `_pgmptr`全局变量包含与进程关联的可执行文件的完整路径。 有关详细信息，请参阅 [_pgmptr、_wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md)。  
  
## <a name="requirements"></a>惠?  
  
|例程所返回的值|必需的标头|  
|-------------|---------------------|  
|`_get_pgmptr`|\<stdlib.h>|  
  
 有关更多兼容性信息，请参见“简介”中的 [兼容性](../../c-runtime-library/compatibility.md) 。  
  
## <a name="see-also"></a>请参阅  
 [_get_wpgmptr](../../c-runtime-library/reference/get-wpgmptr.md)

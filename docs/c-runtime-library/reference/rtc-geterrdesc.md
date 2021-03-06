---
title: "_RTC_GetErrDesc | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _RTC_GetErrDesc
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
- RTC_GetErrDesc
- _RTC_GetErrDesc
dev_langs: C++
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3149c1be671566785f67963368a50cdf2eee3809
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="rtcgeterrdesc"></a>_RTC_GetErrDesc
返回运行时错误检查 (RTC) 类型的简要描述。  
  
## <a name="syntax"></a>语法  
  
```  
  
      const char * _RTC_GetErrDesc(  
   _RTC_ErrorNumber errnum   
);  
```  
  
#### <a name="parameters"></a>参数  
 *errnum*  
 一个数字，介于 0 和 `_RTC_NumErrors`返回的值减 1 所得的值之间。  
  
## <a name="return-value"></a>返回值  
 一个字符串，其中包含由运行时错误检查系统检测到的一个错误类型的简短描述。 如果错误小于 0 或大于等于 [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md) 返回的值，则 `_RTC_GetErrDesc` 将返回 NULL。  
  
## <a name="requirements"></a>惠?  
  
|例程所返回的值|必需的标头|  
|-------------|---------------------|  
|`_RTC_GetErrDesc`|\<rtcapi.h>|  
  
 有关详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="libraries"></a>库  
 [C 运行时库](../../c-runtime-library/crt-library-features.md)的所有版本。  
  
## <a name="see-also"></a>请参阅  
 [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)   
 [运行时错误检查](../../c-runtime-library/run-time-error-checking.md)
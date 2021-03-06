---
title: "__max | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __max
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
- max
- __max
dev_langs: C++
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 585d2a295bedb8b0ba49a893d5089bc682a1debd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="max"></a>__max
返回两个值中的较大者。  
  
## <a name="syntax"></a>语法  
  
```  
type __max(  
   type a,  
   type b   
);  
```  
  
#### <a name="parameters"></a>参数  
 `type`  
 任何数字数据类型。  
  
 `a, b`  
 要比较的任何数字类型的值。  
  
## <a name="return-value"></a>返回值  
 `__max` 将返回其参数中的较大者。  
  
## <a name="remarks"></a>备注  
 `__max` 宏会将两个值进行比较并返回其中的较大者。 参数可以是任何数字数据类型，有符号或无符号均可。 两个自变量以及返回值必须是同一数据类型。  
  
## <a name="requirements"></a>惠?  
  
|例程所返回的值|必需的标头|  
|-------------|---------------------|  
|`__max`|\<stdlib.h>|  
  
## <a name="example"></a>示例  
 有关详细信息，请参阅 [__min](../../c-runtime-library/reference/min.md) 中的示例。  
  
## <a name="see-also"></a>请参阅  
 [浮点支持](../../c-runtime-library/floating-point-support.md)   
 [__min](../../c-runtime-library/reference/min.md)
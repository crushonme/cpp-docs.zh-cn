---
title: "tolower、_tolower、towlower、_tolower_l、_towlower_l | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _tolower_l
- towlower
- tolower
- _tolower
- _towlower_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _totlower
- tolower
- _tolower
- towlower
dev_langs: C++
helpviewer_keywords:
- tolower_l function
- _tolower_l function
- totlower function
- string conversion, to different characters
- lowercase, converting to
- tolower function
- string conversion, case
- towlower function
- _tolower function
- _totlower function
- towlower_l function
- case, converting
- characters, converting
- _towlower_l function
ms.assetid: 86e0fc02-94ae-4472-9631-bf8e96f67b92
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7fe06748a6e349f612fdf564c9aed917e43f164b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="tolower-tolower-towlower-tolowerl-towlowerl"></a>tolower、_tolower、towlower、_tolower_l、_towlower_l
将字符转换为小写。  
  
## <a name="syntax"></a>语法  
  
```  
int tolower(  
   int c   
);  
int _tolower(  
   int c   
);  
int towlower(  
   wint_t c   
);  
int _tolower_l(  
   int c,  
   _locale_t locale   
);  
int _towlower_l(  
   wint_t c,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>参数  
 [in] `c`  
 要转换的字符。  
  
 [in] `locale`  
 用于特定区域设置翻译的区域设置。  
  
## <a name="return-value"></a>返回值  
 如果转换可行，则其中的各个例程将 `c` 的副本转换为小写，并返回结果。 没有保留任何返回值以指示错误。  
  
## <a name="remarks"></a>备注  
 如果可行且相关，则其中的各个例程将指定大写字母转换为小写字母。 `towlower` 的大小写转换是特定于区域设置的。 只改变与当前区域设置相关的字符的大小写。 没有 `_l` 后缀的函数使用当前设置的区域设置。 这些带有 `_l` 后缀的函数的版本将区域设置用作参数并使用它，而不是使用当前设置的区域设置。 有关详细信息，请参阅 [Locale](../../c-runtime-library/locale.md)。  
  
 若要使 `_tolower` 提供预期结果，[__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) 和 [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) 必须均返回非零值。  
  
### <a name="generic-text-routine-mappings"></a>一般文本例程映射  
  
|TCHAR.H 例程|未定义 _UNICODE 和 _MBCS|已定义 _MBCS|已定义 _UNICODE|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_totlower`|`tolower`|`_mbctolower`|`towlower`|  
|`_totlower_l`|`_tolower_l`|`_mbctolower_l`|`_towlower_l`|  
  
> [!NOTE]
>  `_tolower_l` 和 `_towlower_l` 没有区域设置相关性，并且不应直接调用。 它们供 `_totlower_l` 内部使用。  
  
## <a name="requirements"></a>惠?  
  
|例程所返回的值|必需的标头|  
|-------------|---------------------|  
|`tolower`|\<ctype.h>|  
|`_tolower`|\<ctype.h>|  
|`towlower`|\<ctype.h 1> 或 \<wchar.h 1>|  
  
 有关其他兼容性信息，请参见“简介”中的 [兼容性](../../c-runtime-library/compatibility.md) 。  
  
## <a name="example"></a>示例  
 请参阅 [to 函数](../../c-runtime-library/to-functions.md)中的示例。  
  
## <a name="see-also"></a>请参阅  
 [数据转换](../../c-runtime-library/data-conversion.md)   
 [is、isw 例程](../../c-runtime-library/is-isw-routines.md)   
 [to 函数](../../c-runtime-library/to-functions.md)   
 [区域设置](../../c-runtime-library/locale.md)   
 [多字节字符序列的解释](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)
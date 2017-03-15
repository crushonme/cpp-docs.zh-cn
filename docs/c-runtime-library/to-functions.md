---
title: "to 函数 | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr120.dll
- msvcr90.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- To
dev_langs:
- C++
helpviewer_keywords:
- to functions
- string conversion, to different characters
- string conversion, case
- lowercase, converting strings
- uppercase, converting strings
- case, converting
- characters, converting
ms.assetid: f636a4c6-8c9f-4be2-baac-064f9dbae300
caps.latest.revision: 13
author: corob-msft
ms.author: corob
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 0f4efaf826da7a2ff1ef5b9f21bc5e846751211b

---
# <a name="to-functions"></a>to 函数
每个 **to** 函数及其关联的宏（如果有），将单个字符转换为另一个字符。  
  
|||  
|-|-|  
|[__toascii](../c-runtime-library/reference/toascii-toascii.md)|[toupper、_toupper、towupper](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|  
|[tolower、tolower、towlower](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)||  
  
## <a name="remarks"></a>备注  
 **to** 函数和宏转换如下所示。  
  
|例程|宏|描述|  
|-------------|-----------|-----------------|  
|`__toascii`|`__toascii`|将 `c` 转换为 ASCII 字符|  
|`tolower`|`tolower`|如适用，将 `c` 转换为小写|  
|`_tolower`|`_tolower`|将 `c` 转换为小写|  
|`towlower`|无|将 `c` 转换为相应的宽字符小写字母|  
|`toupper`|`toupper`|如适用，将 `c` 转换为大写|  
|`_toupper`|`_toupper`|将 `c` 转换为大写|  
|`towupper`|无|将 c 转换为相应的宽字符大写字母|  
  
 若要将 ** 的函数版本用于同时定义为宏的 ** 例程，或者使用 `#undef` 指令移除宏定义或不包括 CTYPE.H。 如果使用 /Za 编译器选项，编译器将使用 `toupper` 或 `tolower` 的函数版本。 `toupper` 和 `tolower` 函数的声明位于 STDLIB.H 中。  
  
 `__toascii` 例程集将除低顺序 7 位以外的所有 `c` 设置为 0，使转换后的值表示 ASCII 字符集中的字符。 如果 `c` 已表示 ASCII 字符，则 `c` 保持不变。  
  
 `tolower` 和 `toupper` 例程：  
  
-   依赖于当前区域设置的 `LC_CTYPE` 类别（`tolower` 调用 `isupper`，`toupper` 调用 `islower`）。  
  
-   如果 `c` 表示当前区域设置中大小写正确的可转换字母并且该区域设置存在相反的大小写，则转换 `c`。 否则，`c` 保持不变。  
  
 `_tolower` 和 `_toupper` 例程：  
  
-   是 `tolower` 和 **toupper** 区域设置独立的、速度更快的版本。  
  
-   仅当 **isascii(**`c`**)** 和 **isupper(**`c`**)** 或 **islower(**`c`**)** 分别不为零时可用。  
  
-   如果 `c` 不是用于转换的正确大小写的 ASCII 字母，则结果不确定。  
  
 当且仅当下列两个条件均不为零时，`towlower` 和 `towupper` 函数才返回转换后的 `c` 副本。 否则，`c` 保持不变。  
  
-   `c` 是大小写正确的宽字符（即 `iswupper` 或 **iswlower** 分别为非零值）。  
  
-   目标大小写有对应的宽字符（即 `iswlower` 或 **iswupper** 分别为非零值）。  
  
## <a name="example"></a>示例  
  
```  
// crt_toupper.c  
/* This program uses toupper and tolower to  
 * analyze all characters between 0x0 and 0x7F. It also  
 * applies _toupper and _tolower to any code in this  
 * range for which these functions make sense.  
 */  
  
#include <ctype.h>  
#include <string.h>  
  
char msg[] = "Some of THESE letters are Capitals.";  
char *p;  
  
int main( void )  
{  
   printf( "%s\n", msg );  
  
   /* Reverse case of message. */  
   for( p = msg; p < msg + strlen( msg ); p++ )  
   {  
      if( islower( *p ) )  
         putchar( _toupper( *p ) );  
      else if( isupper( *p ) )  
         putchar( _tolower( *p ) );  
      else  
         putchar( *p );  
   }  
}  
```  
  
```Output  
Some of THESE letters are Capitals.  
sOME OF these LETTERS ARE cAPITALS.  
```  
  
## <a name="see-also"></a>另请参阅  
 [数据转换](../c-runtime-library/data-conversion.md)   
 [区域设置](../c-runtime-library/locale.md)   
 [is、isw 例程](../c-runtime-library/is-isw-routines.md)


<!--HONumber=Feb17_HO4-->


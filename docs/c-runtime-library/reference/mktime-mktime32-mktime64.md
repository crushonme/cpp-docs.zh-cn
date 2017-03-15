---
title: "mktime、_mktime32、_mktime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mktime32"
  - "mktime"
  - "_mktime64"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mktime"
  - "_mktime64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mktime32 函数"
  - "_mktime64 函数"
  - "转换时间"
  - "mktime 函数"
  - "mktime32 函数"
  - "mktime64 函数"
  - "时间函数"
  - "时间, 转换"
ms.assetid: 284ed5d4-7064-48a2-bd50-15effdae32cf
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# mktime、_mktime32、_mktime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

将本地时间转换为日历值。  
  
## 语法  
  
```  
time_t mktime(  
   struct tm *timeptr   
);  
__time32_t _mktime32(  
   struct tm *timeptr   
);  
__time64_t _mktime64(  
   struct tm *timeptr   
);  
```  
  
#### 参数  
 *timeptr*  
 有关指向时间结构的指针，请参阅 [asctime](../../c-runtime-library/reference/asctime-wasctime.md)。  
  
## 返回值  
 `_mktime32` 返回编码为 [time\_t](../../c-runtime-library/standard-types.md) 类型的值的指定日历时间。 如果 *timeptr* 引用了 1970 年 1 月 1 日午夜之前的日期，或者如果无法表示日历时间，则 `_mktime32` 将返回转换为 `time_t` 类型的 –1。 当使用 `_mktime32` 并且如果 *timeptr* 23:59:59 2038 年 1 月 18 日，格式为协调世界时 \(UTC\) 之后的日期的引用，它将返回 – 1 转换为类型 `time_t`。  
  
 `_mktime64` 将返回 – 1 转换为类型 `__time64_t` 如果 *timeptr* 引用 23:59:59，3000 年 12 月 31 日，UTC 之后的日期。  
  
## 备注  
 `mktime`、`_mktime32` 和 `_mktime64` 函数将由 *timeptr* 指向的提供的时间结构（可能不完整）转换为使用规范化值的完全定义的结构，然后将它转换为 `time_t` 日历时间值。 转换后的时间与由 [time](../../c-runtime-library/reference/time-time32-time64.md) 函数返回的值具有相同的编码。 原始值 `tm_wday` 和 `tm_yday` 组成部分 *timeptr* 结构将被忽略，并且其他组件的原始值不会限制为其正常范围。  
  
 `mktime` 是一个等效于 `_mktime64` 的内联函数，除非定义 `_USE_32BIT_TIME_T`，否则在这种情况下，它等效于 `_mktime32`。  
  
 调整为 UTC 后, `_mktime32` 句柄日期从 1970 年 1 月 1 日午夜到 23:59:59 2038 年 1 月 18 日，UTC。`_mktime64` 可处理从 1970 年 1 月 1 日午夜到 3000 年 12 月 31 日 23 时 59 分 59 秒之间的日期。 即使你指定的日期在范围内，此调整也可能会导致这些函数返回 \-1（转换为 `time_t`、`__time32_t` 或 `__time64_t`）。 例如，如果你位于埃及开罗（比 UTC 早两个小时），则首先将从你在 *timeptr* 中指定的日期中减去两个小时；此时这可能会使你的日期位于范围之外。  
  
 这些函数可用于在 tm 结构中进行验证和填充。 如果成功，这些函数会将 `tm_wday` 和 `tm_yday` 的值设置为相应的值，并设置其他组件以表示指定的日历时间，但是同时使其值强制位于正常范围内。 除非确定 `tm_mday` 和 `tm_mon`，否则不会设置 `tm_year` 的最终值。 指定 `tm` 结构时间时，将 `tm_isdst` 字段设置为：  
  
-   零 \(0\)，指示标准时间有效。  
  
-   大于 0 的值，指示夏令时有效。  
  
-   小于零的值，使用 C 运行时库代码计算有效的是标准时间还是夏令时。  
  
 C 运行时库将从 [TZ](../../c-runtime-library/reference/tzset.md) 环境变量中确定夏令时行为。 如果 `TZ` 未设置，Win32 API 调用 [GetTimeZoneInformation](http://msdn.microsoft.com/library/windows/desktop/ms724421.aspx) 用于从操作系统中获取夏令时信息。 如果此操作失败，则该库将假设使用用于实现夏令时计算的美国规则。`tm_isdst` 是必填字段。 如果未设置，则未定义其值，并且这些函数的返回值不可预知。 如果 *timeptr* 指向由之前对 `tm`、`asctime` 或 `gmtime` 的调用（或这些函数的变量）返回的 `localtime` 结构，则 `tm_isdst` 字段将包含正确的值。  
  
 请注意，`gmtime` 和 `localtime`（以及 `_gmtime32`、`_gmtime64`、`_localtime32` 和 `_localtime64`）针对每个线程使用单个缓冲区以实现转换。 如果你为 `mktime`、`_mktime32` 或 `_mktime64` 提供此缓冲区，则会损坏之前的内容。  
  
 这些函数将验证其参数。 如果 *timeptr* 是 null 指针，则调用无效参数处理程序，如中所述 [参数验证](../../c-runtime-library/parameter-validation.md)。 如果允许执行继续，则这些函数将返回 \-1 并将 `errno` 设置为 `EINVAL`。  
  
## 要求  
  
|例程|必需的标头|  
|--------|-----------|  
|`mktime`|\<time.h\>|  
|`_mktime32`|\<time.h\>|  
|`_mktime64`|\<time.h\>|  
  
 有关其他兼容性信息，请参见“简介”中的[兼容性](../../c-runtime-library/compatibility.md)。  
  
## 库  
 [C 运行时库](../../c-runtime-library/crt-library-features.md)的所有版本。  
  
## 示例  
  
```  
// crt_mktime.c  
/* The example takes a number of days  
 * as input and returns the time, the current  
 * date, and the specified number of days.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm  when;  
   __time64_t now, result;  
   int        days;  
   char       buff[80];  
  
   time( &now );  
   _localtime64_s( &when, &now );  
   asctime_s( buff, sizeof(buff), &when );  
   printf( "Current time is %s\n", buff );  
   days = 20;  
   when.tm_mday = when.tm_mday + days;  
   if( (result = mktime( &when )) != (time_t)-1 ) {  
      asctime_s( buff, sizeof(buff), &when );  
      printf( "In %d days the time will be %s\n", days, buff );  
   } else  
      perror( "mktime failed" );  
}  
```  
  
## 示例输出  
  
```  
Current time is Fri Apr 25 13:34:07 2003  
  
In 20 days the time will be Thu May 15 13:34:07 2003  
```  
  
## .NET Framework 等效项  
 <xref:System.DateTimeOffset.%23ctor%2A>  
  
## 请参阅  
 [时间管理](../../c-runtime-library/time-management.md)   
 [asctime、\_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [gmtime、\_gmtime32、\_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、\_localtime32、\_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [\_mkgmtime、\_mkgmtime32、\_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [time、\_time32、\_time64](../../c-runtime-library/reference/time-time32-time64.md)
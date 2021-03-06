---
title: "使用内联程序集编写函数 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C++], inline assembly
- inline assembly [C++], writing functions
- assembler [C++], writing functions
- __asm keyword [C++], in functions
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f2fc9e6a1d2c94e74ef8aabf085af8fc4dc0bc28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="writing-functions-with-inline-assembly"></a>使用内联程序集编写函数
## <a name="microsoft-specific"></a>Microsoft 专用  
 如果使用内联程序集代码编写函数，则可轻松将自变量传递给函数并从中返回一个值。 下面的示例先比较为单独的汇编程序编写的函数，然后为内联汇编程序重新编写函数。 称为 `power2` 的函数接收两个参数，将第一个参数乘以 2 得到第二个参数的幂。 为单独的汇编程序编写的函数如下所示：  
  
```  
; POWER.ASM  
; Compute the power of an integer  
;  
       PUBLIC _power2  
_TEXT SEGMENT WORD PUBLIC 'CODE'  
_power2 PROC  
  
        push ebp        ; Save EBP  
        mov ebp, esp    ; Move ESP into EBP so we can refer  
                        ;   to arguments on the stack  
        mov eax, [ebp+4] ; Get first argument  
        mov ecx, [ebp+6] ; Get second argument  
        shl eax, cl     ; EAX = EAX * ( 2 ^ CL )  
        pop ebp         ; Restore EBP  
        ret             ; Return with sum in EAX  
  
_power2 ENDP  
_TEXT   ENDS  
        END  
```  
  
 由于此函数是为单独汇编程序编写的，因此它需要单独的源文件、程序集和链接步骤。 C 和 C++ 函数参数通常在堆栈上传递，因此该版本的 `power2` 函数通过其在堆栈上的位置访问其参数。 (请注意，**模型**指令，MASM 和一些其他汇编程序中可用还允许您按名称访问堆栈参数和局部堆栈变量。)  
  
## <a name="example"></a>示例  
 此程序利用内联程序集代码编写 `power2` 函数：  
  
```  
// Power2_inline_asm.c  
// compile with: /EHsc  
// processor: x86  
  
#include <stdio.h>  
  
int power2( int num, int power );  
  
int main( void )  
{  
    printf_s( "3 times 2 to the power of 5 is %d\n", \  
              power2( 3, 5) );  
}  
int power2( int num, int power )  
{  
   __asm  
   {  
      mov eax, num    ; Get first argument  
      mov ecx, power  ; Get second argument  
      shl eax, cl     ; EAX = EAX * ( 2 to the power of CL )  
   }  
   // Return with result in EAX  
}  
```  
  
 `power2` 函数的内联版本按名称引用其参数并显示在程序的其余部分所在的同一源文件中。 此外，该版本需要的程序集指令更少。  
  
 由于 `power2` 的内联版本不执行 C `return` 语句，因此它将生成一个无害警告（如果您在警告等级 2 或更高等级进行编译）。 函数将返回一个值，但编译器无法告知缺少 `return` 语句。 你可以使用[#pragma 警告](../../preprocessor/warning.md)禁用此警告的生成。  
  
 **结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [在 __asm 块中使用 C 或 C++](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)
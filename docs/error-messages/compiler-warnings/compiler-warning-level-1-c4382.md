---
title: "编译器警告 （等级 1） C4382 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4382
dev_langs: C++
helpviewer_keywords: C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4b0cef09795553759487e28ef61babe75b35ce03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4382"></a>编译器警告（等级 1）C4382
引发 type： 具有 __clrcall 析构函数或复制构造函数的类型仅可捕获在 /clr: pure 模块  
  
 **/Clr: pure**编译器选项在 Visual Studio 2015 中已弃用。  
  
 如果使用编译的**/clr** (不**/clr: pure**)，异常处理预计要的本机类型的成员函数[__cdecl](../../cpp/cdecl.md)而不[__clrcall](../../cpp/clrcall.md). 与成员函数使用的本机类型`__clrcall`调用约定不能使用编译的模块中捕获**/clr**。  
  
 如果使用编译的模块中，将捕获到异常**/clr: pure**，则可以忽略此警告。  
  
 有关详细信息，请参阅 [/clr（公共语言运行时编译）](../../build/reference/clr-common-language-runtime-compilation.md)。  
  
## <a name="example"></a>示例  
 下面的示例生成 C4382。  
  
```  
// C4382.cpp  
// compile with: /clr /W1 /c  
struct S {  
   __clrcall ~S() {}  
};  
  
struct T {  
   ~T() {}  
};  
  
int main() {  
   S s;  
   throw s;   // C4382  
  
   S * ps = &s;  
   throw ps;   // OK  
  
   T t;  
   throw t;   // OK  
}  
```
---
title: "编译器错误 C3027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3027"
ms.assetid: 6562a5c2-2f28-4b36-91ca-2a64c0f0501a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 编译器错误 C3027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“clause”: 需要算术表达式或指针表达式  
  
 需要算术表达式或指针表达式的子句传递了另一种表达式。  
  
## 示例  
 下面的示例生成 C3027：  
  
```  
// C3027.cpp // compile with: /openmp /link vcomps.lib #include <stdio.h> #include "omp.h" struct MyStruct { int x; } m_MyStruct; int main() { int i; puts("Test with class MyStruct:\n"); #pragma omp parallel for if(m_MyStruct)   // C3027 for (i = 1; i <= 2; ++i) printf_s("Hello World - thread %d - iteration %d\n", omp_get_thread_num(), i); puts("Test with int:\n"); #pragma omp parallel for if(9)   // OK for (i = 1; i <= 2; ++i) printf_s("Hello World - thread %d - iteration %d\n", omp_get_thread_num(), i); }  
```
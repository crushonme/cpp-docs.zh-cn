---
title: "编译器错误 C3033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3033"
ms.assetid: 8628b6bb-a650-4ed2-af13-57acd2f7ddbb
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 编译器错误 C3033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“var”: “clause”子句中的变量不能是常量限定类型  
  
 传递给某些子句的值不能为 `const` 变量。  
  
 下面的示例生成 C3033：  
  
```  
// C3033.cpp // compile with: /openmp /link vcomps.lib int main() { const int val = 1; int val2 = 1; #pragma omp parallel reduction(+ : val)   // C3033 ; #pragma omp parallel reduction(+ : val2)   // OK ; }  
```
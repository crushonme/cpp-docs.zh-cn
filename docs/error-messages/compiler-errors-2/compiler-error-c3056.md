---
title: "编译器错误 C3056 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3056"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3056"
ms.assetid: 9500173d-870b-49b3-8e88-0ee93586d19a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 编译器错误 C3056
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“symbol”: 符号所在范围与“threadprivate”指令所在范围不同  
  
 在 [threadprivate](../../parallel/openmp/reference/threadprivate.md) 子句中使用的符号必须位于与 `threadprivate` 子句相同的范围中。  
  
 下面的示例生成 C3056：  
  
```  
// C3056.cpp // compile with: /openmp int x, y; void test() { #pragma omp threadprivate(x, y)   // C3056 #pragma omp parallel copyin(x, y) { x = y; } }  
```  
  
 可能的解决方法：  
  
```  
// C3056b.cpp // compile with: /openmp /LD int x, y; #pragma omp threadprivate(x, y) void test() { #pragma omp parallel copyin(x, y) { x = y; } }  
```
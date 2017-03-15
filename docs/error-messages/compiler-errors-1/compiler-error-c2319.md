---
title: "编译器错误 C2319 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2319"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2319"
ms.assetid: 25263e6e-f5ba-4d2c-8727-8c2d8ca2e5ce
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 编译器错误 C2319
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“try\/catch”后面必须有复合语句。 缺少“{”  
  
 在 `try` 或 `catch` 语句后面未找到 `try` 或 `catch` 块。 块必须括在大括号内。  
  
 下面的示例生成 C2319：  
  
```  
// C2319.cpp // compile with: /EHsc #include <eh.h> class C {}; int main() { try { throw "ooops!"; } catch( C ) ;    // C2319 // try the following line instead // catch( C ) {} }  
```
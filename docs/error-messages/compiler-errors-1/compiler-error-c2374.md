---
title: "编译器错误 C2374 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2374
dev_langs: C++
helpviewer_keywords: C2374
ms.assetid: 73b51965-e91c-4e21-9732-f71c1449d22e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c96f24e2821989e39f028810abc5efea255b607c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2374"></a>编译器错误 C2374
“identifier”：重定义；多次初始化  
  
 不止一次初始化了标识符。  
  
 下面的示例生成 C2374：  
  
```  
// C2374.cpp  
// compile with: /c  
int i = 0;  
int i = 1;   // C2374  
int j = 1;   // OK  
```
---
title: "编译器错误 C2493 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2493
dev_langs: C++
helpviewer_keywords: C2493
ms.assetid: 68316cd5-682b-49c3-b6ea-23c4e5d296cf
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 48b2c26c061ae15c13c80cf530e71cc61aa8798c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2493"></a>编译器错误 C2493
__based 非法形式  
  
 A`__based`表达式必须基于指针。  
  
 下面的示例生成 C2493:  
  
```  
// C2493.cpp  
// compile with: /c  
char mybase;  
int __based(mybase) ptr;   // C2493  
  
// OK  
char * mybase;  
int __based(mybase) * ptr;  
```
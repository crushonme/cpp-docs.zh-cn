---
title: "编译器错误 C2055 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2055
dev_langs: C++
helpviewer_keywords: C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 04ba07229b1beeb0fdf4362d2b382121ab7606b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2055"></a>编译器错误 C2055
预期的形式参数列表中，不是类型列表  
  
 函数定义包含参数类型列表而不是形参列表。 ANSI C 要求形参，除非它们是 void 或省略号命名为 (`...`)。  
  
 下面的示例生成 C2055:  
  
```  
// C2055.c  
// compile with: /c  
void func(int, char) {}  // C2055  
void func (int i, char c) {}   // OK  
```
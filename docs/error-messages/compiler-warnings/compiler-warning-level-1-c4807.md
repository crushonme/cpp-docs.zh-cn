---
title: "编译器警告 （等级 1） C4807 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4807
dev_langs: C++
helpviewer_keywords: C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af604a1a045b9dbef7b3c27f9c7aabd0040aa318
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4807"></a>编译器警告（等级 1）C4807
“operation”: 类型“type”与类型“type”的有符号位域的混合不安全  
  
 在将一位有符号位域与 `bool` 变量进行比较时生成此警告。 因为一位有符号位域只能包含值 -1 或 0，所以将其与 `bool`比较很危险。 将 `bool` 与一位无符号位域进行混合不生成警告，因为它们与 `bool` 相同，只包含 0 或 1。  
  
## <a name="example"></a>示例  
 下面的示例生成 C4807：  
  
```  
// C4807.cpp  
// compile with: /W1  
typedef struct bitfield {  
   signed mybit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bool b = true;  
  
   // try..  
   // int b = true;  
  
   bf.mybit = -1;  
   if (b == bf.mybit) {   // C4807  
      b = false;  
   }  
}  
```
---
title: "编译器错误 C2761 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2761
dev_langs: C++
helpviewer_keywords: C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 978ec4af1371f06ac5577f3dde66f6e7b62d0e4d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2761"></a>编译器错误 C2761
function： 不允许的成员函数重新声明  
  
 不能重新声明成员函数。 您可以定义它，但不是能重新声明。  
  
## <a name="example"></a>示例  
 下面的示例生成 C2761。  
  
```  
// C2761.cpp  
class a {  
   int t;  
   void test();  
};  
  
void a::a;     // C2761  
void a::test;  // C2761  
  
```  
  
## <a name="example"></a>示例  
 不能定义类或结构的非静态成员。  下面的示例生成 C2761。  
  
```  
// C2761_b.cpp  
// compile with: /c  
struct C {  
   int s;  
   static int t;  
};  
  
int C::s;   // C2761  
int C::t;   // OK  
```
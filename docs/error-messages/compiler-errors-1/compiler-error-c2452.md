---
title: "编译器错误 C2452 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2452
dev_langs: C++
helpviewer_keywords: C2452
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a5d2cebe4b17357d1dbb1f1cbdfb237a579b4927
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2452"></a>编译器错误 C2452
type: safe_cast 的源类型无效  
  
 源类型[safe_cast](../../windows/safe-cast-cpp-component-extensions.md)无效。  例如，对中的所有类型`safe_cast`操作必须是 CLR 类型。  
  
 下面的示例生成 C2452:  
  
```  
// C2452.cpp  
// compile with: /clr  
  
struct A {};  
struct B : public A {};  
  
ref struct C {};  
ref struct D : public C{};  
  
int main() {  
   A a;  
   safe_cast<B*>(&a);   // C2452  
  
   // OK  
   C ^ c = gcnew C;  
   safe_cast<D^>(c);  
}  
```
---
title: "编译器错误 C3535 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3535
dev_langs: C++
helpviewer_keywords: C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5797d644ec13ed89bad3ddcda23be109df067b03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3535"></a>编译器错误 C3535
无法推导出的类型 type1 从 type2  
  
 声明的变量的类型`auto`无法从初始化表达式的类型推导关键字。 例如，此错误发生的初始化表达式的计算结果为`void`，这不是类型。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
1.  确保初始化表达式的类型不是`void`。  
  
2.  确保声明不是指向基本类型的指针。 有关详细信息，请参阅[基本类型](../../cpp/fundamental-types-cpp.md)。  
  
3.  请确保如果该声明是指向类型的指针，初始化表达式是指针类型。  
  
## <a name="example"></a>示例  
 下面的示例会产生 C3535，因为初始化表达式的计算结果为`void`。  
  
```  
// C3535a.cpp  
// Compile with /Zc:auto  
void f(){}  
int main()  
{  
   auto x = f();   //C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>示例  
 下面的示例会产生 C3535，因为该语句声明变量`x`作为指向推导出的类型，但初始值设定项的类型的表达式进行双。 因此，编译器无法推导变量类型。  
  
```  
// C3535b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto* x = 123.0;   // C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>示例  
 下面的示例会产生 C3535，因为变量`p`声明指针指向推导出的类型，但初始化表达式不是指针类型。  
  
```  
// C3535c.cpp  
// Compile with /Zc:auto  
class A { };  
A x;  
auto *p = x;  // C3535  
```  
  
## <a name="see-also"></a>请参阅  
 [auto 关键字](../../cpp/auto-keyword.md)   
 [基本类型](../../cpp/fundamental-types-cpp.md)
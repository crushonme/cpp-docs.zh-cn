---
title: "运算符&gt;（堆栈） (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::stack::operator>
dev_langs: C++
helpviewer_keywords: operator> member [STL/CLR]
ms.assetid: 77979026-bed5-4d24-a2af-f720f8c362a2
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8650c16e49e665ce6da23bf45a4e0a32546fb1fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="operatorgt-stack-stlclr"></a>运算符&gt;（堆栈） (STL/CLR)
堆栈大于比较。  
  
## <a name="syntax"></a>语法  
  
```  
template<typename Value,  
    typename Container>  
    bool operator>(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>参数  
 左  
 要比较的左容器。  
  
 右  
 要比较的右容器。  
  
## <a name="remarks"></a>备注  
 运算符函数返回`right` `<` `left`。 用于测试是否`left`进行排序之后`right`的两个堆栈何时比较的元素的元素。  
  
## <a name="example"></a>示例  
  
```  
// cliext_stack_operator_gt.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] > [a b c] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[a b d] > [a b c] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] > [a b c] is False  
[a b d] > [a b c] is True  
```  
  
## <a name="requirements"></a>惠?  
 **标头：** \<cliext/堆栈 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>请参阅  
 [堆栈 (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [运算符 = = （堆栈） (STL/CLR)](../dotnet/operator-equality-stack-stl-clr.md)   
 [运算符 ！ = （堆栈） (STL/CLR)](../dotnet/operator-inequality-stack-stl-clr.md)   
 [运算符\<（堆栈） (STL/CLR)](../dotnet/operator-less-than-stack-stl-clr.md)   
 [运算符 > = （堆栈） (STL/CLR)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)   
 [operator<= (stack) (STL/CLR)](../dotnet/operator-less-or-equal-stack-stl-clr.md)
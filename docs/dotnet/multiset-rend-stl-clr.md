---
title: "multiset:: rend (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multiset::rend
dev_langs: C++
helpviewer_keywords: rend member [STL/CLR]
ms.assetid: db84e142-efa7-4171-bad6-8132f3f5f741
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 46856f7c305b83d88452bd3d6db0ed600a910bd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="multisetrend-stlclr"></a>multiset::rend (STL/CLR)
指定反向受控序列的末尾。  
  
## <a name="syntax"></a>语法  
  
```  
reverse_iterator rend();  
```  
  
## <a name="remarks"></a>备注  
 成员函数返回一个反向迭代器指向刚超出开头的受控序列。 因此，它指定`end`反向序列。 用于获取指定的迭代器`current`末尾按逆序的受控的序列，但其状态可以更改，如果更改了受控序列的长度。  
  
## <a name="example"></a>示例  
  
```  
// cliext_multiset_rend.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Mymultiset::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --rend() = b  
*--rend() = a  
```  
  
## <a name="requirements"></a>惠?  
 **标头：** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>请参阅  
 [多集 (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset:: begin (STL/CLR)](../dotnet/multiset-begin-stl-clr.md)   
 [multiset:: end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)   
 [multiset::rbegin (STL/CLR)](../dotnet/multiset-rbegin-stl-clr.md)
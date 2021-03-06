---
title: "make_pair (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::make_pair
dev_langs: C++
helpviewer_keywords: make_pair function [STL/CLR]
ms.assetid: 74733f2c-97b0-4d69-b431-5ab8f0de9e3e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 34f86aefd9a7bad7b3b1f03f98d3df8965020e48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="makepair-stlclr"></a>make_pair (STL/CLR)
请`pair`从一对值。  
  
## <a name="syntax"></a>语法  
  
```  
template<typename Value1,  
    typename Value2>  
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);  
```  
  
#### <a name="parameters"></a>参数  
 `Value1`  
 第一个包装值类型。  
  
 `Value2`  
 已包装的第二个值的类型。  
  
 `first`  
 要包装的第一个值。  
  
 `second`  
 要包装的第二个值。  
  
## <a name="remarks"></a>备注  
 此模板函数返回 `pair<Value1, Value2>(first, second)`。 使用它来构造`pair<Value1, Value2>`从一对值的对象。  
  
## <a name="example"></a>示例  
  
```cpp  
// cliext_make_pair.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    c1 = cliext::make_pair(L'y', 4);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[y, 4]  
```  
  
## <a name="requirements"></a>惠?  
 **标头：** \<cliext/实用工具 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>请参阅  
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)
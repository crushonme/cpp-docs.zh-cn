---
title: "编译器错误 C3771 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3771
dev_langs: C++
helpviewer_keywords: C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d1f552eee7ac20c086240a4ce79fd3616127268b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3771"></a>编译器错误 C3771
“标识符”: 在最近的命名空间范围内无法找到友元声明  
  
无法在当前命名空间中找到指定模板的类模板声明 *标识符* 。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   确保在当前命名空间中定义了模板标识符的类模板声明，或模板标识符是完全限定的名称。  
  
## <a name="example"></a>示例  
下列代码示例在 `NA`命名空间中声明一个类模板和函数，但试图在 `NB`命名空间中声明友元函数模板。  
  
```cpp  
// C3771.cpp   
// compile with: /c  
  
namespace NA {  
template<class T> class A {  
    void aFunction(T t) {};  
    };  
}  
// using namespace NA;  
namespace NB {  
    class X {  
        template<class T> friend void A<T>::aFunction(T); // C3771  
// try the following line instead  
//      template<class T> friend void NA::A<T>::aFunction(T);  
// or try "using namespace NA;" instead.  
    };  
}  
```  
  
## <a name="see-also"></a>请参阅  
[模板](../../cpp/templates-cpp.md)  
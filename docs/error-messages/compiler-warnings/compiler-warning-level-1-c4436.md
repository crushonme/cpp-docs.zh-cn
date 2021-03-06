---
title: "编译器警告 （等级 1） C4436 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs: C++
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1018d678b6105f2d727f7806326218c168d8f728
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4436"></a>编译器警告（等级 1）C4436
构造函数或析构函数中从虚拟基“class1”到“class2”的 dynamic_cast 对于部分构造的对象可能会失败。使用 /vd2 编译或使用生效的 #pragma vtordisp(2) 定义“class2”  
  
 编译器遇到具有以下特征的 `dynamic_cast` 操作。  
  
-   转换是从基类指针到派生类的指针。  
  
-   派生类虚拟继承基类。  
  
-   派生类没有虚拟基的 `vtordisp` 字段。  
  
-   在派生类或进一步继承派生类的一些类的构造函数或析构函数中发现转换。  
  
 警告指示 `dynamic_cast` 在部分构造的对象上操作时，可能执行不正确。  如果派生的构造函数/析构函数在某些进一步派生对象的子对象上操作时，可能会发生该情况。  如果警告中指定的派生类不再进一步派生，可以忽略警告。  
  
## <a name="example"></a>示例  
 下面的示例生成 C4436 并演示缺少 `vtordisp` 字段所引发的代码生成问题。  
  
```cpp  
// C4436.cpp  
// To see the warning and runtime assert, compile with: /W1  
// To eliminate the warning and assert, compile with: /W1 /vd2  
//       or compile with: /W1 /DFIX  
#include <cassert>  
  
struct A  
{  
public:  
    virtual ~A() {}  
};  
  
#if defined(FIX)  
#pragma vtordisp(push, 2)  
#endif  
struct B : virtual A  
{  
    B()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4436  
        assert(this == b);              // assert unless compiled with /vd2  
    }  
};  
#if defined(FIX)  
#pragma vtordisp(pop)  
#endif  
  
struct C : B  
{  
    int i;  
};  
  
int main()  
{  
    C c;  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [dynamic_cast 运算符](../../cpp/dynamic-cast-operator.md)   
 [vtordisp](../../preprocessor/vtordisp.md)   
 [编译器警告（等级 4）C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)
---
title: "编译器错误 C3797 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3797
dev_langs: C++
helpviewer_keywords: C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5157e8b63bf15c2d972235e38f692e2ba356a629
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3797"></a>编译器错误 C3797
重写： 事件声明不能重写说明符 （应该放在事件添加/删除/引发方法相反）  
  
 不能重写具有另一个常用事件的普通事件 （而无需显式定义访问器方法的事件）。 重写事件必须定义访问器函数使用其行为。  
  
 有关详细信息，请参阅[事件](../../windows/event-cpp-component-extensions.md)。  
  
## <a name="example"></a>示例  
 下面的示例生成 C3797。  
  
```  
// C3797.cpp  
// compile with: /clr /c  
delegate void MyDel();  
  
ref class Class1 {  
public:  
   virtual event MyDel ^ E;  
};  
  
ref class Class2 : public Class1 {  
public:  
   virtual event MyDel ^ E override;   // C3797  
};  
  
// OK  
ref class Class3 : public Class1 {  
public:  
   virtual event MyDel ^ E {  
      void add(MyDel ^ d) override {}  
      void remove(MyDel ^ d) override {}  
   }  
};  
```
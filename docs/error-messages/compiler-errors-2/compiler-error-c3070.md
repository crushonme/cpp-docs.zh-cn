---
title: "编译器错误 C3070 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3070
dev_langs: C++
helpviewer_keywords: C3070
ms.assetid: ac88584d-40a6-4176-90f3-2371c3c935f2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0e7a258263a5a093b003afa669315f77671fe6dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3070"></a>编译器错误 C3070
“property”: 属性没有“set”方法  
  
 未定义属性的 set 访问器方法。 有关详细信息，请参阅 [property](../../windows/property-cpp-component-extensions.md)。  
  
 以下示例生成 C3070：  
  
```  
// C3070.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int size) {  
      m_data = gcnew array<int>(size);  
   }  
  
   property int % MyProp[int] {  
      int% get(int index) {   
         return m_data[index];   
      }  
   }  
  
   property int % MyProp2[int] {  
      int% get(int index) {   
         return m_data[index];  
      }  
      void set(int index, int % value) {}  
   }  
  
   property const int % MyProp3[int] {  
      const int% get(int index) {   
         return m_data[index];  
      }  
      void set(int index, const int % value) {}  
   }  
  
private:  
   array<int>^ m_data;  
};  
  
int main() {  
   R^ r = gcnew R(10);  
   r->MyProp[4] = 4;   // C3070  
  
   int value = 4;  
   r->MyProp2[4] = value;   // OK  
   r->MyProp3[4] = 4;   // OK  
}  
```
---
title: "编译器错误 C3142 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3142
dev_langs: C++
helpviewer_keywords: C3142
ms.assetid: 795137ad-d00a-4a9c-9665-0cd8bfb5da8b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6f3a8ac42883bc40834529eef5593e4814358c12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3142"></a>编译器错误 C3142
property_name： 无法获取属性的地址  
  
 属性的地址不供开发人员。  
  
 下面的示例生成 C3142:  
  
```  
// C3142_2.cpp  
// compile with: /clr  
using namespace System;  
ref class CSize {  
private:  
   property int Size {  
      int get();  
   }  
};  
  
int main() {  
    &CSize::Size; // C3142  
}  
```  

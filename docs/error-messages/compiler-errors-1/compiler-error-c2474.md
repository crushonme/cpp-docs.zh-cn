---
title: "编译器错误 C2474 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2474
dev_langs: C++
helpviewer_keywords: C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 91384ef6ea2a26ad21a8a43f022819b846efb385
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2474"></a>编译器错误 C2474
“keyword”: 缺少相邻的分号，可能是关键字或标识符。  
  
 编译器需要找到一个分号，因此不能确定你的意图。 增加一个分号以解决此问题。  
  
## <a name="example"></a>示例  
 以下示例生成 C2474。  
  
```  
// C2474.cpp  
// compile with: /clr /c  
  
ref class A {  
   ref class B {}  
   property int i;   // C2474 error  
};  
  
// OK  
ref class B {  
   ref class D {};  
   property int i;  
};  
  
ref class E {  
   ref class F {} property;   
   int i;  
};  
```
---
title: "编译器警告 （等级 4） C4337 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4337
dev_langs: C++
helpviewer_keywords: C4337
ms.assetid: 70bc72d9-aac5-45cd-abd3-ebe42a05897b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b620d43e595ca959622cd8fca1396a96718e80df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4337"></a>编译器警告（等级 4）C4337
在 typelib2 的交叉引用的类型库 typelib1 是要自动导入  
  
 Auto_search 特性[#import 指令](../../preprocessor/hash-import-directive-cpp.md)导致隐式要导入类型库。  
  
 从以下两个文件 （使用 midl.exe 编译） 创建的磁盘上的给定两个类型库：  
  
```  
// C4337a.idl  
[  
  uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12B)  
]  
library C4337aLib  
{  
   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12C)]  
   enum E_C4337a  
   {  
      one = 0,  
      two = 1,  
      three = 2  
    };  
};  
```  
  
 然后与第二个.idl 文件  
  
```  
// C4337b.idl  
[  
   uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12D)  
]  
  
library C4337bLib  
{  
   importlib("c4337a.tlb");  
  
   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12E)]  
   struct S_C4337b  
   {  
      enum E_C4337a e;  
   };  
};  
```  
  
 下面的示例生成 C4337:  
  
```  
// C4337.cpp  
// compile with: /W4 /LD  
#import "c4337b.tlb" auto_search   // C4337  
// explicitly #import all type libraries to resolve  
// #import "C4337a.tlb"  
// #import "C4337b.tlb"  
```
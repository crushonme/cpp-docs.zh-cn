---
title: "编译器错误 C2755 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2755
dev_langs: C++
helpviewer_keywords: C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b99ce492806b46231293ca433d24db1b153fb982
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2755"></a>编译器错误 C2755
param： 部分专用化的非类型参数必须是简单标识符  
  
 非类型参数必须是一个简单的标识符，编译器可以解析为一个单一的标识符或常量值的编译时的内容。  
  
 下面的示例生成 C2755:  
  
```  
// C2755.cpp  
template<int I, int J>  
struct A {};  
  
template<int I>   
struct A<I,I*5> {};   // C2755  
// try the following line instead  
// struct A<I,5> {};  
```
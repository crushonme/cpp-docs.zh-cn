---
title: "构造输入流对象 | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d284452e7b6c9983a751117ad6c2290b267c6994
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="constructing-input-stream-objects"></a>构造输入流对象
如果只使用 `cin` 对象，则无需构造输入流。 如果使用以下对象，则必须构造输入流：  
  
- [输入文件流构造函数](#vclrfinputfilestreamconstructorsanchor8)  
  
- [输入字符串流构造函数](#vclrfinputstringstreamconstructorsanchor9)  
  
##  <a name="vclrfinputfilestreamconstructorsanchor8"></a>输入文件流构造函数  
 有两种创建输入文件流的方法：  
  
-   使用 `void` 参数构造函数，然后调用 `open` 成员函数：  
  
 ```  
    ifstream myFile; // On the stack  
    myFile.open("filename");

 
    ifstream* pmyFile = new ifstream; // On the heap  
    pmyFile->open("filename");
```  
  
-   在构造函数调用期间指定文件名和模式标志，从而在构造过程中打开文件：  
  
 ```  
    ifstream myFile("filename");
```  
  
##  <a name="vclrfinputstringstreamconstructorsanchor9"></a>输入字符串流构造函数  
 输入字符串流构造函数需要预分配、预初始化存储的地址：  
  
```  
string s("123.45");

double amt;  
istringstream myString(s);

//istringstream myString("123.45") also works  
myString>> amt; // amt contains 123.45  
```  
  
## <a name="see-also"></a>请参阅  
 [输入流](../standard-library/input-streams.md)


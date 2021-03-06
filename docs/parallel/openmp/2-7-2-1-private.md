---
title: "2.7.2.1 私有 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a08faf39ab2f82d76a936c216ba6707bee5c240
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="2721-private"></a>2.7.2.1 private
`private`子句声明变量的列表是专用于每个线程在一个组中的变量。 语法`private`子句是，如下所示：  
  
```  
private(variable-list)  
```  
  
 中指定的变量的行为`private`子句是，如下所示。 具有自动存储持续时间的新对象分配并供构造。 大小和新对象的对齐方式取决于变量的类型。 此分配一次发生在团队中，每个线程，以及针对的类对象，如有必要; 调用默认构造函数否则的初始值是不确定的。  所引用的变量的原始对象具有不确定的值到构造在输入时、 在构造中，动态范围内不能修改并且在从构造退出时不确定的值。  
  
 在指令构造的词法范围内，该变量引用新线程分配的私有对象。  
  
 对限制`private`子句如下所示：  
  
-   中指定的类类型的变量`private`子句必须具有可访问的明确的默认构造函数。  
  
-   中指定的变量`private`子句不能有**const**-限定类型，除非它具有类型具有的类`mutable`成员。  
  
-   中指定的变量`private`子句必须没有不完整类型或引用类型。  
  
-   在出现的变量`reduction`子句**并行**指令不能指定`private`将绑定到并行构造工作共享指令上的子句。
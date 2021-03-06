---
title: "强制转换运算符 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs: C++
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5bc7f1b0c2df820c3dc9e76b76dfcc72794e1906
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="casting-operators"></a>强制转换运算符
有几种特定于 C++ 语言的转换运算符。 这些运算符用于删除旧式 C 语言转换中的一些多义性和危险继承。 这些运算符是：  
  
-   [dynamic_cast](../cpp/dynamic-cast-operator.md)用于多态类型的转换。  
  
-   [static_cast](../cpp/static-cast-operator.md)用于非多态类型的转换。  
  
-   [const_cast](../cpp/const-cast-operator.md)用于删除`const`， `volatile`，和`__unaligned`属性。  
  
-   [reinterpret_cast](../cpp/reinterpret-cast-operator.md)用于位的简单重新解释。  
  
-   [safe_cast](../windows/safe-cast-cpp-component-extensions.md)用于生成可验证的 MSIL。  
  
 在万不得已时使用 `const_cast` 和 `reinterpret_cast`，因为这些运算符与旧的样式转换带来的危险相同。 但是，若要完全替换旧的样式转换，仍必须使用它们。  
  
## <a name="see-also"></a>请参阅  
 [强制转换](../cpp/casting.md)
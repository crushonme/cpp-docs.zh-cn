---
title: "C 赋值运算符 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- remainder assignment operator (%=)
- '&= operator'
- bitwise-AND assignment operator
- operators [C], assignment
- operators [C], shift
- ^= operator, assignment operators
- += operator
- '>>= operator'
- '|= operator'
- division assignment operator
- subtraction operator
- right shift operators
- subtraction operator, C assignment operators
- = operator, assignment operators
- '*= operator'
- '>> operator'
- '%= operator'
- assignment operators, C
- = operator
- assignment operators
- assignment conversions
- -= operator
- multiplication assignment operator (*=)
- shift operators, right
- /= operator
- operator >>=, C assignment operators
- <<= operator
ms.assetid: 11688dcb-c941-44e7-a636-3fc98e7dac40
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c839538b94ff8f80eabed98dbaf16e4009d3e500
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="c-assignment-operators"></a>C 赋值运算符
赋值操作将右侧操作数的值分配给左侧操作数命名的存储位置。 因此，赋值操作的左侧操作数必须是一个可修改的左值。 在赋值后，赋值表达式具有左操作数的值，但不是左值。  
  
 **语法**  
  
 *assignment-expression*:  
 *conditional-expression*  
  
 *unary-expression assignment-operator assignment-expression*  
  
 *assignment-operator*: one of  
 **= \*=** `/=` `%=` `+=` **-= <\<= >>= &=** `^=` `|=`  
  
 C 中的赋值运算符可以在单个操作中转换值和赋值。 C 提供了以下赋值运算符：  
  
|运算符|执行的操作|  
|--------------|-------------------------|  
|**=**|简单赋值|  
|**\*=**|乘法赋值|  
|`/=`|除法赋值|  
|`%=`|余数赋值|  
|`+=`|加法赋值|  
|**-=**|减法赋值|  
|**<\<=**|左移赋值|  
|**>>=**|右移赋值|  
|**&=**|按位“与”赋值|  
|`^=`|按位“异或”赋值|  
|`&#124;=`|按位“与或”赋值|  
  
 在赋值中，右侧值的类型将转换为左侧值的类型，在完成赋值后，该值将存储在左操作数中。 左操作数不得为数组、函数或常量。 [类型转换](../c-language/type-conversions-c.md)中详细介绍了依赖两个类型的特定转换路径。  
  
## <a name="see-also"></a>请参阅  
 [赋值运算符](../cpp/assignment-operators.md)
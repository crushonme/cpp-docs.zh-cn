---
title: "unorm 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::unorm
- amp/Concurrency::graphics::unorm
dev_langs:
- C++
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: aae5de80bed3b2d3d5c15285c2d12f2f6771a251
ms.lasthandoff: 02/24/2017

---
# <a name="unorm-class"></a>unorm 类
表示 unorm 数。 每个元素是一个浮点数，范围内的 [0.0 f，1.0 f]。  
  
## <a name="syntax"></a>语法  
  
```  
class unorm;  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|说明|  
|----------|-----------------|  
|[unorm 构造函数](#ctor)|已重载。 默认构造函数。 初始化为 0.0f。|  
  
### <a name="public-operators"></a>公共运算符  
  
|名称|描述|  
|----------|-----------------|  
|unorm::operator-运算符||  
|unorm::operator float 运算符|转换运算符。 将 unorm 数字转换为浮点值。|  
|unorm::operator * = 运算符||  
|unorm::operator / = 运算符||  
|unorm::operator + + 运算符||  
|unorm::operator + = 运算符||  
|unorm::operator = 运算符||  
|unorm::operator-= 运算符||  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `unorm`  
  
## <a name="requirements"></a>要求  
 **标头︰** amp_short_vectors.h  
  
 **Namespace:** concurrency:: graphics  
  
##  <a name="a-namectora-unorm"></a><a name="ctor"></a>unorm 

 默认构造函数。 初始化为 0.0f。  
  
```  
unorm(
    void) restrict(amp,
    cpu);

 
explicit unorm(
    float _V) restrict(amp,
    cpu);

 
explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

 
explicit unorm(
    int _V) restrict(amp,
    cpu);

 
explicit unorm(
    double _V) restrict(amp,
    cpu);

 
unorm(
    const unorm& _Other) restrict(amp,
    cpu);

 
inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>参数  
 `_V`  
 用来初始化的值。  
  
 `_Other`  
 用于初始化的标准对象。  
  
## <a name="see-also"></a>另请参阅  
 [Concurrency:: graphics Namespace](concurrency-graphics-namespace.md)

---
title: "is_destructible 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- is_destructible
- std.is_destructible
- std::is_destructible
- type_traits/std::is_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- es-es
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: fecbfd44ca5b3e9d5d8b5d35637b7d1feb74ca48
ms.lasthandoff: 02/24/2017

---
# <a name="isdestructible-class"></a>is_destructible 类
测试该类型是否易损坏。  
  
## <a name="syntax"></a>语法  
  
```
template <class T>  
struct is_destructible;
```  
  
#### <a name="parameters"></a>参数  
 `T`  
 要查询的类型。  
  
## <a name="remarks"></a>备注  
 如果类型 `T` 是易损坏类型，则类型谓词的实例为 true；否则为 false。 易损坏类型是引用类型、对象类型以及那些在其中对于等于 `U` 的某些类型 `remove_all_extents_t<T>` 而言未计算操作数 `std::declval<U&>.~U()` 格式正确的类型。 其他类型（包括不完整类型、 `void`和函数类型）均不属于易损坏类型。  
  
## <a name="requirements"></a>要求  
 **标头：**\<type_traits>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>另请参阅  
 [<type_traits>](../standard-library/type-traits.md)




---
title: "moneypunct_byname 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xlocmon/std::moneypunct_byname
dev_langs: C++
helpviewer_keywords: moneypunct_byname class
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fd5c4774da1ea1c0afc25e1538351dad4decbe6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="moneypunctbyname-class"></a>moneypunct_byname 类
一种派生模板类，用于描述可充当给定区域设置的 `moneypunct` facet 的对象，从而能够格式化货币输入字段或货币输出字段。  
  
## <a name="syntax"></a>语法  
  
```
template <class CharType, bool Intl = false>
class moneypunct_byname : public moneypunct<CharType, Intl>
{
public:
    explicit moneypunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit moneypunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~moneypunct_byname();

};
```  
  
## <a name="remarks"></a>备注  
 其行为由已命名的区域设置 `_Locname` 决定。 每个构造函数通过 [moneypunct](../standard-library/moneypunct-class.md#moneypunct)\<CharType, Intl>( `_Refs`) 初始化其基对象。  
  
## <a name="requirements"></a>惠?  
 **标头：**\<locale>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>请参阅  
 [C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)




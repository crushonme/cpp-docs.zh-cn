---
title: "logic_error 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: stdexcept/std::logic_error
dev_langs: C++
helpviewer_keywords: logic_error class
ms.assetid: b290d73d-94e1-4288-af86-2bb5d71f677a
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a9f5afb57135d5358bc22496668dee6a91b23efd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="logicerror-class"></a>logic_error 类
此类用作引发报告执行程序前大概可检测的错误（例如，违反逻辑前提条件）的所有异常的基类。  
  
## <a name="syntax"></a>语法  
  
```  
class logic_error : public exception {  
public:  
    explicit logic_error(const string& message);

    explicit logic_error(const char *message);

};  
```  
  
## <a name="remarks"></a>备注  
 [what](../standard-library/exception-class.md) 返回的值是 **message**`.`[data](../standard-library/basic-string-class.md#data) 的副本。  
  
## <a name="example"></a>示例  
  
```cpp  
// logic_error.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   try   
   {  
      throw logic_error( "logic error" );  
   }  
   catch ( exception &e )   
   {  
      cerr << "Caught: " << e.what( ) << endl;  
      cerr << "Type: " << typeid( e ).name( ) << endl;  
   };  
}  
```  
  
 **输出**  
  
```  
Caught: logic error  
Type: class std::logic_error  
```  
  
## <a name="requirements"></a>惠?  
 **标头：**\<stdexcept>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>请参阅  
[exception 类](../standard-library/exception-class.md)  
 [C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)


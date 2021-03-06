---
title: "check_stack |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
dev_langs: C++
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e48952788e7bbef86ade1177ce243da503ec8b9b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="checkstack"></a>check_stack
指示编译器将关闭堆栈探测，如果**关闭**(或 **-** ) 指定，或者要关闭堆栈探测，如果**上**(或 **+** ) 指定。  
  
## <a name="syntax"></a>语法  
  
```  
  
      #pragma check_stack([ {on | off}] )  
#pragma check_stack{+ | -}  
```  
  
## <a name="remarks"></a>备注  
 如果未给定自变量，则根据默认设置处理堆栈探测。 此杂注出现后，当定义了第一个函数时，它就会生效。 堆栈探测既不是宏的一部分也不是以内联方式生成的函数的一部分。  
  
 如果你提供的自变量**check_stack**杂注，堆栈检查将还原为命令行上指定的行为。 有关详细信息，请参阅[编译器参考](../build/reference/compiler-options.md)。 交互**#pragma check_stack**和[/Gs](../build/reference/gs-control-stack-checking-calls.md)下表总结了选项。  
  
### <a name="using-the-checkstack-pragma"></a>使用 check_stack 杂注  
  
|语法|是否使用<br /><br /> /Gs 选项进行编译？|操作|  
|------------|------------------------------------|------------|  
|**#pragma check_stack （)**或<br /><br /> **#pragma check_stack**|是|为后面的函数关闭堆栈检查|  
|**#pragma check_stack （)**或<br /><br /> **#pragma check_stack**|否|为后面的函数打开堆栈检查|  
|**#pragma check_stack(on)**<br /><br /> 或**#pragma check_stack +**|是或否|为后面的函数打开堆栈检查|  
|**#pragma check_stack(off)**<br /><br /> 或**#pragma check_stack-**|是或否|为后面的函数关闭堆栈检查|  
  
## <a name="see-also"></a>请参阅  
 [Pragma 指令和 __Pragma 关键字](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
---
title: "独立特性 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- standalone attributes
- attributes [C++], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a3098fec700a498f73a86f8e1fd40609628a77d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="stand-alone-attributes"></a>独立特性
独立属性不对 c + + 关键字进行操作，但更类似的代码行。 独立特性语句需要行尾的分号。  
  
|特性|描述|  
|---------------|-----------------|  
|[cpp_quote](../windows/cpp-quote.md)|发出指定的字符串，而无需引号字符，到生成的头文件。|  
|[自定义](../windows/custom-cpp.md)|你可以定义自己的属性。|  
|[db_command](../windows/db-command.md)|创建 OLE DB 命令。|  
|[emitidl](../windows/emitidl.md)|确定是否将处理并放置在生成的.idl 文件中所有后续的 IDL 特性。|  
|[idl_module](../windows/idl-module.md)|在 DLL 中指定的入口点。|  
|[idl_quote](../windows/idl-quote.md)|允许你使用 Visual c + + 的当前版本中不支持的 IDL 构造并将它们传递到生成的.idl 文件。|  
|[import](../windows/import.md)|指定包含你想要从您的主要.idl 文件引用的定义的另一个.idl、.odl 或.h 文件。|  
|[importidl](../windows/importidl.md)|将指定的.idl 文件插入到生成的.idl 文件|  
|[importlib](../windows/importlib.md)|使已编译到另一个类型库中的类型可供所创建的类型库使用。|  
|[include](../windows/include-cpp.md)|指定要包含在生成的.idl 文件中的一个或多个标头文件。|  
|[includelib](../windows/includelib-cpp.md)|导致要包含在生成的.idl 文件的.idl 或.h 文件。|  
|[library_block](../windows/library-block.md)|将.idl 文件的库块中的构造。|  
|[模块](../windows/module-cpp.md)|定义.Idl 文件中的库块。|  
|[no_injected_text](../windows/no-injected-text.md)|阻止编译器将注入代码作为特性，请使用结果。|  
|[pragma](../windows/pragma.md)|发出指定的字符串，而无需引号字符，到生成的.idl 文件。|  
  
## <a name="see-also"></a>请参阅  
 [按用法分的特性](../windows/attributes-by-usage.md)
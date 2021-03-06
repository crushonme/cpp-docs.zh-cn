---
title: "importlib |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.importlib
dev_langs: C++
helpviewer_keywords: importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c62db5b1e10f115a57da1ea00cd87760b96a71f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="importlib"></a>importlib
使已编译到另一个类型库中的类型可供所创建的类型库使用。  
  
## <a name="syntax"></a>语法  
  
```  
  
      [ importlib(  
   "tlb_file"  
) ];  
```  
  
#### <a name="parameters"></a>参数  
 *tlb_file*  
 要导入当前项目类型库中的 .tlb 文件的名称（用引号引起来）。  
  
## <a name="remarks"></a>备注  
 **Importlib** c + + 特性将导致`importlib`语句放置在生成的.idl 文件的库块中。 **Importlib**属性具有相同的功能[importlib](http://msdn.microsoft.com/library/windows/desktop/aa367050) MIDL 特性。  
  
## <a name="example"></a>示例  
 下面的代码演示如何使用的示例**importlib**:  
  
```  
// cpp_attr_ref_importlib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importlib("importlib.tlb")];  
```  
  
## <a name="requirements"></a>惠?  
  
### <a name="attribute-context"></a>特性上下文  
  
|||  
|-|-|  
|**适用对象**|任何位置|  
|**可重复**|否|  
|**必需的特性**|无|  
|**无效的特性**|无|  
  
 有关详细信息，请参见 [特性上下文](../windows/attribute-contexts.md)。  
  
## <a name="see-also"></a>请参阅  
 [编译器特性](../windows/compiler-attributes.md)   
 [独立特性](../windows/stand-alone-attributes.md)   
 [导入](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [包括](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)
---
title: "添加属性 （Visual c + +） |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interfaces, adding properties
- properties [C++], adding to interfaces
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33fc8c3b5528c0ced4e0d402aec48791b7fbcb9a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-property-visual-c"></a>添加属性 (Visual C++)
你可以使用[添加属性向导](../ide/names-add-property-wizard.md)添加到你的项目中的接口的方法。  
  
### <a name="to-add-a-property-to-your-object"></a>若要将属性添加到你的对象  
  
1.  在[类视图](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)，右键单击你想要添加的属性的接口的名称。  
  
    > [!NOTE]
    >  你还可以将属性添加到调度接口，该项目已特性化，除非嵌套在库节点。  
  
2.  从快捷菜单中，单击**添加**，然后单击**添加属性**。  
  
3.  在[添加属性向导](../ide/names-add-property-wizard.md)，提供信息来创建属性。  
  
4.  指定的属性中的任何接口定义语言 (IDL) 设置[IDL 特性](../ide/idl-attributes-add-property-wizard.md)向导页。  
  
5.  单击**完成**以添加属性。  
  
 **获取**和`Put`作为在类视图中，在其中定义的接口的两个图标显示的属性的方法。 你可以双击以查看.idl 文件中的属性声明这两个图标。  
  
-   ATL 接口**获取**和**放**函数添加到.cpp 文件中，并且对这些函数的引用添加到.h 文件。  
  
-   对于 MFC 调度接口，如果你选择**成员变量**作为实现类型时，一个方法和变量添加到实现该接口的类。 如果你选择**Get/Set 方法**作为实现类型中，两种方法添加到实现该接口的类。  
  
## <a name="see-also"></a>请参阅  
 [创建 COM 接口](../ide/creating-a-com-interface-visual-cpp.md)   
 [编辑 COM 接口](../ide/editing-a-com-interface.md)   
 [组件对象模型](http://msdn.microsoft.com/library/windows/desktop/ms694363)   
 [接口指针和接口](http://msdn.microsoft.com/library/windows/desktop/ms688484)
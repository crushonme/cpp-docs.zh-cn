---
title: "OLE 后台： 实现策略 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE [MFC], development strategy
- OLE applications [MFC], implementing OLE
- applications [OLE], implementing OLE
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7325cb5cb7be4750507d8694ba8bc5efc3ce8606
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="ole-background-implementation-strategies"></a>OLE 后台：实现策略
根据您的应用程序，添加 OLE 支持有四个可能的实现策略：  
  
-   您要编写一个新应用程序。  
  
     这种情况下的工作量通常最小。 您运行 MFC 应用程序向导并选择高级功能或复合文档支持以创建主干应用程序。 有关这些选项及其作用的信息，请参阅文章[创建 MFC EXE 程序](../mfc/reference/mfc-application-wizard.md)。  
  
-   您有一个使用不支持 OLE 的 Microsoft 基础类库 2.0 版或更高版本编写的程序。  
  
     如前文所述使用 MFC 应用程序向导创建新应用程序，然后将新应用程序中的代码复制并粘贴到你的现有应用程序中。 这对服务器、容器或自动化应用程序都有效。 请参阅 MFC [SCRIBBLE](../visual-cpp-samples.md)示例有关此策略的示例。  
  
-   您有一个实现 OLE 1.0 版支持的 Microsoft 基础类库程序。  
  
     请参阅[MFC 技术说明 41](../mfc/tn041-mfc-ole1-migration-to-mfc-ole-2.md)有关此转换策略。  
  
-   您有一个并非使用 Microsoft 基础类编写并且不一定实现了 OLE 支持的应用程序。  
  
     这种情况下的工作量最大。 一个方法是创建新应用程序（与在第一个策略中一样），然后将现有代码复制并粘贴到该应用程序中。 如果现有代码是在 C 中编写的，则可能需要修改它，以便让它能够编译为 C++ 代码。 如果 C 代码调用了 Windows API，则不必将其更改为使用 Microsoft 基础类。 此方法可能需要对您的程序进行一些重构以支持 Microsoft 基础类 2.0 版和更高版本使用的文档/视图体系结构。 有关此体系结构的详细信息，请参阅[技术说明 25](../mfc/tn025-document-view-and-frame-creation.md)。  
  
 一旦你已决定一个策略，您应该阅读[容器](../mfc/containers.md)或[服务器](../mfc/servers.md)（具体取决于你正在编写的应用程序的类型） 文章或检查示例程序，或者两者。 MFC OLE 示例[OCLIENT](../visual-cpp-samples.md)和[HIERSVR](../visual-cpp-samples.md)显示如何分别实现容器和服务器的各个方面。 在这些文章中的不同地方，将会提到这些示例中的某些函数作为要讨论的技术的示例。  
  
## <a name="see-also"></a>请参阅  
 [OLE 后台](../mfc/ole-background.md)   
 [容器： 实现容器](../mfc/containers-implementing-a-container.md)   
 [服务器： 实现服务器](../mfc/servers-implementing-a-server.md)   
 [MFC 应用程序向导](../mfc/reference/mfc-application-wizard.md)


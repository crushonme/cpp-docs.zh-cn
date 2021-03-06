---
title: "自动化管理器 (MFC) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Automation Manager
- Automation servers, Automation Manager
- Automation, Automation Manager
- Remote Automation, Automation Manager
- Automation clients, Automation Manager
- AUTMGR32.exe
ms.assetid: 6bf3429e-1946-41c5-86d0-ad7f5b8585b8
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 338b619580ef7967d871ff3f960fc467555ab72a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="automation-manager-mfc"></a>自动化管理器 (MFC)
应该将 AUTMGR32.EXE 复制到用来提供远程自动化对象的每台计算机的 Windows 系统目录。 对于 Windows 95 和 Windows 98，此目录通常是 C:\WINDOWS\SYSTEM。 对于 Windows 2000 和 Windows NT，此目录通常是 C:\WINNT\SYSTEM32。  
  
 如果要启用从服务器到客户端的回调，则还应将此可执行文件复制到每台客户端计算机的系统目录。  
  
 当自动化管理器运行时，它会在服务器计算机上显示包含简要状态信息的小窗口。 如果要隐藏它，请参阅 Microsoft 知识库中的文章 Q138067。  
  
## <a name="see-also"></a>请参阅  
 [远程自动化连接管理器](../mfc/remote-automation-connection-manager.md)   
 [远程自动化用户组件](../mfc/remote-automation-user-components.md)   
 [远程自动化安装](../mfc/remote-automation-installation.md)


---
title: "橡皮带线条和跟踪器 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3bd9da00d2d6ea0110562f523a0adc53c1a476c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="rubber-banding-and-trackers"></a>橡皮筋和跟踪器
提供有跟踪器的其他功能是“橡皮筋”选择，该功能允许用户通过围绕要选择的项拖动调整大小矩形来选择多个 OLE 项。 当用户松开鼠标左键后，用户选定区域中的项将选定并且可由用户进行操作。 例如，用户可以将选择拖进另一个容器应用程序。  
  
 实现此功能需要应用程序的 `WM_LBUTTONDOWN` 处理程序函数中的一些其他代码。  
  
 以下代码示例实现橡皮筋选择和其他功能。  
  
 [!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]  
  
 如果你想要允许在橡皮筋法期间方向可逆跟踪器，则应调用[crecttracker:: Trackrubberband](../mfc/reference/crecttracker-class.md#trackrubberband)第三个参数设置为**TRUE**。 请记住，允许可逆方向有时将导致[crecttracker:: M_rect](../mfc/reference/crecttracker-class.md#m_rect)反向。 这可以通过调用更正[crect:: Normalizerect](../atl-mfc-shared/reference/crect-class.md#normalizerect)。  
  
 有关详细信息，请参阅[容器客户端项](../mfc/containers-client-items.md)和[自定义拖放](../mfc/drag-and-drop-customizing.md)。  
  
## <a name="see-also"></a>请参阅  
 [跟踪器： 在 OLE 应用程序中实现跟踪器](../mfc/trackers-implementing-trackers-in-your-ole-application.md)   
 [CRectTracker 类](../mfc/reference/crecttracker-class.md)

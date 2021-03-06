---
title: "Rebar 控件和带区 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6426a25746858ed5bd7c0d8ef70575e029453bae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="rebar-controls-and-bands"></a>Rebar 控件和带区
Rebar 控件的主要用途是充当子窗口、 通用对话框控件、 菜单、 工具栏和等等的容器。 此包含支持的"带。"的概念 每个 rebar 带区可以包含一个手柄栏、 位图、 文本标签和子窗口的任意组合。  
  
 类`CReBarCtrl`具有许多成员函数，可以使用来检索，并且操作特定 rebar 带区的信息：  
  
-   [GetBandCount](../mfc/reference/crebarctrl-class.md#getbandcount)检索 rebar 控件中的当前带区的数目。  
  
-   [GetBandInfo](../mfc/reference/crebarctrl-class.md#getbandinfo)初始化**REBARBANDINFO**使用指定的带区中的信息的结构。 具有对应[SetBandInfo](../mfc/reference/crebarctrl-class.md#setbandinfo)成员函数。  
  
-   [GetRect](../mfc/reference/crebarctrl-class.md#getrect)检索指定的带区的边框。  
  
-   [GetRowCount](../mfc/reference/crebarctrl-class.md#getrowcount)检索的 rebar 控件中的带行数。  
  
-   [IDToIndex](../mfc/reference/crebarctrl-class.md#idtoindex)检索指定带外的索引。  
  
-   [GetBandBorders](../mfc/reference/crebarctrl-class.md#getbandborders)检索带区的边框。  
  
 除了操作，多个成员函数不提供，可让你对特定 rebar 带区进行操作。  
  
 [InsertBand](../mfc/reference/crebarctrl-class.md#insertband)和[DeleteBand](../mfc/reference/crebarctrl-class.md#deleteband)添加和删除 rebar 带区。 [MinimizeBand](../mfc/reference/crebarctrl-class.md#minimizeband)和[MaximizeBand](../mfc/reference/crebarctrl-class.md#maximizeband)影响特定 rebar 带区的当前大小。 [MoveBand](../mfc/reference/crebarctrl-class.md#moveband)更改特定 rebar 带区的索引。 [ShowBand](../mfc/reference/crebarctrl-class.md#showband)显示或隐藏从用户 rebar 带区。  
  
 下面的示例演示如何添加工具栏带 (`m_wndToolBar`) 到现有 rebar 控件 (`m_wndReBar`)。 初始化描述带`rbi`结构，然后再调用`InsertBand`成员函数：  
  
 [!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]  
  
## <a name="see-also"></a>请参阅  
 [使用 CReBarCtrl](../mfc/using-crebarctrl.md)   
 [控件](../mfc/controls-mfc.md)


---
title: "NMAKE 警告 U4004 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U4004
dev_langs: C++
helpviewer_keywords: U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcbda9dd9d7ca5ecb99e46b9916fb95c2c560e49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-warning-u4004"></a>NMAKE 警告 U4004
太多规则目标 targetname  
  
 已为给定的目标使用单冒号指定多个描述块 (**:**) 作为分隔符。 NMAKE 在第一个描述块中执行命令并忽略更高版本的块。  
  
 若要在多个依赖项中指定相同的目标，使用双冒号 (`::`) 为在每个依赖项的行分隔符。
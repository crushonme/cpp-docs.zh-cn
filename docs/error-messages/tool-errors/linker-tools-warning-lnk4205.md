---
title: "链接器工具警告 LNK4205 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4205
dev_langs: C++
helpviewer_keywords: LNK4205
ms.assetid: d63b9d18-ef3c-4081-9d8d-93077dad13c2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fdf9cf0da51b7bb034984fceca209a110e81d54d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4205"></a>链接器工具警告 LNK4205
filename 缺少引用模块中; 当前调试信息正在链接对象，如同没有调试信息  
  
 .Pdb 文件包含过期信息。 链接器将继续链接对象但不调试信息。 你可能想要重新编译对象文件使用[/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)选项。
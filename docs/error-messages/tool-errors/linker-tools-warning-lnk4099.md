---
title: "链接器工具警告 LNK4099 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4099
dev_langs: C++
helpviewer_keywords: LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 364c2f9303707328ebf3bdf3284398e6d4f9f0d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4099"></a>链接器工具警告 LNK4099
PDB filename 找不到与对象/库 ' 或 'path';正在链接对象，如同没有调试信息  
  
 链接器无法找到.pdb 文件。 将其复制到包含的目录`object/library`。  
  
 若要查找的对象文件与关联的.pdb 文件的名称：  
  
1.  从库中，与提取的对象文件[lib](../../build/reference/lib-reference.md) **/提取：**`objectname`**.obj** `xyz` **.lib**。  
  
2.  检查包含的.pdb 文件的路径**dumpbin /section:.debug$ T /rawdata** `objectname` **.obj**。  
  
 此外可以使用编译[/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)，因此不需要使用，或者删除 pdb [/调试](../../build/reference/debug-generate-debug-info.md)链接器选项，如果你没有要链接的对象的.pdb 文件。
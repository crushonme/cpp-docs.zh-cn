---
title: "-DEBUGTYPE （调试信息选项） |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /debugtype
dev_langs: C++
helpviewer_keywords:
- /DEBUGTYPE linker option
- DEBUGTYPE linker option
- -DEBUGTYPE linker option
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c069caca9831b841c3cb4be347331b58f538ba6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="debugtype-debug-info-options"></a>/DEBUGTYPE（调试信息选项）
/DEBUGTYPE 选项指定 /DEBUG 选项生成的调试信息的类型。  
  
```  
/DEBUGTYPE:[CV | PDATA | FIXUP]  
```  
  
## <a name="arguments"></a>自变量  
 CV  
 指示链接器针对 PDB 文件中的符号、行号和其他对象编译信息发出调试信息。 默认情况下，启用此选项时**/调试**指定和**/DEBUGTYPE**未指定。  
  
 PDATA  
 指示链接器向 PDB 文件中的调试流信息添加 .pdata 和 .xdata 条目。 默认情况下，启用此选项时同时**/调试**和**/DRIVER**所指定的选项。 如果**/DEBUGTYPE:PDATA**单独指定，链接器会自动包括调试 PDB 文件中的符号。 如果**/DEBUGTYPE:PDATA，修正**指定，则链接器不包括调试 PDB 文件中的符号。  
  
 FIXUP  
 指示链接器向 PDB 文件中的调试流信息添加重定位表条目。 默认情况下，启用此选项时同时**/调试**和**/配置文件**所指定的选项。 如果**/DEBUGTYPE:FIXUP**或**/DEBUGTYPE:FIXUP，PDATA**指定，则链接器不包括调试 PDB 文件中的符号。  
  
 自变量**/DEBUGTYPE**可能按任何顺序组合并用逗号分隔。 **/DEBUGTYPE**选项和其自变量不区分大小写。  
  
## <a name="remarks"></a>备注  
 使用**/DEBUGTYPE**选项以指定在调试流中包含重定位表数据或.pdata 和.xdata 标头信息。 这导致链接器包含有关破坏内核模式代码时内核调试程序中可见的用户模式代码的信息。 要使调试符号可用时**修正**是指定，包括**CV**自变量。  
  
 若要在用户模式，这是典型的应用程序，调试代码**/DEBUGTYPE**无需选项。 默认情况下，输出指定调试编译器开关 ([/Z7、 /Zi、 /ZI](../../build/reference/z7-zi-zi-debug-information-format.md)) 发出所有信息需要由 Visual Studio 调试器。 使用**/DEBUGTYPE:PDATA**或**/DEBUGTYPE:CV，PDATA，修正**用户模式和内核模式组件，比如设备驱动程序的配置应用组合的代码进行调试。 有关内核模式调试程序的详细信息，请参阅[Windows 调试工具 （WinDbg、 KD、 CDB、 NTSD）](http://go.microsoft.com/fwlink/p?LinkID=285651)  
  
## <a name="see-also"></a>请参阅  
 [/DEBUG （生成调试信息）](../../build/reference/debug-generate-debug-info.md)   
 [/ 驱动程序 （Windows NT 内核模式驱动程序）](../../build/reference/driver-windows-nt-kernel-mode-driver.md)   
 [/ 配置文件 （性能工具分析器）](../../build/reference/profile-performance-tools-profiler.md)   
 [适用于 Windows （WinDbg、 KD、 CDB、 NTSD） 的调试工具](http://go.microsoft.com/fwlink/p?LinkID=285651)
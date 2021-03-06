---
title: "-等待 （启用协同程序支持） |Microsoft 文档"
ms.custom: 
ms.date: 08/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /await
- -await
dev_langs: C++
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 47134532b16d1b5a907e4ed3170a0827316d7c65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="await-enable-coroutine-support"></a>/ await （启用协同程序支持）  
  
使用**/ await**编译器选项来启用协同程序的编译器支持。  
  
## <a name="syntax"></a>语法  
  
> await /  
  
## <a name="remarks"></a>备注  
  
**/ Await**编译器选项启用 c + + 协同程序和关键字的编译器支持**co_await**， **co_yield**，和**co_return**. 默认情况下，此选项处于关闭状态。 有关 Visual Studio 中的协同程序支持的信息，请参阅[Visual Studio 团队博客](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/)。 有关协同程序标准建议的详细信息，请参阅[N4628 工作草案、 协同程序的 c + + 扩展的技术规范](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/n4628.pdf)。  

**/ Await**选项是 Visual Studio 2015 中的开始提供。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项  
  
1. 打开你的项目的**属性页**对话框。   
  
2. 下**配置属性**，展开**C/c + +**文件夹，然后选择**命令行**属性页。  
  
3. 输入**/ await**中的编译器选项**其他选项**框。 选择**确定**或**应用**以保存所做的更改。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项  
  
-   请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。  
  
## <a name="see-also"></a>请参阅  
  
[编译器选项](../../build/reference/compiler-options.md)   
[设置编译器选项](../../build/reference/setting-compiler-options.md)
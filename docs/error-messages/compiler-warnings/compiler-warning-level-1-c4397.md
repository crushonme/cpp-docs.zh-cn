---
title: "编译器警告 （等级 1） C4397 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4397
dev_langs: C++
helpviewer_keywords: C4397
ms.assetid: 6346fdc2-dbbf-4fba-803a-32b0d0a707be
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eae4518c731327a59d7efd049e25a823922bc65c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4397"></a>编译器警告（等级 1）C4397
忽略 DefaultCharSetAttribute  
  
 <xref:System.Runtime.InteropServices.DefaultCharSetAttribute>Visual c + + 编译器会忽略。 若要指定 DLL 字符集，请使用 DllImport CharSet 选项。 有关详细信息，请参阅[使用 c + + 互操作 (隐式 PInvoke)](../../dotnet/using-cpp-interop-implicit-pinvoke.md)。  
  
## <a name="example"></a>示例  
 下面的示例生成 C4397。  
  
```  
// C4397.cpp  
// compile with: /W1 /c /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[module:DefaultCharSetAttribute(CharSet::Unicode)];   // C4397  
  
[DllImport("kernel32", EntryPoint="CloseHandle", CharSet=CharSet::Unicode)]   // OK  
extern "C" bool ImportDefault(IntPtr hObject);  
  
public ref class MySettingVC {  
public:  
   void method() {  
      ImportDefault(IntPtr::Zero);  
   }  
};  
  
[StructLayout(LayoutKind::Explicit)]  
public ref struct StructDefault1{};  
  
public ref class ClassDefault1{};  
```
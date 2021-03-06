---
title: "Platform:: writeonlyarray 类 |Microsoft 文档"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
s.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::WriteOnlyArray::begin
- VCCORLIB/Platform::WriteOnlyArray::Data
- VCCORLIB/Platform::WriteOnlyArray::end
- VCCORLIB/Platform::WriteOnlyArray::FastPass
- VCCORLIB/Platform::WriteOnlyArray::Length
- VCCORLIB/Platform::WriteOnlyArray::set
dev_langs: C++
helpviewer_keywords: Platform::WriteOnlyArray Class
ms.assetid: 92d7dd56-ec58-4b8c-88ba-9c903668b687
caps.latest.revision: "11"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d63072e3190929f5191f3d515b73dbd6a6a75040
ms.sourcegitcommit: 6f40bba1772a09ff0e3843d5f70b553e1a15ab50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2018
---
# <a name="platformwriteonlyarray-class"></a>Platform::WriteOnlyArray 类
表示一个一维数组，当调用方为要填充的方法传递数组时，可将此一维数组用作输入参数。  
  
 此 ref 类在 vccorlib.h 中声明为私有；因此，它不是通过元数据发出的，只能通过 C++ 使用它。 此类仅用作输入参数，用于接收调用方分配的数组。 此类无法通过用户代码构造。 它允许 C++ 方法直接写入到该数组中，这种模式称为“FillArray”  模式。 有关详细信息，请参阅[Array 和 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)。  
  
## <a name="syntax"></a>语法  
  
```cpp  
private ref class WriteOnlyArray<T, 1>  
```  
  
### <a name="members"></a>成员  
  
### <a name="public-methods"></a>公共方法  
 这些方法具有内部可访问性，即，只能在 C++ 应用或组件中访问这些方法。  
  
|name|描述|  
|----------|-----------------|  

|[Writeonlyarray:: Begin](#begin)|指向数组的第一个元素的迭代器。 |  
|[Writeonlyarray:: Data](#data)|指向数据缓冲区的指针。 |  
|[Writeonlyarray:: End](#end)|指向一个过去的数组中的最后一个元素的迭代器。 |  
|[Writeonlyarray:: Fastpass](#fastpass)|指示数组能否使用 FastPass 机制，后者是系统透明执行的优化。 请勿在你的代码使用此 |  
|[Writeonlyarray:: Length](#length)|返回数组中元素的数目。 |  
|[Writeonlyarray:: Set](#set)|将指定的元素设置为指定的值。 |  

  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `WriteOnlyArray`  
  
### <a name="requirements"></a>惠?  
 编译器选项： **/ZW**  
  
 **元数据：** Platform.winmd  
  
 **命名空间：** Platform  

## <a name="begin"></a>  WriteOnlyArray::begin 方法
返回一个指向数组中第一个元素的指针。  
  
### <a name="syntax"></a>语法  
  
```cpp  
T* begin() const;  
```  
  
### <a name="return-value"></a>返回值  
 指向数组中第一个元素的指针。  
  
### <a name="remarks"></a>备注  
 此迭代器可与 STL 算法（如 `std::sort`）一起使用以操作数组中的元素。  
  


## <a name="data"></a>  WriteOnlyArray::Data 属性
指向数据缓冲区的指针。  
  
### <a name="syntax"></a>语法  
  
```cpp  
property T* Data{  
   T* get() const;  
}  
```  
  
### <a name="return-value"></a>返回值  
 指向原始数组字节的指针。  
  


## <a name="end"></a>  WriteOnlyArray::end 方法
返回一个指向数组中最后一个元素的下一位置的指针。  
  
### <a name="syntax"></a>语法  
  
```cpp  
T* end() const;  
```  
  
### <a name="return-value"></a>返回值  
 指向数组中最后一个元素的下一位置的指针迭代器。  
  
### <a name="remarks"></a>备注  
 此迭代器可与 STL 算法（如 `std::sort`）一起使用以对数组元素执行操作。  
  


## <a name="fastpass"></a>  WriteOnlyArray::FastPass 属性
指示能否执行内部 FastPass 优化。 不用于用户代码。  
  
### <a name="syntax"></a>语法  
  
```cpp  
property bool FastPass{  
   bool get() const;  
}  
```  
  
### <a name="return-value"></a>返回值  
 指示数组是否为 FastPass 的布尔值。  
  


## <a name="get"></a>Writeonlyarray:: Get 方法
返回指定索引处的元素。  
  
### <a name="syntax"></a>语法  
  
```cpp  
T& get(  
   unsigned int indexArg) const;  
```  
  
### <a name="parameters"></a>参数  
 `indexArg`  
  
### <a name="return-value"></a>返回值  
  


## <a name="length"></a>  WriteOnlyArray::Length 属性
返回调用方分配的数组中的元素数目。  
  
### <a name="syntax"></a>语法  
  
```cpp  
property unsigned int Length{  
   unsigned int get() const;  
}  
```  
  
### <a name="return-value"></a>返回值  
 数组中的元素数。  
  


## <a name="set"></a>  WriteOnlyArray::set 函数
在数组中指定索引处设置指定值。  
  
### <a name="syntax"></a>语法  
  
```cpp  
T& set(  
   unsigned int indexArg,  
   T valueArg);  
```  
  
### <a name="parameters"></a>参数  
 `indexArg`  
 要设置的元素的索引。  
  
 `valueArg`  
 要在 `indexArg` 设置的值。  
  
### <a name="return-value"></a>返回值  
 对刚刚设置的元素的引用。  
  

  
### <a name="remarks"></a>备注  
 有关如何解释 HRESULT 值的详细信息，请参阅[COM 错误代码的结构](http://go.microsoft.com/fwlink/p/?LinkId=262045)。  
  
  
## <a name="see-also"></a>请参阅  
 [平台 Namespace](platform-namespace-c-cx.md)   
 [C + + 创建 Windows 运行时组件](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
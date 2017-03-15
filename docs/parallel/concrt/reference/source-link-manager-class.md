---
title: "source_link_manager 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::source_link_manager
dev_langs:
- C++
helpviewer_keywords:
- source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: b9323da4d2ccefe09ba38df088e546828d41f2ee
ms.lasthandoff: 02/24/2017

---
# <a name="sourcelinkmanager-class"></a>source_link_manager 类
`source_link_manager` 对象管理到 `ISource` 块的消息块网络链接。  
  
## <a name="syntax"></a>语法  
  
```
template<class _LinkRegistry>
class source_link_manager;
```  
  
#### <a name="parameters"></a>参数  
 `_LinkRegistry`  
 网络链接注册表中。  
  
## <a name="members"></a>成员  
  
### <a name="public-typedefs"></a>公共 Typedef  
  
|名称|说明|  
|----------|-----------------|  
|`const_pointer`|提供指向的指针的类型`const`中的元素`source_link_manager`对象。|  
|`const_reference`|提供对引用的类型`const`元素存储在`source_link_manager`用于读取和执行 const 操作的对象。|  
|`iterator`|提供的迭代器的类型可读取或修改中的任何元素`source_link_manager`对象。|  
|`type`|类型由链接注册表`source_link_manager`对象。|  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|说明|  
|----------|-----------------|  
|[source_link_manager 构造函数](#ctor)|构造 `source_link_manager` 对象。|  
|[~ source_link_manager 析构函数](#dtor)|销毁`source_link_manager`对象。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[添加方法](#add)|添加源链接到`source_link_manager`对象。|  
|[begin 方法](#begin)|返回一个迭代中的第一个元素指向`source_link_manager`对象。|  
|[包含方法](#contains)|搜索`network_link_registry`在此`source_link_manager`对象指定块。|  
|[count 方法](#count)|对链接中的块数量进行计数`source_link_manager`对象。|  
|[引用方法](#reference)|获取在上一个引用`source_link_manager`对象。|  
|[register_target_block 方法](#register_target_block)|注册持有此目标块`source_link_manager`对象。|  
|[release 方法](#release)|在释放该引用`source_link_manager`对象。|  
|[remove 方法](#remove)|移除从链接`source_link_manager`对象。|  
|[set_bound 方法](#set_bound)|设置源链接，可以添加到此最大数目`source_link_manager`对象。|  
  
## <a name="remarks"></a>备注  
 目前，源块没有引用计数。 这是一个包装上`network_link_registry`对象，它允许对链接的并发访问，并提供能够引用通过回调的链接。 消息块 ( `target_block`s 或`propagator_block`s) 应使用此类用于其源链接。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `source_link_manager`  
  
## <a name="requirements"></a>要求  
 **标头：** agents.h  
  
 **命名空间：** 并发  
  
##  <a name="a-nameadda-add"></a><a name="add"></a>添加 

 添加源链接到`source_link_manager`对象。  
  
```
void add(_EType _Link);
```  
  
### <a name="parameters"></a>参数  
 `_Link`  
 指向要添加的块的指针。  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>开始 

 返回一个迭代中的第一个元素指向`source_link_manager`对象。  
  
```
iterator begin();
```  
  
### <a name="return-value"></a>返回值  
 发现的第一个元素的迭代器`source_link_manager`对象。  
  
### <a name="remarks"></a>备注  
 迭代器的最终状态由`NULL`链接。  
  
##  <a name="a-namecontainsa-contains"></a><a name="contains"></a>包含 

 搜索`network_link_registry`在此`source_link_manager`对象指定块。  
  
```
bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>参数  
 `_Link`  
 指向要在其中搜索中的块的指针`source_link_manager`对象。  
  
### <a name="return-value"></a>返回值  
 `true`如果找到指定的块，`false`否则为。  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>计数 

 对链接中的块数量进行计数`source_link_manager`对象。  
  
```
size_t count();
```  
  
### <a name="return-value"></a>返回值  
 在链接块数`source_link_manager`对象。  
  
##  <a name="a-namereferencea-reference"></a><a name="reference"></a>引用 

 获取在上一个引用`source_link_manager`对象。  
  
```
void reference();
```  
  
##  <a name="a-nameregistertargetblocka-registertargetblock"></a><a name="register_target_block"></a>register_target_block 

 注册持有此目标块`source_link_manager`对象。  
  
```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```  
  
### <a name="parameters"></a>参数  
 `_PTarget`  
 目标块持有这`source_link_manager`对象。  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>版本 

 在释放该引用`source_link_manager`对象。  
  
```
void release();
```  
  
##  <a name="a-nameremovea-remove"></a><a name="remove"></a>删除 

 移除从链接`source_link_manager`对象。  
  
```
bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>参数  
 `_Link`  
 指向块被删除，如果找到。  
  
### <a name="return-value"></a>返回值  
 `true`如果找到该链接并将其删除，`false`否则为。  
  
##  <a name="a-namesetbounda-setbound"></a><a name="set_bound"></a>set_bound 

 设置源链接，可以添加到此最大数目`source_link_manager`对象。  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>参数  
 `_MaxLinks`  
 最大链接数。  
  
##  <a name="a-namectora-sourcelinkmanager"></a><a name="ctor"></a>source_link_manager 

 构造 `source_link_manager` 对象。  
  
```
source_link_manager();
```  
  
##  <a name="a-namedtora-sourcelinkmanager"></a><a name="dtor"></a>~ source_link_manager 

 销毁`source_link_manager`对象。  
  
```
~source_link_manager();
```  
  
## <a name="see-also"></a>另请参阅  
 [并发 Namespace](concurrency-namespace.md)   
 [single_link_registry 类](single-link-registry-class.md)   
 [multi_link_registry 类](multi-link-registry-class.md)

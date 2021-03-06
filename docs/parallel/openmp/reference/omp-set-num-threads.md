---
title: "omp_set_num_threads |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_set_num_threads
dev_langs: C++
helpviewer_keywords: omp_set_num_threads OpenMP function
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 49383e47c161c7cec59f3f0fb7c618f4c4924655
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="ompsetnumthreads"></a>omp_set_num_threads
在后续的并行区域设置的线程数，除非通过重写[num_threads](../../../parallel/openmp/reference/num-threads.md)子句。  
  
## <a name="syntax"></a>语法  
  
```  
void omp_set_num_threads(  
   int num_threads  
);  
```  
  
## <a name="remarks"></a>备注  
 其中，  
  
 `num_threads`  
 并行区域中的线程数。  
  
## <a name="remarks"></a>备注  
 有关详细信息，请参阅[3.1.1 omp_set_num_threads 函数](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)。  
  
## <a name="example"></a>示例  
 请参阅[omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)有关的使用示例`omp_set_num_threads`。  
  
## <a name="see-also"></a>请参阅  
 [函数](../../../parallel/openmp/reference/openmp-functions.md)
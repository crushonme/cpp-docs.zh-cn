---
title: "omp_get_wtime |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_get_wtime
dev_langs: C++
helpviewer_keywords: omp_get_wtime OpenMP function
ms.assetid: c8dee105-ec1b-42e5-a6e3-edeedcf9854c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3c9a4d66789a94e30c2562c5a6d071cab1012b32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="ompgetwtime"></a>omp_get_wtime
返回从某一时刻已用时间的秒中的值。  
  
## <a name="syntax"></a>语法  
  
```  
double omp_get_wtime( );  
```  
  
## <a name="return-value"></a>返回值  
 返回一个值以秒为单位的时间已用从一些任意的但一致的点。  
  
## <a name="remarks"></a>备注  
 在程序执行，因此后续比较可能会导致过程，该点将保持一致。  
  
 有关详细信息，请参阅[3.3.1 omp_get_wtime 函数](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md)。  
  
## <a name="example"></a>示例  
  
```  
// omp_get_wtime.cpp  
// compile with: /openmp  
#include "omp.h"  
#include <stdio.h>  
#include <windows.h>  
  
int main() {  
    double start = omp_get_wtime( );  
    Sleep(1000);  
    double end = omp_get_wtime( );  
    double wtick = omp_get_wtick( );  
  
    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",  
             start, end, end - start);  
  
    printf_s("wtick = %.16g\n1/wtick = %.16g\n",  
             wtick, 1.0 / wtick);  
}  
```  
  
```Output  
start = 594255.3671159324  
end = 594256.3664474116  
diff = 0.9993314791936427  
wtick = 2.793651148400146e-007  
1/wtick = 3579545  
```  
  
## <a name="see-also"></a>请参阅  
 [函数](../../../parallel/openmp/reference/openmp-functions.md)
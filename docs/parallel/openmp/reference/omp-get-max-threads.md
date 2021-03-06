---
title: "omp_get_max_threads |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- omp_get_max_threads
dev_langs:
- C++
helpviewer_keywords:
- omp_get_max_threads OpenMP function
ms.assetid: f47c3725-3e40-469f-8bc8-a1e47f264cc3
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8acb323a72300a3e613c0b8df8f5dfadd6de7643
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ompgetmaxthreads"></a>omp_get_max_threads
場合は、並列領域なしで利用できるスレッドの数を示す整数を返します[num_threads](../../../parallel/openmp/reference/num-threads.md)コードでその時点で定義されています。  
  
## <a name="syntax"></a>構文  
  
```  
int omp_get_max_threads( )  
```  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [3.1.3 omp_get_max_threads 関数](../../../parallel/openmp/3-1-3-omp-get-max-threads-function.md)します。  
  
## <a name="example"></a>例  
  
```  
// omp_get_max_threads.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_num_threads(8);  
    printf_s("%d\n", omp_get_max_threads( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_max_threads( ));  
        }  
  
    printf_s("%d\n", omp_get_max_threads( ));  
  
    #pragma omp parallel num_threads(3)  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_max_threads( ));  
        }  
  
    printf_s("%d\n", omp_get_max_threads( ));  
}  
```  
  
```Output  
8  
8  
8  
8  
8  
```  
  
## <a name="see-also"></a>関連項目  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)

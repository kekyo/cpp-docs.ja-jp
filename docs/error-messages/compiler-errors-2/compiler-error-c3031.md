---
title: "コンパイラ エラー C3031 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3031
dev_langs: C++
helpviewer_keywords: C3031
ms.assetid: 7e621e7e-eda7-45b5-8836-29599cd05255
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3ddf6809081cae78d0280c57f9ecc156f82e2821
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3031"></a>コンパイラ エラー C3031
'var': 'reduction' 句の変数には、スカラー演算型を指定しなければなりません  
  
 間違った型の変数が reduction 句に渡されました。  
  
 次の例では C3031 が生成されます。  
  
```  
// C3031.cpp  
// compile with: /openmp /link vcomps.lib  
#include <stdio.h>  
#include "omp.h"  
  
typedef struct {  
   int n;  
} Incomplete;  
  
extern Incomplete inc;  
int i = 9;  
  
int main() {  
   #pragma omp parallel reduction(+: inc)   // C3031   
      ;  
  
   #pragma omp parallel reduction(+: i)     // OK  
      ;  
}  
```
---
title: "共有 (OpenMP) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Shared
dev_langs: C++
helpviewer_keywords: shared OpenMP clause
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 966584b3a294551560bb88430a2424f353a1e3b2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="shared-openmp"></a>shared (OpenMP)
すべてのスレッド間で 1 つまたは複数の変数を共有する必要がありますを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
shared(var)  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `var`  
 共有する 1 つ以上の変数です。 複数の変数が指定されている場合は、変数名をコンマで区切ります。  
  
## <a name="remarks"></a>コメント  
 スレッド間で変数を共有する別の方法は、 [copyprivate](../../../parallel/openmp/reference/copyprivate.md)句。  
  
 `shared`次のディレクティブに適用されます。  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [セクション](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、次を参照してください。[共有 2.7.2.4](../../../parallel/openmp/2-7-2-4-shared.md)です。  
  
## <a name="example"></a>例  
 参照してください[プライベート](../../../parallel/openmp/reference/private-openmp.md)の使用例については`shared`します。  
  
## <a name="see-also"></a>関連項目  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)
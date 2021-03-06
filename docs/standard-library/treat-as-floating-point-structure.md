---
title: "treat_as_floating_point 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: chrono/std::chrono::treat_as_floating_point
dev_langs: C++
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8bfdda5bab6db19a1cf6d123f141f87249b62478
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="treatasfloatingpoint-structure"></a>treat_as_floating_point 構造体
`Rep` を浮動小数点型として扱うことができるかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Rep>  
struct treat_as_floating_point : is_floating_point<Rep>;  
```  
  
## <a name="remarks"></a>コメント  
 `Rep` は、特殊化 `treat_as_floating_point<Rep>` が [true_type](../standard-library/type-traits-typedefs.md#true_type) から派生したときにのみ浮動小数点型として処理できます。 このテンプレート クラスは、ユーザー定義型に特殊化することができます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<chrono >  
  
 **名前空間:** std::chrono  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)


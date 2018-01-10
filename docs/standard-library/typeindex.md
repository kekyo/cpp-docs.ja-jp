---
title: '&lt;typeindex&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <typeindex>
dev_langs: C++
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 42d1788ef0d9864d37e26f5a424b81fb0b57afab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="lttypeindexgt"></a>&lt;typeindex&gt;
[type_info](../cpp/type-info-class.md) クラスのオブジェクトのインデックス作成をサポートするクラスや関数を定義するには、標準ヘッダー \<typeindex> をインクルードします。  
  
## <a name="syntax"></a>構文  
  
```cpp  
#include <typeindex>  
```  
  
## <a name="remarks"></a>コメント  
 インデックス値の分布への [type_index](../standard-library/type-index-class.md) 型の値のマッピングに適した `hash function` は、[hash 構造体](../standard-library/hash-structure.md)で定義します。  
  
 `type_index` クラスは、インデックス作成をしやすくするために `type_info` オブジェクトへのポインターをラップするものです。  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



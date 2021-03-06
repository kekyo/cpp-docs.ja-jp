---
title: '&lt;hash_map&gt; | Microsoft Docs'
ms.custom: 
ms.date: 09/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <hash_map>
- std::<hash_map>
dev_langs: C++
helpviewer_keywords: hash_map header
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e69496f3383233c45ba994305342c3340459a287
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;
> [!NOTE]
>  このヘッダーは廃止され、互換性のために残されています。 代わりに、 [ \<unordered_map >](unordered-map.md)です。  
  
 コンテナーのテンプレート クラス hash_map と hash_multimap、およびそのサポート用テンプレートを定義します。  
 
  
## <a name="syntax"></a>構文  
  
```  
#include <hash_map>  
  
```  
  
### <a name="operators"></a>演算子  
  
|hash_map バージョン|hash_multimap バージョン|説明|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_map)](hash-map-operators.md#op_neq)|[operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|演算子の左側の hash_map または hash_multimap オブジェクトが右側の hash_map または hash_multimap オブジェクトと等しくないかどうかをテストします。|  
|[operator== (hash_map)](hash-map-operators.md#op_eq_eq)|[演算子 = = (hash_multimap)]((ハッシュ マップ-operators.md #op_eq_eq_mm)|演算子の左側の hash_map または hash_multimap オブジェクトが右側の hash_map または hash_multimap オブジェクトと等しいかどうかをテストします。|  
  
### <a name="specialized-template-functions"></a>特殊テンプレート関数  
  
|hash_map バージョン|hash_multimap バージョン|説明|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_map)](hash-map-class.md#swap)|[swap (hash_multimap)](hash-multimap-class.md#swap)|2 つの hash_map または hash_multimap の要素を交換します。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[hash_compare クラス](hash-compare-class.md)|任意のハッシュ連想コンテナー (hash_map、hash_multimap、hash_set、または hash_multiset) によって使用可能なオブジェクトを示しています。既定では **Traits** パラメーター オブジェクトを使用して、含まれる要素の順序付けおよびハッシュを行います。|  
|[value_compare クラス](value-compare-class.md)|要素のキーの値を比較し、要素の hash_map 内の相対順序を決定して、hash_map の要素を比較できる関数オブジェクトを提供します。|  
|[hash_map クラス](hash-map-class.md)|一意の並べ替えキーとそれに関連付けられている値のペアを要素として持つコレクションのデータを格納したり、迅速に取得したりするために使用されます。|  
|[hash_multimap クラス](hash-multimap-class.md)|必ずしも一意ではない並べ替えキーとそれに関連付けられている値のペアを要素として持つコレクションのデータを格納したり、迅速に取得したりするために使用されます。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<hash_map>  
  
 **名前空間:** stdext  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](cpp-standard-library-reference.md)




---
title: "&lt;hash_set&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
caps.latest.revision: "7"
manager: ghogen
ms.openlocfilehash: 4fcd6f0d72d31823a0d35108f087f2ad680e2f48
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="lthashsetgt-functions"></a>&lt;hash_set&gt; 関数
|||  
|-|-|  
|[swap](#swap)|[swap (hash_multiset)](#swap_hash_multiset)|  
  
##  <a name="swap"></a>  swap  
  
> [!NOTE]
>  この API は、互換性のために残されています。 代わりに、[unordered_set クラス](../standard-library/unordered-set-class.md)を使用してください。  
  
 2 つの hash_set の要素を交換します。  
  
```
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 交換する要素を提供する hash_set (hash_set `left` の要素と要素を交換する hash_set)。  
  
 `left`  
 要素が hash_set `right` の要素と交換される hash_set。  
  
### <a name="remarks"></a>コメント  
 `swap` テンプレート関数は、コンテナー クラス hash_set に特化したアルゴリズムであり、メンバー関数 `left.`[swap](../standard-library/hash-set-class.md#swap)(`right`) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン  
  
 **template \<class T> void swap(T&, T&),**  
  
 は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
   
  
### <a name="example"></a>例  
  `swap` のテンプレート バージョンの使用例については、メンバー クラス [hash_set::swap](../standard-library/hash-set-class.md#swap) のコード例をご覧ください。  
  
##  <a name="swap_hash_multiset"></a> swap (hash_multiset)  
  
> [!NOTE]
>  この API は、互換性のために残されています。 代わりに、[unordered_set クラス](../standard-library/unordered-set-class.md)を使用してください。  
  
 2 つの hash_multiset の要素を交換します。  
  
```
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 交換する要素を提供する hash_multiset (hash_multiset `left` の要素と要素を交換する hash_multiset)。  
  
 `left`  
 要素が hash_multiset `right` の要素と交換される hash_multiset。  
  
### <a name="remarks"></a>コメント  
 `swap` テンプレート関数は、コンテナー クラス hash_multiset に特化したアルゴリズムであり、メンバー関数 `left.`[swap](../standard-library/hash-multiset-class.md#swap)(`right`) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン  
  
 **template \<class T> void swap(T&, T&),**  
  
 は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
   
  
### <a name="example"></a>例  
  `swap` のテンプレート バージョンの使用例については、メンバー クラス [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap) のコード例をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [<hash_set>](../standard-library/hash-set.md)




---
title: "begin 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: collection/Windows::Foundation::Collections::begin
dev_langs: C++
helpviewer_keywords: begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 4bd4d94d2e65a4ad285a1a87c211169482cee1a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="begin-function"></a>begin 関数
指定されたインターフェイス パラメーターによってアクセスされるコレクションの先頭を指す反復子を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
template <typename T>   
    ::Platform::Collections::VectorIterator<T>   
    begin(  
          IVector<T>^ v         );  
  
template <typename T>   
    ::Platform::Collections::VectorViewIterator<T>   
    begin(  
          IVectorView<T>^ v  
         );   
  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    begin(  
          IIterable<T>^ i         );  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 テンプレート型パラメーター。  
  
 `v`  
 ベクターのコレクション\<T > または VectorView\<T >、IVector によってアクセスされるオブジェクト\<T > または IVectorView\<T > インターフェイスです。  
  
 `i`  
 IIterable によってアクセスされる任意の Windows ランタイム オブジェクトのコレクション\<T > インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 コレクションの先頭を指す反復子。  
  
### <a name="remarks"></a>コメント  
 最初の 2 つのテンプレート関数は反復子を返し、3 番目のテンプレート関数は入力反復子を返します。  
  
 によって返されるオブジェクトの開始 VectorIterator は、型 VectorProxy の要素を格納するプロキシ反復子\<T > です。 ただし、プロキシ オブジェクトは、ユーザー コードにはほとんどは表示されません。 詳細については、「 [Collections (C++/CX) (コレクション (C++/CX))](../cppcx/collections-c-cx.md)」を参照してください。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Windows::Foundation::Collections  
  
## <a name="see-also"></a>関連項目  
 [:Foundation Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)
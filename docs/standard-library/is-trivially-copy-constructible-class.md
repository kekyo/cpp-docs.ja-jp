---
title: "is_trivially_copy_constructible クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_trivially_copy_constructible
dev_langs: C++
helpviewer_keywords: is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 465d5a1756a416eac2c01c5191b4f63f986ffcba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible クラス
型に自明なコピー コンストラクターが含まれるかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>
struct is_trivially_copy_constructible;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 型 `T` が自明なコピー コンストラクターを持つクラスである場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
 クラス `T` のコピー コンストラクターが自明となるのは、このコピー コンストラクターが暗黙的に宣言されており、クラス `T` に仮想関数も仮想基底も含まれず、クラス `T` のすべての直接基底が自明なコピー コンストラクターを持ち、クラス型の非静的データ メンバーすべてのクラスが自明なコピー コンストラクターを持ち、かつクラスの型配列の非静的データ メンバーすべてでクラスが自明なコピー コンストラクターを持つ場合です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




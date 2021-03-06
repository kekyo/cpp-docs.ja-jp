---
title: "_com_ptr_t::Detach |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: f61b0fb05f182ef2723fdcc564fd697f490aed20
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach
**Microsoft 固有の仕様**  
  
 カプセル化されたインターフェイス ポインターを抽出して返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
Interface* Detach( ) throw( );  
  
```  
  
## <a name="remarks"></a>コメント  
 抽出、カプセル化されたインターフェイス ポインターを返し、カプセル化されたポインター ストレージをクリア**NULL**です。 これによって、カプセル化からインターフェイス ポインターが削除されます。 呼び出すかどうかは**リリース**返されたインターフェイス ポインター。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)

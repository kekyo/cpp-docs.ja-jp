---
title: '&lt;new&gt; typedefs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
caps.latest.revision: 7
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: e23ea06002dc840997a0e7202f581cd81ef407c5
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; typedefs
||  
|-|  
|[new_handler](#new_handler)|  
  
##  <a name="new_handler"></a>  new_handler  
 新しいハンドラーとして使用するのに適した関数を指す型。  
  
```
typedef void (*new_handler)();
```  
  
### <a name="remarks"></a>コメント  
 このハンドラー関数の型は、追加の記憶域の要求を満たすことができない場合に、**operatornew** または `operator new[]` によって呼び出されます。  
  
### <a name="example"></a>例  
  `new_handler` を戻り値として使用する例については、「[set_new_handler](../standard-library/new-functions.md#set_new_handler)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [\<new>](../standard-library/new.md)





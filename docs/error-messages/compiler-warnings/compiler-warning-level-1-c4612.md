---
title: "コンパイラの警告 (レベル 1) C4612 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4612
dev_langs:
- C++
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: ede7b643c5be50f430859f2716e542560d6b04c5
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4612"></a>コンパイラの警告 (レベル 1) C4612
インクルード ファイル名にエラーがあります  
  
 この警告は、ファイル名が正しくないか、不足している場合に、 **#pragma include_alias** で発生します。  
  
 引数を**#pragma include_alias**ステートメントから引用符を使用できます (**"***filename***"**) または山かっこ形式 (**\<***filename***>**)、両方とも同じ形式を使用する必要がありますが、します。  
  
## <a name="example"></a>例  
  
```  
// C4612.cpp  
// compile with: /W1 /LD  
#pragma include_alias("StandardIO", <stdio.h>) // C4612  
```

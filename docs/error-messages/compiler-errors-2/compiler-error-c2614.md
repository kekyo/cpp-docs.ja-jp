---
title: "コンパイラ エラー C2614 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2614
dev_langs:
- C++
helpviewer_keywords:
- C2614
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 077762fef5474b3761c504224c58de83d82bdb12
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2614"></a>コンパイラ エラー C2614
'class1': 無効なメンバーの初期化: 'class2' が基底クラスまたはメンバーがありません  
  
 メンバーまたは基底クラスのみが、クラスまたは構造体の初期化リストに表示できます。  
  
## <a name="example"></a>例  
 次の例では、C2614 を生成します。  
  
```  
// C2614.cpp  
// compile with: /c  
struct A {  
   int i;  
   A( int ia ) : B( i ) {};   // C2614 B is not a member of A  
};  
  
struct A2 {  
   int B;  
   int i;  
   A2( int ia ) : B( i ) {};   // OK  
};  
```

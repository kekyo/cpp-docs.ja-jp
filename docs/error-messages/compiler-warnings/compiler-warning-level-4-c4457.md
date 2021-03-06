---
title: "コンパイラの警告 (レベル 4) C4457 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4457
dev_langs: C++
helpviewer_keywords: C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a8ede4500e579436d5d6b9db581a06c14a6aca43
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4457"></a>コンパイラの警告 (レベル 4) C4457
  
> 宣言 '*識別子*' 関数のパラメーターを非表示にします
  
宣言*識別子*ローカル スコープでは、同じ名前の関数のパラメーターの宣言を非表示にします。 この警告を参照するを認識できます。*識別子*ローカル スコープで解決するにはローカルに宣言されたバージョンを、パラメーターではありません、またはユーザーの意図ができない可能性があります。 この問題を修正するのには、パラメーター名と競合しないローカル変数名を付けるお勧めします。  
    
## <a name="example"></a>例
  
次の例では、ため C4457 が生成されますパラメーター`x`し、ローカル変数`x`で`member_fn`名前が同じです。 この問題を解決するには、パラメーターおよびローカル変数の別の名前を使用します。  
  
```cpp  
// C4457_hide.cpp
// compile with: cl /W4 /c C4457_hide.cpp

struct S {
    void member_fn(unsigned x) {
        double a = 0;
        for (int x = 0; x < 10; ++x) {  // C4457
            a += x; // uses local x
        } 
        a += x; // uses parameter x
    }
} s;
```  

---
title: "コンパイラ エラー C2712 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2712
dev_langs:
- C++
helpviewer_keywords:
- C2712
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: af8f975960f34307c0e297f58f613eaf92018ef2
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2712"></a>コンパイラ エラー C2712
オブジェクト アンワインディングが必要な関数内で __try を使用できません。  
  
 使用する場合、エラー C2712 が発生する可能性が[/EHsc](../../build/reference/eh-exception-handling-model.md)、構造化例外処理もと関数にアンワインディング (破棄) を必要とするオブジェクトとします。  
  
 考えられる解決策:  
  
-   SEH を必要とするコードを別の関数に移動します。  
  
-   デストラクターを含むローカル変数とパラメーターを使用しないように、SEH を使用する関数を記述し直します。 コンストラクターまたはデストラクターで SEH を使用しないようにします。  
  
-   /EHsc を使用せずにコンパイルします。  
  
 使用して宣言されたメソッドを呼び出す場合もエラー C2712 が発生、 [_ _event](../../cpp/event.md)キーワード。 コンパイラが、基になるイベント オブジェクトの操作を防止し、SEH で生成されたコードを囲むコードを生成するイベントは、マルチ スレッド環境で使用される可能性があります、ため[try-finally ステートメント](../../cpp/try-finally-statement.md)です。 その結果、イベント メソッドを呼び出し、型にデストラクターが含まれる引数を値渡しで渡すと、エラー C2712 が発生します。 このような場合の解決策の 1 つとして、引数を定数参照として渡します。  
  
## <a name="example"></a>例  
 コンパイルする場合も C2712 が発生**/clr: 純粋な**内から関数へのポインターの静的配列を宣言し、`__try`ブロックします。 静的メンバーには、動的な初期化を使用するコンパイラが必要です。 **/clr: 純粋な**、C++ 例外処理が含まれています。 しかし、`__try` ブロックでは C++ の例外処理を実行できません。  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
 次の例では、C2712 を生成し、その修正方法を示しています。  
  
```  
// C2712.cpp  
// compile with: /clr:pure /c  
struct S1 {  
   static int smf();  
   void fnc();  
};  
  
void S1::fnc() {  
   __try {  
      static int (*array_1[])() = {smf,};   // C2712  
  
      // OK  
      static int (*array_2[2])();  
      array_2[0] = smf;  
    }  
    __except(0) {}  
}  
```

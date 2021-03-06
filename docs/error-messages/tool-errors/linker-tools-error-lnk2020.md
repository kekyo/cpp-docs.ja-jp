---
title: "リンカ ツール エラー LNK2020 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2020
dev_langs: C++
helpviewer_keywords: LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d9a4bedb06ccad45a105c0e47fbc1f839891bea7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2020"></a>リンカ ツール エラー LNK2020
未解決のトークン 'token'  
  
 未定義の外部エラーに似ていますが、参照がメタデータからです。 メタデータですべての関数とデータを定義する必要があります。  
  
 解決するのには  
  
-   不足している関数またはデータ定義または  
  
-   オブジェクト ファイルまたは不足している関数またはデータが既に定義されているライブラリが含まれます。  
  
## <a name="example"></a>例  
 次の例では、LNK2020 が生成されます。  
  
```  
// LNK2020.cpp  
// compile with: /clr /LD  
ref struct A {  
   A(int x);   // LNK2020  
   static int f();   // LNK2020  
};  
  
// OK  
ref struct B {  
   B(int x) {}  
   static int f() { return 0; }  
};  
```  
  
## <a name="example"></a>例  
 LNK2020 は、管理されているテンプレートの種類の変数を作成することが、型をインスタンス化しない場合にも発生します。  
  
 次の例では、LNK2020 が生成されます。  
  
```  
// LNK2020_b.cpp  
// compile with: /clr   
  
template <typename T>  
ref struct Base {  
   virtual void f1() {};  
};  
  
template <typename T>  
ref struct Base2 {  
   virtual void f1() {};  
};  
  
int main() {  
   Base<int>^ p;   // LNK2020  
   Base2<int>^ p2 = gcnew Base2<int>();   // OK  
};  
```
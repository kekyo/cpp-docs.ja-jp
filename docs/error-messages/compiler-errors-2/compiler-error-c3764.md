---
title: "コンパイラ エラー C3764 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3764
dev_langs: C++
helpviewer_keywords: C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 60317bb31b5021d4b9b1b6568d77ae92e06880ce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3764"></a>コンパイラ エラー C3764
'override_function': 基底クラス メソッド 'base_class_function' をオーバーライドすることはできません  
  
 正しくない形式の上書きが検出されました。 たとえば、基底クラス関数が`virtual`です。 詳細については、次を参照してください。[オーバーライド](../../windows/override-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3764 を生成します。  
  
```  
// C3764.cpp  
// compile with: /clr /c  
public ref struct A {  
   void g(int);  
   virtual void h(int);  
};  
  
public ref struct B : A {  
   virtual void g(int) override {}   // C3764  
   virtual void h(int) override {}   // OK  
};  
```  
  
## <a name="example"></a>例  
 C3764 は基底クラスのメソッドは、両方を明示的にはときも発生し、名前付きオーバーライドします。 次の例では、C3764 を生成します。  
  
```  
// C3764_b.cpp  
// compile with: /clr /c  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : public A {  
   virtual void Test() override {}  
   virtual void Test2() = A::Test {}   // C3764  
};  
```
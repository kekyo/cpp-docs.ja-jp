---
title: "コンパイラ エラー C3894 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3894
dev_langs: C++
helpviewer_keywords: C3894
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 46dffabb57e871e1635738434e7efb4812850379
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3894"></a>コンパイラ エラー C3894
'var': initonly スタティック データ メンバーの左辺値の使用はクラス 'class' のクラス コンス トラクターでのみ許可  
  
 静的[initonly](../../dotnet/initonly-cpp-cli.md)データ メンバーは、または静的コンス トラクターの宣言の位置で左辺値としてのみ使用できます。  
  
 インスタンス (静的ではない) initonly データ メンバーは、宣言、またはインスタンス (静的ではない) コンス トラクターでは、その時点で左辺値としてのみ使用できます。  
  
 次の例では、C3894 が生成されます。  
  
```  
// C3894.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly static int data_var = 0;  
  
public:  
   // class constructor  
   static Y1() {  
      data_var = 99;   // OK  
      System::Console::WriteLine("in static constructor");  
   }  
  
   // not the class constructor  
   Y1(int i) {  
      data_var = i;   // C3894  
   }  
  
   static void Test() {}  
  
};  
  
int main() {  
   Y1::data_var = 88;   // C3894  
   int i = Y1::data_var;  
   Y1 ^ MyY1 = gcnew Y1(99);  
   Y1::Test();  
}  
```
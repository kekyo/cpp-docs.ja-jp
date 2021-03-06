---
title: "コンパイラ エラー C3673 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3673
dev_langs: C++
helpviewer_keywords: C3673
ms.assetid: bb6d2079-05af-4e2c-be0e-75c892e6c590
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4958f3652119e105ed327d5476c084ad6707fb9a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3673"></a>コンパイラ エラー C3673
'type': クラスには、コピー コンス トラクターがありません。  
  
 CLR 参照型のオブジェクトをコピーするには、ユーザー定義のコンス トラクターが必要です。 詳細については、次を参照してください。[参照型の C++ スタック セマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3673 を生成します。  
  
```  
// C3673.cpp  
// compile with: /clr  
public ref struct R {  
public:  
   R() {}  
   // Uncomment the following line to resolve.  
   // R(R% p) {}  
};  
  
int main() {  
   R r;  
   R s = r;   // C3673  
}  
```  
  
## <a name="example"></a>例  
 次の例では、C3673 を生成します。  
  
```  
// C3673_b.cpp  
// compile with: /clr /c  
// C3673 expected  
using namespace System;  
[AttributeUsage(AttributeTargets::Class)]  
ref class MyAttr : public Attribute {  
public:  
   MyAttr() {}  
   // Uncomment the following line to resolve.  
   // MyAttr(int i) {}  
   property int Priority;  
   property int Version;  
};  
  
[MyAttr]   
ref class ClassA {};   // OK, no arguments  
  
[MyAttr(Priority = 1)]   
ref class ClassB {};   // OK, named argument  
  
[MyAttr(123)]  
ref class ClassC {};   // Positional argument  
  
[MyAttr(123, Version = 1)]  
ref class ClassD {};   // Positional and named  
```
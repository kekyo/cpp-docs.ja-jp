---
title: "コンパイラ エラー C2071 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2071
dev_langs:
- C++
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c62bb735a84b04bfb0c1addd5e3dd20a48a3eb33
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2071"></a>コンパイラ エラー C2071
'識別子' : ストレージ クラスが正しくありません。  
  
 `identifier`無効な状態で宣言されました[ストレージ クラス](../../c-language/c-storage-classes.md)です。 1 つの識別子に複数のストレージ クラスが指定されている場合や、定義がストレージ クラスの宣言と互換性がない場合に、このエラーが発生することがあります。  
  
 この問題を解決するには、識別子の目的の記憶域クラスを理解する。-たとえば、`static`または`extern`— と一致するように宣言を修正して。  
  
## <a name="example"></a>例  
 次の例では C2071 エラーが生成されます。  
  
```  
// C2071.cpp  
// compile with: /c  
struct C {  
   extern int i;   // C2071  
};  
struct D {  
   int i;   // OK, no extern on an automatic  
};  
```  
  
## <a name="example"></a>例  
 次の例では C2071 エラーが生成されます。  
  
```  
// C2071_b.cpp  
// compile with: /c  
typedef int x(int i) { return i; }   // C2071  
typedef int (x)(int);   // OK, no local definition in typedef  
```

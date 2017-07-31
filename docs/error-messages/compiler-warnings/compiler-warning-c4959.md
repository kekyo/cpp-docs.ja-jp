---
title: "コンパイラの警告 C4959 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4959
dev_langs:
- C++
helpviewer_keywords:
- C4959
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
caps.latest.revision: 11
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
ms.openlocfilehash: f7cde1151bd220415b950dcce089265be118de34
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4959"></a>コンパイラの警告 C4959
アンマネージ構造体 'type' は、そのメンバーへのアクセスによって検証不可能なコードが生成されるため、/clr:safe で定義できません  
  
 アンマネージ型のメンバーにアクセスすると、検証不可能な (peverify.exe) イメージが生成されます。  
  
 詳細については、次を参照してください。[純粋なコードと検証可能なコード (C + + CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)です。  
  
 この警告がエラーとして発行され、無効にする、[警告](../../preprocessor/warning.md)プラグマ、または[/wd](../../build/reference/compiler-option-warning-level.md)コンパイラ オプション。  
  
 次の例では C4959 が生成されます。  
  
```  
// C4959.cpp  
// compile with: /clr:safe  
  
// Uncomment the following line to resolve.  
// #pragma warning( disable : 4959 )  
struct X {  
   int data;  
};  
  
int main() {  
   X x;  
   x.data = 10;   // C4959  
}  
```
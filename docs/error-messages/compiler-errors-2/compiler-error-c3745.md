---
title: "コンパイラ エラー C3745 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3745
dev_langs: C++
helpviewer_keywords: C3745
ms.assetid: 1e64aec5-7e53-47e5-bc7d-3905230cfc66
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 330e9c62e2235e1f352b64d1f236423d6786cc1d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3745"></a>コンパイラ エラー C3745
'function': イベントだけが生成されることが' '  
  
 定義された関数のみ、 [_ _event](../../cpp/event.md)にキーワードを渡すことができます、 [_ _raise](../../cpp/raise.md)キーワード。  
  
 次の例では、C3745 が生成されます。  
  
```  
// C3745.cpp  
struct E {  
   __event void func();  
   void func(int) {  
   }  
  
   void func2() {  
   }  
  
   void bar() {  
      __raise func();  
      __raise func(1);   // C3745  
      __raise func2();   // C3745  
   }  
};  
  
int main() {  
   E e;  
   __raise e.func();  
   __raise e.func(1);   // C3745  
   __raise e.func2();   // C3745  
}  
```
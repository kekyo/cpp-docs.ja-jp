---
title: "コンパイラ エラー C3351 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3351
dev_langs:
- C++
helpviewer_keywords:
- C3351
ms.assetid: c021bbbe-1067-4f51-af4f-940d2b792eb5
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c6a449d904e0b5122ec1a8d2ae9734a6dd3f8b00
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3351"></a>コンパイラ エラー C3351
'object': デリゲート コンストラクター: 2 番目の引数は、静的メンバー関数またはグローバル関数のアドレスでなければなりません  
  
 コンパイラには、 `static`として宣言された関数のアドレスが必要です。  
  
 次の例では C3351 が生成されます。  
  
```  
// C3351a.cpp  
// compile with: /clr  
delegate int D(int, int);  
  
ref class C {  
public:  
   int mf(int, int) {  
      return 1;  
   }  
  
   static int mf2(int, int) {  
      return 1;  
   }  
};  
  
int main() {  
   System::Delegate ^pD = gcnew D(nullptr, &C::mf);   // C3351  
   System::Delegate ^pD2 = gcnew D(&C::mf2);  
}  
```  


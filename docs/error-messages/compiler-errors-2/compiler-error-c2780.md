---
title: "コンパイラ エラー C2780 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2780
dev_langs:
- C++
helpviewer_keywords:
- C2780
ms.assetid: 423793d8-a3b2-4f35-85f8-ae1d043e2b69
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 96ca469a10c96ad16027ec696af0b43e8ac4e2c5
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2780"></a>コンパイラ エラー C2780
'declaration': 引数 N が必要です - M が設定されます  
  
 関数テンプレートの引数が多すぎるか少なすぎます。  
  
 次の例は C2780 を生成し、その修正方法を示しています。  
  
```  
// C2780.cpp  
template<typename T>  
void f(T, T){}  
  
int main() {  
   f(1);  // C2780  
   // try the following line instead  
   // f(1,2);  
}  
```

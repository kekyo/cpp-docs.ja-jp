---
title: "コンパイラ エラー C2192 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2192
dev_langs:
- C++
helpviewer_keywords:
- C2192
ms.assetid: a147197e-e72d-4620-939b-f9e08d7c7c12
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c56dae7438c8c8dd7d17332f65b5c32aff16db39
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2192"></a>コンパイラ エラー C2192
パラメーター 'number' の宣言が異なる  
  
 C の関数は、異なるパラメーター リストで 2 番目の時間を宣言されました。 C では、オーバー ロードされた関数はサポートされません。  
  
 次の例では、C2192 が生成されます。  
  
```  
// C2192.c  
// compile with: /Za /c  
void func( float, int );  
void func( int, float );   // C2192, different parameter list  
void func2( int, float );   // OK  
```

---
title: "コンパイラの警告 (レベル 1) C4333 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4333
dev_langs: C++
helpviewer_keywords: C4333
ms.assetid: d3763c52-6110-4da0-84db-5264e3f3f166
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 505181ea2008680c20a4e63a4d2a1a0e89d91f01
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4333"></a>コンパイラの警告 (レベル 1) C4333
'operator': 右シフトのデータが失われる回数が多すぎます  
  
 右シフト演算が、大きすぎます。  すべての上位ビットをシフトされ、結果は常に 0 です。  
  
## <a name="example"></a>例  
 次の例では、C4333 を生成します。  
  
```  
// C4333.cpp  
// compile with: /c /W1  
unsigned shift8 (unsigned char c) {  
   return c >> 8;   // C4333  
  
   // try the following line instead  
   // return c >> 4;   // OK  
}  
```
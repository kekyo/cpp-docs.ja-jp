---
title: "コンパイラの警告 (レベル 1) C4172 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4172
dev_langs: C++
helpviewer_keywords: C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8e8abc6d26898dda197580e83a34f20acd4b01d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4172"></a>コンパイラの警告 (レベル 1) C4172
ローカル変数またはテンポラリのアドレスを返します。  
  
 関数は、ローカル変数または一時オブジェクトのアドレスを返します。 ローカル変数と一時オブジェクトが破棄されます関数が戻るときに返されるアドレスが有効でないためです。  
  
 関数は、ローカル オブジェクトのアドレスを返さないように再設計します。  
  
 次の例では、C4172 が生成されます。  
  
```  
// C4172.cpp  
// compile with: /W1 /LD  
float f = 10;  
  
const double& bar() {  
// try the following line instead  
// const float& bar() {  
   return f;   // C4172  
}  
```
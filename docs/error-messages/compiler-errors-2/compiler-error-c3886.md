---
title: "コンパイラ エラー C3886 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3886
dev_langs: C++
helpviewer_keywords: C3886
ms.assetid: 485f6c12-cc1b-4146-9034-409a0a5e615e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 095b0f64bc2d792f6cde5c64d32cb8110d04bdbe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3886"></a>コンパイラ エラー C3886
'var': リテラル データ メンバーを初期化する必要があります  
  
 A[リテラル](../../windows/literal-cpp-component-extensions.md)declaraed であるときに、変数を初期化する必要があります。  
  
 次の例では、C3886 が生成されます。  
  
```  
// C3886.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal int staticConst;   // C3886  
   literal int staticConst2 = 0;   // OK  
};  
```
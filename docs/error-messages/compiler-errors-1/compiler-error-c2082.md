---
title: "コンパイラ エラー C2082 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2082
dev_langs:
- C++
helpviewer_keywords:
- C2082
ms.assetid: 87a6d442-157c-46e8-9bff-8388f8338ae0
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fc76b22d70f23639758706f6fdcb13a0adbfbb69
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2082"></a>コンパイラ エラー C2082
仮パラメーター 'identifier' が再定義されました  
  
 関数の仮パラメーターが、関数本体の中で再宣言されています。 エラーを解決するには、再定義を削除します。  
  
 次の例では C2082 が生成されます。  
  
```  
// C2082.cpp  
void func(int i) {  
   int i;   // C2082  
   int ii;   // OK  
}  
```

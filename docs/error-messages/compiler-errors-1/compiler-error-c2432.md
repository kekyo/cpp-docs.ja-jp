---
title: "コンパイラ エラー C2432 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2432
dev_langs:
- C++
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d89d894738978359fa0cedb9a9da6c4f9781c135
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2432"></a>コンパイラ エラー C2432
'identifier' での 16 ビット データへの参照が正しくありません。  
  
 16 ビット レジスタは、インデックスまたはベース レジスタとして使用されます。 コンパイラは、16 ビットのデータの参照をサポートしていません。 16 ビット レジスタは、32 ビット コードのコンパイルするときに、インデックスまたはベース レジスタとして使用できません。  
  
 次の例では、C2432 が生成されます。  
  
```  
// C2432.cpp  
// processor: x86  
int main() {  
   _asm mov eax, DWORD PTR [bx]   // C2432  
}  
```

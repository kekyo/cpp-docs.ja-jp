---
title: "コンパイラ エラー C2036 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2036
dev_langs:
- C++
helpviewer_keywords:
- C2036
ms.assetid: 895821a9-65d1-44b5-bde1-dae827f3e486
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8ffb8f2b8ad0df1741687c1081fc499d3a9fde31
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2036"></a>コンパイラ エラー C2036
'identifier': 不明なサイズ  
  
 操作`identifier`を特定することはできません、データ オブジェクトのサイズが必要です。  
  
## <a name="example"></a>例  
 次の例では、C2036 を生成します。  
  
```  
// C2036.c  
// a C program  
struct A* pA;  
struct B { int i; } *pB;  
int main() {  
   pA++;   // C2036, size of A not known  
   ((char*)pA)++;   // OK  
  
   pB++;   // OK  
}  
```  
  
## <a name="example"></a>例  
 次の例では、C2036 を生成します。  
  
```  
// C2036_2.cpp  
// a C++ program  
struct A* pA;  
int main() {  
   pA++;   // C2036, size of A not known  
   ((char*&)pA)++;   // OK, if sizeof(A) == sizeof(char)  
}  
```

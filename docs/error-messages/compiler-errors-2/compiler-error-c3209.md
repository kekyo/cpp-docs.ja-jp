---
title: "コンパイラ エラー C3209 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3209
dev_langs:
- C++
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 99cffcf55850035bc114c5b158ad3fde304234f0
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3209"></a>コンパイラ エラー C3209
'class': ジェネリック クラスは、マネージまたは WinRTclass に指定する必要があります  
  
 ジェネリック クラスは、マネージ クラスまたは Windows ランタイム クラスである必要があります。  
  
 次の例では、C3209 を生成し、その修正方法を示しています。  
  
```  
// C3209.cpp  
// compile with: /clr  
generic <class T>  
class C {};   // C3209  
  
// OK - ref class can be generic  
generic <class T>  
ref class D {};  
```

---
title: "コンパイラ エラー C2500 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2500
dev_langs:
- C++
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2b869ca0ba959e9b774a005298ef4456d0995156
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2500"></a>コンパイラ エラー C2500
'identifier1': 'identifier2' である直接基底クラス  
  
 クラスまたは構造体の基底クラスの一覧に 2 回以上表示されます。  
  
 直接の基本クラスは基底のリストに記載されています。 間接基本は、基底のリスト内のクラスのいずれかの基本クラスです。  
  
 クラスは、直接基底クラスとして複数回指定できません。 クラスは、間接基底クラスとして複数回使用できます。  
  
 次の例では、C2500 が生成されます。  
  
```  
// C2500.cpp  
// compile with: /c  
class A {};  
class B : public A, public A {};    // C2500  
  
// OK  
class C : public A {};  
class D : public A {};  
class E : public C, public D {};  
```

---
title: "コンパイラ エラー C3765 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3765
dev_langs: C++
helpviewer_keywords: C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 44311ab210a85b05d86eb48aebe8294c95bfb5ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3765"></a>コンパイラ エラー C3765
'event': event_receiver とマークされている 'type' クラス/構造体にイベントを定義することはできません  
  
 クラスが付いている場合、 [event_receiver](../../windows/event-receiver.md)属性、クラスを含めることはできません、 [_ _event](../../cpp/event.md)宣言します。  
  
 次の例では、C3765 が生成されます。  
  
```  
// C3765.cpp  
[event_receiver(native)]  
struct ER2 {  
   __event void f();   // C3765  
   __event void b(int);   // C3765  
};  
```
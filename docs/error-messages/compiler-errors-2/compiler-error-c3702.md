---
title: "コンパイラ エラー C3702 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3702
dev_langs:
- C++
helpviewer_keywords:
- C3702
ms.assetid: 14fcc20e-4404-45d7-be54-e4f09332fa5a
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a6d41ff2f20caa61126c122b50957037718968d3
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3702"></a>コンパイラ エラー C3702
'function': ATL が COM イベント用に必要です  
  
 必要な ATL ヘッダー ファイルを含めずに COM イベントを使用しようとするとします。  
  
 次の例では、C3702 が生成されます。  
  
```  
// C3702.cpp  
// uncomment the following line to resolve  
// #define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(dll, name=idid, uuid="12341234-1234-1234-1234-123412341234")];  
  
[object]  
__interface IEvents : IUnknown  
{  
   HRESULT event1([in] int i);  
};  
  
[dual]  
__interface IBase  
{  
   HRESULT fireEvents();  
};  
  
[coclass, event_source(com)]  
class CEventSrc : public IBase  
{  
   public:  
   __event __interface IEvents;  
  
   HRESULT fireEvents()  
   {  
      HRESULT hr = IEvents_event1(123);  
      return hr;  
   }  
};   // C3702  
  
int main() {  
}  
```

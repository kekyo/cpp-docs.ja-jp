---
title: "コンパイラ エラー C3628 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3628
dev_langs: C++
helpviewer_keywords: C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 131b2829991d0d8c40b64c903afd45b485b9ba55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3628"></a>コンパイラ エラー C3628
'base class': マネージ配列または WinRTclasses はパブリック継承のみをサポート  
  
マネージまたは WinRT の使用を試みましたクラスの[プライベート](../../cpp/private-cpp.md)または[保護](../../cpp/protected-cpp.md)基本クラスです。 マネージ配列または WinRT クラスを持つ基本クラスとしてのみ使用できます[パブリック](../../cpp/public-cpp.md)アクセスします。  
  
次の例は C3628 を生成し、その修正方法を示しています。  
  
```  
// C3628a.cpp  
// compile with: /clr  
ref class B {  
};  
  
ref class D : private B {   // C3628  
  
// The following line resolves the error.  
// ref class D : public B {  
};  
  
int main() {  
}  
```  

---
title: "コンパイラ エラー C3296 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3296
dev_langs: C++
helpviewer_keywords: C3296
ms.assetid: fc4c9dcd-16cf-4eee-a1ac-c43e7c29e443
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 734f4e1e337833e26c60d4239a465818d8601ae5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3296"></a>コンパイラ エラー C3296
'property': この名前のプロパティが既に存在します  
  
 コンパイラは同じ名前の 1 つ以上のプロパティを見つけました。 1 つの型の各プロパティには、一意の名前が必要です。  
  
 詳細については、「 [property](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では C3296 が生成されます。  
  
```  
// C3296.cpp  
// compile with: /clr /c  
using namespace System;  
  
ref class R {  
public:  
   property int MyProp[int] { int get(int); }  
  
   property String^ MyProp[int] { void set(int, String^); }   // C3296  
};  
```
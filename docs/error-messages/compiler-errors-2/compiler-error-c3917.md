---
title: "コンパイラ エラー C3917 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3917
dev_langs: C++
helpviewer_keywords: C3917
ms.assetid: a24cd0c9-262f-46e5-9488-1c01f945933d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 87ff4bde3b37e630f4d6a4a64f12039cf98ff2be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3917"></a>コンパイラ エラー C3917
'*プロパティ*': コンス トラクターの宣言スタイルの廃止  
  
プロパティまたはイベント定義では、Visual Studio 2005 より前に、のバージョンの構文を使用します。  
  
詳細については、「 [property](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```cpp  
// C3917.cpp  
// compile with: /clr /c  
public ref class  C {  
private:  
   int m_length;  
public:  
   C() {  
      m_length = 0;  
   }  
  
   property int get_Length();   // C3917  
  
   // The correct property definition:  
   property int Length {  
      int get() {  
         return m_length;  
      }  
  
      void set( int i ) {  
         m_length = i;  
      }  
   }  
};  
```
---
title: "コンパイラの警告 (レベル 1) C4835 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4835
dev_langs: C++
helpviewer_keywords: C4835
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c1b01a84313d2d04e927420d1462dd8d5c2c495b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4835"></a>コンパイラの警告 (レベル 1) C4835
'variable': マネージ コードがホスト アセンブリで最初に実行されるまで、エクスポートされたデータの初期化子は実行されません  
  
 マネージ コンポーネントの間でデータにアクセスするときにないネイティブの C++ のインポートを使用してをエクスポート機構をお勧めします。 代わりに、マネージ型の内部データ メンバーを宣言してメタデータを参照`#using`クライアントにします。 詳細については、次を参照してください。 [#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)です。  
  
## <a name="example"></a>例  
 次の例では、C4835 を生成します。  
  
```  
// C4835.cpp  
// compile with: /W1 /clr /LD  
int f() { return 1; }  
int n = 9;  
  
__declspec(dllexport) int m = f();   // C4835  
__declspec(dllexport) int *p = &n;   // C4835  
```  
  
## <a name="example"></a>例  
 次の例では、変数の値が期待どおりにないことを示す、前の例でビルドされたコンポーネントを使用します。  
  
```  
// C4835_b.cpp  
// compile with: /clr C4835.lib  
#include <stdio.h>  
__declspec(dllimport) int m;  
__declspec(dllimport) int *p;  
  
int main() {  
   printf("%d\n", m);  
   printf("%d\n", p);  
}  
```  
  
```Output  
0  
268456008  
```
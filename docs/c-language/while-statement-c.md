---
title: "while ステートメント (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: while
dev_langs: C++
helpviewer_keywords:
- while keyword [C]
- while keyword [C], syntax
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5f8157d4006d3f2a53e2f32a87d8923baf73628f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="while-statement-c"></a>while ステートメント (C)
`while` ステートメントを使用して、指定した式が false になるまでステートメントを繰り返すことができます。  
  
## <a name="syntax"></a>構文  
 *iteration-statement*:  
 **while (**  *expression*  **)**  *statement*  
  
 *expression* は演算型またはポインター型であることが必要です。 次のように実行されます。  
  
1.  *expression* が評価されます。  
  
2.  最初の時点で *expression* が false の場合、`while` ステートメントの本体は実行されず、`while` ステートメントからプログラムの次のステートメントへ制御が渡されます。  
  
     *expression* が true (0 以外) の場合はステートメントの本体が実行され、手順 1 からプロセスが繰り返されます。  
  
 `while` ステートメントは、ステートメント本体内の **break**、`goto`、または `return` が実行されたときにも終了できます。 `while` ループが終了する前に反復を終了するには、**continue** ステートメントを使用します。 **continue** ステートメントは `while` ステートメントの次のイテレーションに制御を渡します。  
  
 `while` ステートメントの例を次に示します。  
  
```  
while ( i >= 0 )   
{  
    string1[i] = string2[i];  
    i--;  
}  
```  
  
 このコード例では、`string2` の文字を `string1` にコピーします。 `i` が 0 以上の場合、`string2[i]` が `string1[i]` に割り当てられ、`i` がデクリメントされます。 `i` が 0 に達するか、0 より小さくなると、`while` ステートメントの実行が終了します。  
  
## <a name="see-also"></a>関連項目  
 [while ステートメント (C++)](../cpp/while-statement-cpp.md)
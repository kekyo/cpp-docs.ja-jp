---
title: "コンパイラ エラー C3286 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3286
dev_langs:
- C++
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 551d5136cec63b968ce7b9711b06d8c7b509d9c8
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3286"></a>コンパイラ エラー C3286
'specifier': 繰り返し変数は、ストレージ クラスの指定子を含むことはできません  
  
 参照してください[(NOTINBUILD) ストレージ クラス指定子](http://msdn.microsoft.com/en-us/10b3d22d-cb40-450b-994b-08cf9a211b6c)詳細についてはします。  
  
 参照してください[ごとで](../../dotnet/for-each-in.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では C3286 が生成されます。  
  
```  
// C3286.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p = { 1, 2, 3 };  
   for each (static int i in p) {}   // C3286   
   for each (int j in p) {}   // OK  
}  
```

---
title: "2.7.2.5 既定の |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c856df07-705c-4ad3-9105-a268dd33e939
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 26dff1f0e8b3b88b4891617a2eef2bb2d82240eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="2725-default"></a>2.7.2.5 default
**既定**句は、ユーザーに影響を与える変数のデータ共有属性を使用できます。 構文、**既定**句を次に示します。  
  
```  
default(shared | none)  
```  
  
 指定する**default(shared)**は明示的にリスト内の現在表示されている各変数に相当、**共有**句である場合を除き**threadprivate**または**cons**`t`で修飾します。 ない場合、明示的な**既定**句、既定の動作は同じ場合**default(shared)**指定されました。  
  
 指定する**default (none)** parallel コンストラクトの構文の範囲内の変数への参照をすべて true に設定する必要がありますには、少なくとも次のいずれかのことが必要です。  
  
-   変数は、参照を含む構造のデータ共有属性句で明示的に表示されます。  
  
-   変数は、parallel コンストラクト内で宣言されます。  
  
-   変数が**threadprivate**です。  
  
-   変数が、 **const**-型を修飾します。  
  
-   変数が、ループ コントロール変数の**の**直後に続くループ、**の**または**の並列**ディレクティブ、および変数の参照、ループ内が表示されます。.  
  
 変数を指定する、 **firstprivate**、 **lastprivate**、または**削減**かっこで囲んだディレクティブの句では、変数への暗黙的な参照をにより、外側コンテキスト。 このような暗黙的な参照は、上に示した要件に応じたもです。  
  
 1 つだけ**既定**句で指定できる、**並列**ディレクティブです。  
  
 変数の既定値を使用してデータ共有属性をオーバーライドすることができます、**プライベート**、 **firstprivate**、 **lastprivate**、**削減**、および**共有**句、次の例に示すようにします。  
  
```  
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\  
   private(x)  private(r)  lastprivate(i)  
```
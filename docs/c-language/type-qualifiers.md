---
title: "型修飾子 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const キーワード [C]"
  - "メモリ, volatile によるアクセス"
  - "修飾子 (型の)"
  - "型の修飾子"
  - "volatile キーワード [C]"
  - "volatile キーワード [C], 型の修飾子"
  - "volatile キーワード [C], 型指定子"
ms.assetid: bb4c6744-1dd7-40a8-b4eb-f5585be30908
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 型修飾子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型修飾子は、2 つのうちいずれかの特性を識別子に割り当てます。  **const** 型修飾子は、変更不可能なオブジェクトを宣言します。  `volatile` 型修飾子は、同時実行されるスレッドなど、そのプログラムの制御範囲以外の要素によって値を変更できる項目を宣言します。  
  
 これら 2 つの型修飾子 **const** と `volatile` は、宣言で内 1 回だけ使用できます。  型修飾子は型指定子との併用が可能ですが、複数項目宣言で、最初のコンマの後にこれらを指定することはできません。  たとえば、次の宣言は有効です。  
  
```  
typedef volatile int VI;  
const int ci;  
```  
  
 次の宣言は無効です。  
  
```  
typedef int *i, volatile *vi;  
float f, const cf;     
```  
  
 型修飾子が意味を持つのは、式の左辺値として識別子にアクセスする場合のみです。  左辺値および式の詳細については、「[左辺値と右辺値の式](../Topic/L-Value%20and%20R-Value%20Expressions.md)」を参照してください。  
  
## 構文  
 *type\-qualifier*:  
 **constvolatile**  
  
 以下は、有効な **const** 宣言と `volatile` 宣言です。  
  
```  
int const *p_ci;       /* Pointer to constant int */  
int const (*p_ci);     /* Pointer to constant int */  
int *const cp_i;       /* Constant pointer to int */  
int (*const cp_i);     /* Constant pointer to int */  
int volatile vint;     /* Volatile integer        */  
```  
  
 配列型の指定に型修飾子が含まれる場合、要素は修飾されますが、配列型は修飾されません。  関数型の指定に修飾子が含まれる場合、その動作は未定義になります。  `volatile` と **const** はいずれも、オブジェクトの値の範囲または算術的特性に影響を与えません。  
  
 次に、**const** と `volatile` の使用方法について説明します。  
  
-   **const** キーワードを使用できるのは、基本型、集約型、任意の型のオブジェクトへのポインター、または `typedef` を変更する場合です。  **const** 型修飾子のみを使用して項目を宣言した場合、その型は **const int** になります。  **const** 変数は初期化できます。また、ストレージの読み取り専用領域に配置できます。  **const** へのポインターを宣言する場合に **const** キーワードを使用すると便利です。この方法でポインターを宣言すると、関数がそのポインターを一切変更できなくなります。  
  
-   プログラムのどの時点でも、未知のプロセスが `volatile` 変数にアクセスし、その値を使用または変更できると見なされます。  したがって、コマンド ラインで指定した最適化にかかわらず、`volatile` 変数に値を割り当てたり参照したりするコードが必ず \(それが何も影響しない場合でも\) 生成されます。  
  
     `volatile` を単独で使用した場合、`int` を指定したと見なされます。  `volatile` 型指定子を使用すれば、特別なメモリ位置へ確実にアクセスできます。  シグナル ハンドラー、同時実行のプログラム、または特殊なハードウェア \(メモリ マップト I\/O 制御レジスタなど\) がアクセスまたは変更できるデータ オブジェクトで `volatile` を使用します。  変数が有効な間だけ `volatile` として宣言するか、または 1 つの参照を `volatile` にキャストできます。  
  
-   項目は **const** と `volatile` の両方であってもかまいません。その場合、自身のプログラムではその項目を変更できませが、非同期のプロセスでは変更できます。  
  
## 参照  
 [型の宣言](../c-language/declarations-and-types.md)
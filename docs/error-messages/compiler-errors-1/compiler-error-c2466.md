---
title: "コンパイラ エラー C2466 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2466
dev_langs: C++
helpviewer_keywords: C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3c3ad19ce37aa51bd6b670da6e857d7eccce04ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2466"></a>コンパイラ エラー C2466
サイズが 0 の配列を割り当てることができません。  
  
 配列が割り当てられているか、サイズが 0 で宣言されています。 配列のサイズの定数式は、0 より大きい整数である必要があります。 添字が 0 の配列宣言はクラス、構造体、または共用体メンバーに対してのみ、Microsoft 拡張機能でのみ有効です。 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md))。  
  
 次の例では、C2466 が生成されます。  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```
---
title: "減算 (-) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- operators [C], subtraction
- subtraction operator, syntax
ms.assetid: 9cacba7d-20b3-4372-8a63-ba5d8ee64177
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7d07f6bf2c5d48b3149eb43448e217d1a66b92c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="subtraction--"></a>減算 (-)
減算演算子 (**-**) は、最初から 2 番目のオペランドを減算します。 両方のオペランドが整数または浮動小数型でもかまいません。または、1 個のオペランドがポインターで他方が整数でもかまいません。  
  
 2 つのポインターを減算する場合は、差をポインターが指す型の値のサイズで除算することにより、差が符号付き整数値に変換されます。 整数値のサイズは標準インクルード ファイル STDDEF.H の **ptrdiff_t** 型で定義されます。 結果は、2 つのアドレス間にあるその型のメモリ位置の数を表します。 結果は、「[ポインター演算](../c-language/pointer-arithmetic.md)」で説明するように、同じ配列の 2 つの要素に対して意味を持つことのみが保証されます。  
  
 整数値をポインター値から減算すると、減算演算子は、整数値 (*i*) を、ポインターが参照している値のサイズを乗算することによって変換します。 変換後、整数値が *i* のメモリ位置を表します。ここでは、各位置にポインター型で指定された長さがあります。 変換された整数値がポインター値から減算されると、結果は、元のアドレスより前のメモリ アドレス *i* 位置です。 新しいポインターは、元のポインター値によってアドレス指定された型の値をポイントします。  
  
## <a name="see-also"></a>関連項目  
 [C 加法演算子](../c-language/c-additive-operators.md)
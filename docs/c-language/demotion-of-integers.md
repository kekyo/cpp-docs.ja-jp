---
title: "Demotion of Integers (整数の下位変換) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: demoting integers
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e09a81ca21f6e00777322178dcdf1c09ef22dd5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="demotion-of-integers"></a>Demotion of Integers (整数の下位変換)
**ANSI 3.2.1.2** 値を表すことができない場合に、整数を短い符号付き整数に変換したか、符号なし整数を同じ長さの符号付き整数に変換したときの結果  
  
 **long** 整数が **short** にキャストされるか、**short** が `char` にキャストされるときには、下位バイトが保持されます。  
  
 たとえば、次のコード行、  
  
```  
short x = (short)0x12345678L;  
```  
  
 では、値 0x5678 が `x` に代入されます。また、次のコード行、  
  
```  
char y = (char)0x1234;  
```  
  
 では、値 0x34 が `y` に代入されます。  
  
 符号付き変数が符号なしに変換されるときと、その逆で、ビット パターンは変わりません。 たとえば、-2 (0xFE) を符号なしの値にキャストすると、254 (これも 0xFE) になります。  
  
## <a name="see-also"></a>関連項目  
 [整数](../c-language/integers.md)
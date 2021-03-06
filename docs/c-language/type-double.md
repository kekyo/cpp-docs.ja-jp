---
title: "double 型 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- mantissas, floating-point variables
- type double
- portability [C++], type double
- double data type
ms.assetid: 17c85b24-1475-4d41-a03c-ddf2d6561d34
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aa4e81164a02774f7f9aa034f2c1a5492233600d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="type-double"></a>double 型
double 型の倍精度浮動小数点値のサイズは 8 バイトです。 形式は、float 形式に似ています。ただし、エクセス 1023 形式の 11 ビット指数部と 52 ビット仮数部に、暗黙の上位 1 ビットを持ちます。 この形式では、およそ 1.7E-308 から 1.7E+308 の範囲を double 型で表現します。  
  
 **Microsoft 固有の仕様**  
  
 double 型は 64 ビットで、符号が 1 ビット、指数部が 11 ビット、仮数部が 52 ビットです。 その範囲は 15 桁以上の精度で、+/-1.7E308 です。  
  
 **END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [基本型の格納](../c-language/storage-of-basic-types.md)
---
title: "コンパイラ エラー C2344 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2344
dev_langs: C++
helpviewer_keywords: C2344
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c7044ae9c2e15caa7ea2e0992512d22a146ec22a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2344"></a>コンパイラ エラー C2344
align(#): アラインメントは 2 の累乗でなければなりません  
  
 [align](../../cpp/align-cpp.md) キーワードを使用する場合は、渡す値は 2 の累乗である必要があります。  
  
 たとえば、3 は 2 の累乗ではないため、次のコードでは C2344 が生成されます。  
  
```  
// C2344.cpp  
// compile with: /c  
__declspec(align(3)) int a;   // C2344  
__declspec(align(4)) int b;   // OK  
```
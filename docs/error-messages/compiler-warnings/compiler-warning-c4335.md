---
title: "コンパイラの警告 C4335 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4335
dev_langs:
- C++
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ab7406a9c161d47e431cb0af8183d99eac7bfe86
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4335"></a>コンパイラの警告 C4335
Mac ファイル形式が検出されました: ソース ファイルを DOS または UNIX の形式に変換してください  
  
 ソース ファイルの最初の行の行終端文字は、UNIX ('\n') または DOS ('\r\n') ではなく Macintosh スタイル ('\r') です。  
  
 この警告はエラーとして常に発行します。  参照してください[警告](../../preprocessor/warning.md)プラグマをこの警告を無効にする方法についてはします。  また、この警告が発行されるのみ 1 回コンパイル単位ごとです。 したがってが複数ある場合`#include`Macintosh 形式のファイルを指定するディレクティブ、C4335 はのみ発行されます。  
  
 Macintosh 形式でファイルを生成する方法の 1 つを使用して、 **保存オプションの**(上、**ファイル**メニュー) Visual Studio でします。  
  
## <a name="example"></a>例  
 次の例では、C4335 を生成します。  
  
```  
// C4335 expected  
#include "c4335.h"   // assume both include files are in Macintosh format  
#include "c4335_2.h"  
```

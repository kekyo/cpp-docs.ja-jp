---
title: "コンパイラの警告 (レベル 1) C4228 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4228
dev_langs:
- C++
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8e64b3cc33f5f6a879a7a97fcd53561e3ad6a70d
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4228"></a>コンパイラの警告 (レベル 1) C4228
非標準の拡張機能が使用されています : 宣言リストにあるコンマの後の修飾子は無視されます。  
  
 修飾子の使用と同様に**const**または`volatile`後、変数を宣言するときに、コンマは Microsoft 拡張機能 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md))。  
  
## <a name="example"></a>例  
  
```  
// C4228.cpp  
// compile with: /W1  
int j, const i = 0;  // C4228  
int k;  
int const m = 0;  // ok  
int main()  
{  
}  
```

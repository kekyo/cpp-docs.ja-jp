---
title: "コンパイラ エラー C3180 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3180
dev_langs:
- C++
helpviewer_keywords:
- C3180
ms.assetid: 5281f583-7df7-418a-8507-d4da67ed6572
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9724a295840da9d688b4d38d8eb830b01c43e618
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3180"></a>コンパイラ エラー C3180
'type name': 名前は 'limit' 文字のメタデータの限度を超えています  
  
 コンパイラでは、メタデータ内のマネージ型の名前が切り捨てられます。 切り捨てを行った後、この型はで使用できなくなります、`#using`ディレクティブ (または、別の言語のと同じ)。  
  
 型名の制限には、すべての名前空間の修飾子が含まれています。

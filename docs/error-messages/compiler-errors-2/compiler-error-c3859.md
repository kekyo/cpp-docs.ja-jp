---
title: "コンパイラ エラー C3859 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3859
dev_langs: C++
helpviewer_keywords: C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8a132eb7dbf09421ad5c99249b0208e5f901156b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3859"></a>コンパイラ エラー C3859
PCH の仮想メモリの範囲が超えています。'-Zmvalue' 以上のコマンド ライン オプションで再コンパイルしてください。  
  
 プリコンパイル済みヘッダーが、コンパイラが挿入しようとしているデータの量に対して小さすぎます。 使用して、 **/Zm**コンパイラ フラグをプリコンパイル済みヘッダー ファイル用のより大きい値を指定します。 詳細については、次を参照してください。 [/Zm (指定プリコンパイル済みヘッダーのメモリ割り当て制限)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)です。
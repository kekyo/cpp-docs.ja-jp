---
title: "コンパイラ エラー C2818 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2818
dev_langs: C++
helpviewer_keywords: C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 02c1b8e67679e7b8ce69b202c3ddef899439095d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2818"></a>コンパイラ エラー C2818
アプリケーションは、'operator ->' をオーバー ロードされた 'type' を型全体に再帰的には  
  
 クラス メンバー アクセス演算子の再定義を含む再帰的な`return`ステートメントです。 再定義する、`->`再帰では演算子、関数をオーバーライドして、再帰ルーチン オペレーターからと呼ばれる別の関数に移動する必要があります。
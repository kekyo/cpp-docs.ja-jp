---
title: "抽出エラーのテスト | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 088cc150513d593aff5d4250c899eb3712c5fe39
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="testing-for-extraction-errors"></a>抽出エラーのテスト
[エラー処理関数](../standard-library/output-file-stream-member-functions.md)に関する記事で説明されている出力エラー処理関数を、入力ストリームに適用します。 抽出時にエラーをテストすることは重要です。 次のようなステートメントを考えてみましょう。  
  
```  
cin>> n;  
```  
  
 `n` が符号付きの整数である場合、値が 32,767 (最大許容値。つまり MAX_INT) を超えるとストリームの `fail` ビットが設定され、`cin` オブジェクトは使用できなくなります。 これ以降の抽出ではすべて、値が格納されないまますぐに戻り値が返されます。  
  
## <a name="see-also"></a>関連項目  
 [入力ストリーム](../standard-library/input-streams.md)


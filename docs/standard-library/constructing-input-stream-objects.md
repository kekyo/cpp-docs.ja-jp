---
title: "入力ストリーム オブジェクトのコンストラクト | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
caps.latest.revision: 8
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
ms.openlocfilehash: 7e8c664bd6632f480ba53b9dedea914bbc8e4dd7
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="constructing-input-stream-objects"></a>入力ストリーム オブジェクトのコンストラクト
`cin` オブジェクトのみを使う場合は、入力ストリームをコンストラクトする必要はありません。 次のものを使う場合は、入力ストリームをコンストラクトする必要があります。  
  
- [入力ファイル ストリーム コンストラクター](#vclrfinputfilestreamconstructorsanchor8)  
  
- [入力文字列ストリーム コンストラクター](#vclrfinputstringstreamconstructorsanchor9)  
  
##  <a name="vclrfinputfilestreamconstructorsanchor8"></a> 入力ファイル ストリーム コンストラクター  
 入力ファイル ストリームは、2 つの方法で作成できます。  
  
-   `void` 引数コンストラクターを使った後、`open` メンバー関数を呼び出します。  
  
 ```  
    ifstream myFile; // On the stack  
    myFile.open("filename");

 
    ifstream* pmyFile = new ifstream; // On the heap  
    pmyFile->open("filename");
```  
  
-   コンストラクターの呼び出しでファイル名とモード フラグを指定し、それによってコンストラクション プロセスの間にファイルを開きます。  
  
 ```  
    ifstream myFile("filename");
```  
  
##  <a name="vclrfinputstringstreamconstructorsanchor9"></a> 入力文字列ストリーム コンストラクター  
 入力文字列ストリーム コンストラクターには、事前に割り当てられて初期化された記憶域のアドレスが必要です。  
  
```  
string s("123.45");

double amt;  
istringstream myString(s);

//istringstream myString("123.45") also works  
myString>> amt; // amt contains 123.45  
```  
  
## <a name="see-also"></a>関連項目  
 [入力ストリーム](../standard-library/input-streams.md)



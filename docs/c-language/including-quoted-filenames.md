---
title: "引用符で囲まれたファイル名を含む | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 17c40e74a31341fc3a725c5e5b3823058e403cff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="including-quoted-filenames"></a>引用符で囲まれたファイル名を含む
**ANSI 3.8.2** インクルード可能なソース ファイルの引用された名前のサポート  
  
 2 組の二重引用符 (" ") 間にインクルード ファイルのあいまいでない完全なパスを指定すると、プリプロセッサはそのパスのみを検索し、標準ディレクトリを無視します。  
  
 [#include](../preprocessor/hash-include-directive-c-cpp.md) "path-spec" に指定されたインクルード ファイルでは、ディレクトリの検索は親ファイルのディレクトリから始まり、その後にすべての祖父母ファイルのディレクトリが検索されます。 したがって、検索は現在処理中のソース ファイルが含まれるディレクトリに対して相対的に開始されます。 親の親ファイルが存在せず、見つからなかった場合は、ファイル名が山かっこで囲まれているものとして検索が続行されます。  
  
## <a name="see-also"></a>関連項目  
 [プリプロセス ディレクティブ](../c-language/preprocessing-directives.md)
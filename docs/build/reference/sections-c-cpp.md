---
title: "セクション (C/C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SECTIONS
dev_langs: C++
helpviewer_keywords: SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9d1564d068f4d69c3190b8bb24a32e7efb01dbef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="sections-cc"></a>SECTIONS (C/C++)
1 つまたは複数のセクションを導入`definitions`のセクションで、プロジェクトの出力ファイルのアクセス指定子であります。  
  
```  
SECTIONS  
definitions  
```  
  
## <a name="remarks"></a>コメント  
 各定義は個別の行に指定する必要があります。 `SECTIONS`キーワードは、最初の定義と同じ行または前の行を指定できます。 .Def ファイルは、1 つまたは複数を含めることができます`SECTIONS`ステートメントです。  
  
 これは、`SECTIONS`ステートメントは、イメージ ファイルのセクションでは 1 つまたは複数の属性を設定し、セクションの各種類の既定の属性をオーバーライドするために使用できます。  
  
 形式`definitions`は。  
  
 `.section_name specifier`  
  
 ここで`.section_name`プログラム イメージ内のセクションの名前を指定し、`specifier`は次のアクセス修飾子を 1 つ以上。  
  
|修飾子|説明|  
|--------------|-----------------|  
|`EXECUTE`|セクションが実行可能ファイル|  
|`READ`|データの読み取り操作します。|  
|`SHARED`|イメージを読み込むすべてのプロセス間でセクションを共有します|  
|`WRITE`|データの書き込み操作します。|  
  
 指定子名をスペースで区切ります。 例:  
  
```  
SECTIONS  
.rdata READ WRITE  
```  
  
 `SECTIONS`セクションの一覧の先頭をマーク`definitions`です。 各`definition`別々 の行にある必要があります。 `SECTIONS`キーワードは、最初と同じ行に配置できます`definition`または前の行。 .Def ファイルは、1 つまたは複数を含めることができます`SECTIONS`ステートメントです。 `SEGMENTS`のシノニムとしてキーワードがサポートされている`SECTIONS`です。  
  
 古いバージョンの Visual C がサポートされています。  
  
```  
section [CLASS 'classname'] specifier  
```  
  
 `CLASS`キーワードは、互換性のためサポートされますは無視されます。  
  
 セクションの属性を指定するのと同じ方法は、 [/section](../../build/reference/section-specify-section-attributes.md)オプション。  
  
## <a name="see-also"></a>関連項目  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)
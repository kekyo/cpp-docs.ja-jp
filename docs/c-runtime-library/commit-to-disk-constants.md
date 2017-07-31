---
title: "ディスク コミット定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.constants
dev_langs:
- C++
helpviewer_keywords:
- commit-to-disk constants
ms.assetid: 0b903b23-b4fa-431e-a937-51d95f695ecf
caps.latest.revision: 6
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ed87b11ce1938abb0ef7b31cc9ca03e6b0f76903
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="commit-to-disk-constants"></a>ディスク コミット定数
**Microsoft 固有の仕様**  
  
## <a name="syntax"></a>構文  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>コメント  
 これらの Microsoft 固有の定数は、開いているファイルに関連付けられているバッファーが、オペレーティング システムのバッファーまたはディスクにフラッシュされるかどうかを指定します。 このモードは、読み取り/書き込みのアクセス権の種類 (**"r"**、**"w"**、**"a"**、**"r+"**、**"w+"**、**"a+"**) を指定する文字列に含まれます。  
  
 ディスク コミット モードは次のとおりです。  
  
 **c**  
 指定したバッファーの書き込まれていない内容をディスクに書き込みます。 このディスク コミット機能は、[fflush](../c-runtime-library/reference/fflush.md) または [_flushall](../c-runtime-library/reference/flushall.md) 関数のいずれかを明示的に呼び出す場合にのみ発生します。 このモードは、機密データを処理する場合に便利です。 たとえば、プログラムが `fflush` または `_flushall` を呼び出した後に終了する場合、データがオペレーティング システムのバッファーに達したと考えて間違いありません。 ただし、ファイルを **c** オプションで開く場合を除き、オペレーティング システムも終了する場合は、データがディスクに書き込まれることはほぼありません。  
  
 **n**  
 指定したバッファーの書き込まれていない内容をオペレーティング システムのバッファーに書き込みます。 オペレーティング システムはデータをキャッシュし、ディスクに書き込むための最適な時間を決定します。 多くの状況で、この動作は効率的なプログラムの動作になります。 ただし、データの保有期間が重要な場合 (銀行取引や航空券の情報など) は、**c**オプションを使用することを検討してください。 既定では **n** モードです。  
  
> [!NOTE]
>  **c** および **n** オプションは、`fopen` の ANSI 標準には含まれませんが、Microsoft 拡張機能です。ANSI 互換が必要な場合は使用しないでください。  
  
## <a name="using-the-commit-to-disk-feature-with-existing-code"></a>既存のコードと共にディスク コミット機能を使用する  
 既定では、[fflush](../c-runtime-library/reference/fflush.md) または [_flushall](../c-runtime-library/reference/flushall.md) ライブラリ関数への呼び出しは、オペレーティング システムによって保持されるバッファーにデータを書き込みます。 オペレーティング システムでは、ディスクにデータを実際に書き込むための最適な時間を決定します。 ランタイム ライブラリのディスク コミット機能を使用すると、重要なデータをオペレーティング システムのバッファーではなく、ディスクに直接書き込むことができます。 既存のプログラムのオブジェクト ファイルと COMMODE.OBJ をリンクさせて書き直すことなく、既存のプログラムにこの機能を提供することができます。  
  
 生成される実行ファイルでは、`fflush` への呼び出しはバッファーの内容をディスクに直接書き込み、`_flushall` への呼び出しはすべてのバッファーの内容をディスクに書き込みます。 これら 2 つの関数のみが、COMMODE.OBJ の影響を受けます。  
  
 **END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../c-runtime-library/stream-i-o.md)   
 [_fdopen、_wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen、_wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)
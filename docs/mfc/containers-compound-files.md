---
title: "コンテナー : 複合ファイル | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アクセス モード (ファイルの) [C++]"
  - "複合ドキュメント"
  - "複合ファイル"
  - "コンテナー [C++], 複合ファイル"
  - "ドキュメント [C++], 複合"
  - "ドキュメント [C++], OLE"
  - "ファイル [C++], 複合"
  - "OLE コンテナー, 複合ファイル"
  - "OLE ドキュメント, 複合ファイル"
  - "パフォーマンス [C++], 複合ファイル"
  - "標準化されたファイル構造体の複合ファイル"
ms.assetid: 8b83cb3e-76c8-4bbe-ba16-737092b36f49
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# コンテナー : 複合ファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、OLE アプリケーションで複合ファイルを使用する場合の複合ファイル コンポーネントと実装や利点と欠点について説明します。  
  
 複合ファイルは、OLE の不可欠な部分です。  それをデータ転送を OLE ドキュメントのストレージを容易にするために使用されます。  複合ファイルは実行中の構造化ストレージ モデルの実装です。  一貫したインターフェイスは、サポート シリアル化ストレージ、ストリーム、またはオブジェクト ファイルにあります。  複合ファイルはクラス `COleStreamFile` と `COleDocument`で Microsoft Foundation Class ライブラリでサポートされます。  
  
> [!NOTE]
>  複合ファイルを使用して情報を OLE ドキュメントまたは複合ドキュメントであることを意味しません。  複合ファイルで複合ドキュメント、OLE ドキュメントを保存する方法の 1、および他のデータです。  
  
##  <a name="_core_components_of_a_compound_file"></a> 複合ファイル コンポーネント  
 複合ファイルの OLE 実装は 3 個のオブジェクト型を使用する: ストリーム オブジェクト、ストレージ オブジェクトと `ILockBytes` オブジェクト。  これらのオブジェクトは、標準のファイル システム コンポーネントには、次のように似ています:  
  
-   ストリーム オブジェクトは、ファイルなどのデータ入力します。  
  
-   ストレージ オブジェクトは、ディレクトリなど、他のストレージおよびストリーム オブジェクトを含めることができます。  
  
-   **LockBytes** オブジェクトはストレージ オブジェクトと物理的なハードウェア間のインターフェイスを表します。  これらは、ストレージ デバイスに **LockBytes** オブジェクトがアクセスする実際のバイトがグローバル メモリのハード ドライブまたは領域など、どのように表示されるかを決定します。  **LockBytes** オブジェクトに関する詳細についてと `ILockBytes` は *OLE Programmer's Reference*し、インターフェイスを参照します。  
  
##  <a name="_core_advantages_and_disadvantages_of_compound_files"></a> 複合ファイルの長所と短所  
 複合ファイル ストレージの初期メソッドを使用できないことを示します。  Windows コモン コントロールには以下が含まれます。  
  
-   インクリメンタル ファイル アクセス。  
  
-   ファイル アクセス モード。  
  
-   ファイル構造の正規化。  
  
 複合ファイルの短所は、—フロッピー ディスクのストレージに関する大きいとパフォーマンスの問題をアプリケーションで使用するには、—決定した場合かどうかも検討する必要があります。  
  
###  <a name="_core_incremental_access_to_files"></a> ファイルに対するインクリメンタル アクセス  
 ファイルに対するインクリメンタル アクセスは、複合ファイルの自動利点です。  複合ファイルに「ファイル内のファイル システムと見なすことができるため」、個々のオブジェクト型は、ストリームまたはストレージなどのファイル全体を読み込むせずにもアクセスできます。  これには、アプリケーションがユーザーによって編集用の新しいオブジェクトにアクセスする必要がある時間を短くできます。  インクリメンタル更新は、同じ概念に基づいて、同様の機能を提供します。  ファイル全体で格納する代わりに行われた OLE 1 つオブジェクトへの変更をユーザーが編集するストリームまたはストレージ オブジェクトだけを格納する格納する。  
  
###  <a name="_core_file_access_modes"></a> ファイル アクセス モード  
 複合ファイル オブジェクトへの変更はディスクにいつコミット決定されます。複合ファイルを使用するもう一つの利点です。  ファイルが、処理されてアクセスされたり、指示モードは、変更がコミットになったかどうかを判定します。  
  
-   トランザクション モードは、複合ファイルで変更を保存するか、元に戻すことをユーザーがクリックするまでオブジェクトに変更を加えるために 2 フェーズ コミット操作を使用し、それによって使用できるドキュメントの古い値と新しいコピーを保持します。  
  
-   ダイレクト モードは後で元に戻す機能なしで行った変更としてドキュメントに変更を組み込む。  
  
 アクセス モードの詳細については、*OLE Programmer's Reference を*参照します。  
  
###  <a name="_core_standardization"></a> 標準化  
 複合ファイルの正規化された構造体は、実際にファイルを作成したアプリケーションを認識せずに OLE アプリケーションによって作成される複合ファイルを参照する各 OLE アプリケーションを有効にします。  
  
###  <a name="_core_size_and_performance_considerations"></a> サイズおよび Performance Considerations  
 この形式を使用してデータを、ファイルは、インクリメント方式で格納する複合ファイル ストレージ構造体および機能の複雑さに構造化されていないまたは「フラット ファイル」のストレージを使用して他のファイルより大きくする傾向があります。  アプリケーションが頻繁にファイルを読み込み、保存して、複合ファイルを使用して、ファイル サイズを noncompound ファイルよりもすばやく増加することができます。  複合ファイルが大きくなる可能性があるため、ファイルへのアクセス時刻はに格納し、フロッピー ディスクから、ファイルに対するアクセス、後に、読み込みましたが低下する可能性があります。  
  
 パフォーマンスに影響する別の問題は、ファイルのフラグメンテーションです。  複合ファイル サイズがファイルで使用される 1 番目の最後のディスクのセクターの違いによって決まります。  断片化したファイルはサイズを計算するときにデータを空き領域のさまざまな領域を含む含まないができますが、カウントされます。  複合ファイルの有効期間中、これらの領域はストレージ オブジェクトの挿入や削除によって作成されます。  
  
##  <a name="_core_using_compound_files_format_for_your_data"></a> データの複合ファイル形式を使用します。  
 正常にドキュメント クラスを持つアプリケーションを作成すると `COleDocument`から、確認してから、メイン ドキュメントのコンストラクター呼び出し `EnableCompoundFile`を派生しました。  アプリケーション ウィザードが OLE コンテナー アプリケーションを作成すると、この呼び出しが挿入されます。  
  
 *OLE Programmer's Reference*で、[IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)、[IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015)と [ILockBytes](http://msdn.microsoft.com/library/windows/desktop/aa379238)を参照してください。  
  
## 参照  
 [コンテナー](../mfc/containers.md)   
 [コンテナー : ユーザー インターフェイスの問題](../mfc/containers-user-interface-issues.md)   
 [COleStreamFile クラス](../Topic/COleStreamFile%20Class.md)   
 [COleDocument クラス](../mfc/reference/coledocument-class.md)
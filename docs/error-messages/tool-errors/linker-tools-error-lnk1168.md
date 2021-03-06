---
title: "リンカ ツール エラー LNK1168 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1168"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1168"
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# リンカ ツール エラー LNK1168
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

書き込みモードで 'filename' を開けません。  
  
 リンカーは `filename` に書き込むことができません。  ファイルが使用中で、そのファイル ハンドルが別のプロセスによってロックされている可能性があります。または、ファイルに対する書き込みアクセス許可、あるいはファイルが配置されているディレクトリやネットワーク共有に対する書き込みアクセス許可がない可能性があります。  このエラーの原因は、多くの場合、ウイルス対策プログラムによって設定されているロック、ファイル検索インデックス作成プロセス、[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] ビルド システムが設定したロックを解除する際に発生する遅延のように一時的なものです。  
  
 この問題を解決するには、`filename` ファイル ハンドルがロックされていないこと、およびファイルに対する書き込みアクセス許可があることを確認します。  実行可能ファイルの場合は、そのファイルが実行されていないことを確認します。  
  
 Windows SysInternals ユーティリティである[ハンドル](http://technet.microsoft.com/sysinternals/bb896655.aspx)または[プロセス エクスプローラー](http://technet.microsoft.com/sysinternals/bb896653)を使用すると、`filename` のどのプロセスにファイル ハンドルのロックがあるかを特定できます。  また、プロセス エクスプローラーを使用して、開いているファイル ハンドルのロックを解除することもできます。  これらのユーティリティの使用方法については、そのユーティリティに付属のヘルプ ファイルを参照してください。  
  
 ファイルがウイルス対策プログラムによってロックされている場合、この問題を解決するには、ウイルス対策プログラムによる自動スキャンの対象からビルド出力ディレクトリを除外します。  ウイルス対策スキャナーは、多くの場合、ファイル システムで新しいファイルを作成することにより実行され、スキャンの実行中は、このスキャナーによりファイルがロックされます。  特定のディレクトリをスキャン対象から除外する方法の詳細については、ウイルス対策プログラムのドキュメントを参照してください。  
  
 ファイルが検索インデックス作成サービスによってロックされている場合、この問題を解決するには、自動インデックス作成の対象からビルド出力ディレクトリを除外します。  詳細については、インデックス作成サービスのドキュメントを参照してください。  Windows 検索インデックス作成サービスを変更するには、Windows の **\[コントロール パネル\]** で **\[インデックスのオプション\]** を使用します。  詳細については、「[インデックスを使って Windows の検索を効率化する: よく寄せられる質問](http://windows.microsoft.com/en-us/windows/improve-windows-searches-using-index-faq#1TC=windows-7)」を参照してください。  
  
 ビルド処理で実行可能ファイルを上書きできない場合、そのファイルは、ファイル エクスプローラーによってロックされている可能性があります。  **アプリケーション エクスペリエンス** サービスが無効の場合、ファイル エクスプローラーでは、長時間にわたって実行可能ファイルのハンドル ロックが保持されることがあります。  この問題を解決するには、**services.msc** を実行し、**アプリケーション エクスペリエンス** サービスの **\[プロパティ\]** ダイアログ ボックスを開いて、  **\[スタートアップの種類\]** を **\[無効\]** から **\[手動\]** に変更します。  
  
## 参照  
 [Visual C\+\+ でソリューションまたは ActiveX プロジェクトのビルド時に "error PRJ0008" または "Fatal error LNK1168" のエラー メッセージが表示される](http://support.microsoft.com/kb/308358)
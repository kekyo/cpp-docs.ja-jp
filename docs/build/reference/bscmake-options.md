---
title: "BSCMAKE オプション |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCBscMakeTool.OutputFile
- VC.Project.VCBscMakeTool.SuppressStartupBanner
- VC.Project.VCBscMakeTool.PreserveSBR
dev_langs: C++
helpviewer_keywords:
- /v BSCMAKE option
- Iu BSCMAKE option
- browse information files (.bsc), content
- /Er BSCMAKE option
- NOLOGO BSCMAKE option
- /s BSCMAKE option
- /Ei BSCMAKE option
- /o BSCMAKE option
- /NOLOGO BSCMAKE option
- /Iu BSCMAKE option
- s BSCMAKE option (/s)
- /Em BSCMAKE option
- Em BSCMAKE option
- Es BSCMAKE option
- files [C++], BSCMAKE
- Er BSCMAKE option
- BSCMAKE, options for controlling files
- controlling BSCMAKE options
- El BSCMAKE option
- /El BSCMAKE option
- /Es BSCMAKE option
- Ei BSCMAKE option
ms.assetid: fa2f1e06-c684-41cf-80dd-6a554835ebd2
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 972ac61ff4e838e1c1bf2ad10db50f3a3d595a5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-options"></a>BSCMAKE オプション
ここでは、BSCMAKE を制御するためのオプションを説明します。 一部のオプションでは、特定の情報を除外するか、または含めることによってブラウザー情報ファイルの内容を制御できます。 除外オプションを使用すると、BSCMAKE の処理が速くなるだけでなく、.bsc ファイルのサイズが小さくなります。 オプション名は大文字小文字を区別 (除く**/help**と**/NOLOGO**)。  
  
 のみ**/NOLOGO**と**/o**は、Visual Studio 開発環境から入手します。  参照してください[Visual C プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)については、プロジェクトのプロパティ ページにアクセスします。  
  
 /Ei ( `filename`...)  
 指定したインクルード ファイルの内容をブラウザー情報ファイルから除外します。 複数のファイルを指定する場合は、スペースで名前を区切り、名前のリストをかっこで囲みます。 かっこは、指定する `filename` が 1 つだけの場合は不要です。 使用して**/Ei**と共に、 **/Es**で除外されないファイルを除外するオプション**/Es**です。  
  
 /El  
 ローカル シンボルを除外します。 既定では、ローカル シンボルは含まれます。 ローカル シンボルの詳細については、次を参照してください。 [.sbr ファイルの作成](../../build/reference/creating-an-dot-sbr-file.md)です。  
  
 /Em  
 マクロの本体のシンボルを除外します。 使用して**/Em**ブラウザー情報ファイルにマクロの名前のみを含める。 既定では、マクロ名とマクロの展開の結果の両方が含められます。  
  
 /Er (`symbol`...)  
 指定したシンボルをブラウザー情報ファイルから除外します。 複数のシンボル名を指定する場合は、スペースで名前を区切り、名前のリストをかっこで囲みます。 かっこは、指定する `symbol` が 1 つだけの場合は不要です。  
  
 /Es  
 絶対パスで指定されたインクルード ファイル、または INCLUDE 環境変数内の絶対パスで検索できるインクルード ファイルを、すべてブラウザー情報ファイルから除外します。 通常、こういったインクルード ファイルは、ブラウザー情報ファイルでは必要としない情報が数多く格納されているシステム インクルード ファイルです。このオプションでは、パスなしで指定されたファイル、相対パスで指定されたファイル、または INCLUDE の相対パスで見つかるファイルは除外されません。 使用することができます、 **/Ei**オプションと共に**/Es**ファイルを除外するのには**/Es**は除外されません。 ファイルの一部のみを除外するかどうかを**/Es**を除外を使用して**/Ei**の代わりに**/Es**と除外するファイルを一覧表示します。  
  
 /errorreport: [なし &#124; プロンプト &#124; キュー &#124; 送信]  
 bscmake.exe の内部エラーについての情報を Microsoft に送信できます。  
  
 詳細については**/errorreport**を参照してください[/errorReport (内部コンパイラ エラーの報告)](../../build/reference/errorreport-report-internal-compiler-errors.md)です。  
  
 /HELP  
 BSCMAKE コマンド ライン構文の簡単な説明を表示します。  
  
 /Iu  
 未参照シンボルを含めます。 既定では、定義されているが、参照はされていないシンボルは記録されません。 .sbr ファイルがパックされている場合、このオプションはその入力ファイルには効果がありません。なぜなら、コンパイラによって未参照シンボルが既に削除されているためです。  
  
 /n  
 ノンインクリメンタル ビルドを強制的に実行します。 使用して **/n**  .bsc ファイルが存在するかどうか、ブラウザー情報ファイルの完全ビルドを強制して、.sbr ファイルが切り捨てられないようにするのにします。 参照してください[BSCMAKE による .bsc ファイルのビルド方法](../../build/reference/how-bscmake-builds-a-dot-bsc-file.md)です。  
  
 /NOLOGO  
 BSCMAKE の著作権メッセージが表示されなくなります。  
  
 /o `filename`  
 ブラウザー情報ファイルの名前を指定します。 既定では、ブラウザー情報ファイルの名前は最初の .sbr ファイルの基本名と拡張子 .bsc で構成されます。  
  
 /S ( `filename`...)  
 指定したインクルード ファイルを最初に見つけたときに処理し、それ以降では除外するように BSCMAKE に通知します。 このオプションを使用すると、ファイル (.c または .cpp ソース ファイルのヘッダー (.h) ファイルなど) が、複数のソース ファイルにインクルードされているがプリプロス ディレクティブによっては変更されない場合、処理時間を短縮できます。 また、このオプションは、作成するブラウザー情報ファイルにとってあまり重要ではない方法でファイルが変更される場合にも使用できます。 複数のファイルを指定する場合は、スペースで名前を区切り、名前のリストをかっこで囲みます。 かっこは、指定する `filename` が 1 つだけの場合は不要です。 含まれているたびに、このファイルを除外するには、使用する場合、 **/Ei**または**/Es**オプション。  
  
 /v  
 処理される各 .sbr ファイルの名前や、BSCMAKE の実行についての情報が含まれる詳細出力を表示します。  
  
 /?  
 BSCMAKE コマンド ライン構文の簡単な説明を表示します。  
  
 3 つの .sbr ファイルから MAIN.bsc の完全ビルドを実行するには、次のコマンド ラインを使用します。 このコマンド ラインでは、TOOLBOX.h の重複インスタンスが除外されます。  
  
```  
BSCMAKE /n /S toolbox.h /o main.bsc file1.sbr file2.sbr file3.sbr  
```  
  
## <a name="see-also"></a>関連項目  
 [BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)
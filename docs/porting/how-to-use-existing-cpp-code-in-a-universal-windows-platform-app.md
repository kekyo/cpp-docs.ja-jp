---
title: "方法: ユニバーサル Windows アプリで既存の C++ コードを使用する | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 87e5818c-3081-42f3-a30d-3dca2cf0645c
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 10b63f8e7bd7d23e75417e28b45d533832c8426e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-existing-c-code-in-a-universal-windows-platform-app"></a>方法: ユニバーサル Windows アプリで既存の C++ コードを使用する
UWP 環境でデスクトップ プログラムを実行できるようにする最も簡単な方法は、おそらく、デスクトップ ブリッジ テクノロジを使うことです。 このテクノロジに含まれる Desktop App Converter は、既存のアプリケーションを UWP アプリとしてパッケージ化し、コードの変更は必要ありません。 詳しくは、「[Desktop Bridge でデスクトップ アプリをユニバーサル Windows プラットフォーム (UWP) 用に変換する](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-root)」をご覧ください。

以下では、C++ ライブラリ (DLL とスタティック ライブラリ) をユニバーサル Windows プラットフォーム (UWP) に移植する方法を説明します。 C++ のコア ロジックを複数の UWP アプリで使用できるようにする場合、これが必要になることがあります。 
  
 UWP アプリは保護された環境で実行されるため、プラットフォームのセキュリティを損なう可能性がある多くの Win32、COM、および CRT API の呼び出しは許可されていません。 /ZW オプションが使用されていると、コンパイラはこのような呼び出しを検出し、エラーを生成することができます。 アプリ認定キットをアプリケーションに対して使用して、禁止されている API を呼び出すコードを検出することができます。 「[Windows アプリ認定キットの使用](https://msdn.microsoft.com/library/windows/apps/hh694081.aspx)」をご覧ください。  
  
 ソース コードがライブラリに使用できるなら、禁止されている API 呼び出しを除去できる場合があります。 許可または禁止されている API の一覧を含む詳細については、「[Windows ランタイム アプリの Win32 API と COM API (システム)](https://msdn.microsoft.com/library/windows/apps/br205762.aspx)」および「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](https://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。 いくつかの代替手段が「[Windows ランタイム アプリでの Windows API の代替](https://msdn.microsoft.com/library/windows/apps/hh464945.aspx)」にあります。  
  
 ユニバーサル Windows プロジェクトから従来のデスクトップ ライブラリへの参照を追加しようとすると、ライブラリに互換性がないことを示すエラー メッセージを受け取ります。 スタティック ライブラリの場合、従来の Win32 アプリケーションの場合と同様、ライブラリ (.lib ファイル) をリンカー入力に追加するだけでライブラリにリンクできます。 バイナリのみが使用可能なライブラリの場合は、これが唯一の選択肢です。 スタティック ライブラリはアプリの実行可能ファイルにリンクされますが、UWP アプリで使用する Win32 DLL は、プロジェクトに含め、"Content" としてマークすることによって、アプリにパッケージする必要があります。 ユニバーサル Windows プラットフォームのアプリで Win32 DLL を読み込むには、LoadLibrary や LoadLibraryEx ではなく、[LoadPackagedLibrary](https://msdn.microsoft.com/library/windows/desktop/hh447159.aspx) を呼び出す必要もあります。  
  
 DLL ライブラリかスタティック ライブラリのソース コードがある場合は、/ZW を使用して UWP プロジェクトとして再コンパイルできます。 こうするなら、ソリューション エクスプローラーを使用して参照を追加し、その参照を C++ UWP アプリで使用することができます。 DLL の場合は、エクスポート ライブラリでリンクさせます。  
  
 他の言語の呼び出し元に機能を公開するために、ライブラリを Windows ランタイム コンポーネントに変換することができます。 Windows ランタイム コンポーネントは通常の DLL とは異なります。Windows ランタイム コンポーネントでは、コンテンツを説明するメタデータが .winmd ファイル形式になっています。これは、.NET および JavaScript のコンシューマーが必要とする形式です。 他の言語に API 要素を公開するには、ref クラスのような C++/CX コンストラクトを追加して公開するか、[Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)使用できます。  Windows 10 以降では、C++/CX の代わりに [C++/WinRT ライブラリ](https://github.com/microsoft/cppwinrt)を使うことができます。 
  
 これまでの説明は、COM コンポーネントには当てはまりません。COM コンポーネントは、異なる仕方で扱う必要があります。 EXE または DLL で COM サーバーを使っている場合、[登録を必要としない COM コンポーネント](https://msdn.microsoft.com/library/dd408052.aspx)としてパッケージ化し、コンテンツ ファイルとしてプロジェクトに追加して、[CoCreateInstanceFromApp](https://msdn.microsoft.com/library/windows/apps/hh404137.aspx) を使ってインスタンス化するのであれば、COM サーバーをユニバーサル Windows プロジェクトで使うことができます。 「[Using Free-COM DLL in Windows Store C++ Project](http://blogs.msdn.com/b/win8devsupport/archive/2013/05/20/using-free-com-dll-in-windows-store-c-project.aspx)」(Windows ストア C++ プロジェクトでの Free-COM DLL の使用) をご覧ください。  
  
 ユニバーサル Windows プラットフォームに移植したい既存の COM ライブラリがある場合、[Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md) を使うことで、Windows ランタイム コンポーネントに変換できます。 WRL は ATL と OLE のすべての機能をサポートしているわけではありません。そのため、移植が可能かどうかは、コンポーネントに COM、ATL、および OLE のどの機能が必要で、使用する COM コードがそれにどの程度依存しているかによって決まります。  
  
 ユニバーサル Windows プラットフォームのプロジェクトで既存の C++ コードを使える方法は、いろいろあります。 これらの方法の中には、コンポーネントの拡張子 (C++/CX) を有効にして (つまり、/ZW オプションを使用して) コードを再コンパイルすることが不要なものと必要なものがあります。したがって、コードを標準 C++ のまま保持する、または一部のコードのために従来の Win32 コンパイル環境を維持する必要がある場合は、適切なアーキテクチャを選択してそうすることができます。 たとえば、ユニバーサル Windows プラットフォームの UI と C#、Visual Basic、および JavaScript の呼び出し元に公開する必要がある型を含むコード全体は、Windows アプリ プロジェクトと Windows ランタイム コンポーネント プロジェクトに配置する必要があります。 C++ (C++/CX を含む) コードだけで使用する必要があるコードの場合は、/WX オプションを使用してコンパイルするプロジェクトまたは標準 C++ のプロジェクトに配置できます。 バイナリのみのコードは、スタティック ライブラリとしてリンクさせることにより使用できます。禁止されている API を使用しないのであれば、コンテンツとしてアプリと一緒にパッケージ化して DLL に読み込むこともできます。  
  
 これらのうちのどの開発シナリオを選択する場合でも、従来のデスクトップ Win32 でもユニバーサル Windows プラットフォームでも条件に応じてコードをコンパイルできるように、コードで使用できるマクロ定義の数を意識してください。  
  
```cpp  
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)  
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)  
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)  
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)  
```  
  
 これらのステートメントは、それぞれ、Windows ストア アプリ、Windows Phone ストア アプリ、両方のアプリ、どちらでもないアプリ (クラシック Win32 デスクトップのみ) の順に適用されます。 これらのマクロは Windows SDK 8.1 以降でのみ使用可能です。それ以前のバージョンの Windows SDK を使用してコードをコンパイルする必要があるか、Windows 以外のプラットフォーム用にコンパイルする必要がある場合は、マクロが全く定義されないケースも考えられます。  
  
 このトピックでは、次の手順を説明します。  
  
1.  [ユニバーサル Windows プラットフォーム アプリで Win32 DLL を使用する](#BK_Win32DLL)  
  
2.  [UWP アプリでネイティブ C++ スタティック ライブラリを使用する](#BK_StaticLib)  
  
3.  [C++ ライブラリをWindows ランタイム コンポーネントに移植する](#BK_WinRTComponent)  
  
##  <a name="BK_Win32DLL"></a> ユニバーサル Windows プラットフォーム アプリで Win32 DLL を使用する  
 セキュリティと信頼性を向上させるため、ユニバーサル Windows アプリは制限付きランタイム環境で実行されます。したがって、従来の Windows デスクトップ アプリケーションの場合のようにネイティブ DLL を任意に使用することはできません。 DLL のソース コードがある場合、コードが UWP 上で実行されるように、コードを移植することができます。 まず、いくつかのプロジェクト設定とプロジェクト ファイル メタデータを変更し、プロジェクトを UWP プロジェクトとして識別させます。 /ZW オプションを使用してライブラリ コードをコンパイルする必要があります。これにより、C++/CX が使用可能になります。 特定の API 呼び出しは、環境と関連付けられているより厳密な制御のため、UWP アプリでは許可されていません。 「[Windows ランタイム アプリおよびユニバーサル Windows プラットフォーム (UWP) アプリの Win32 と COM](https://msdn.microsoft.com/library/windows/apps/br205757.aspx)」をご覧ください。  
  
 次の手順は、__declspec(dllexport) を使用して関数を公開するネイティブ DLL がある場合に適用されます。  
  
#### <a name="to-port-a-native-dll-to-the-uwp-without-creating-a-new-project"></a>新しいプロジェクトを作成せずに UWP にネイティブ DLL を移植するには  
  
1.  __declspec(dllexport) を使用して関数をエクスポートするネイティブ DLL がある場合は、DLL を UWP プロジェクトとして再コンパイルすることで UWP アプリからこれらの関数を呼び出すことができます。 たとえば、いくつかのクラスとそのメソッドをエクスポートする DLL があり、次のヘッダー ファイルのようなコードを使用するとします。  
  
    ```  
    // giraffe.h  
    #pragma once  
  
    #ifdef _DLL  
    #define GIRAFFE_API __declspec(dllexport)  
    #else  
    #define GIRAFFE_API   
    #endif  
  
    GIRAFFE_API int giraffeFunction();  
  
    class Giraffe  
    {  
        int id;  
            Giraffe(int id_in);  
        friend class GiraffeFactory;  
  
    public:  
        GIRAFFE_API int GetID();  
    };  
  
    class GiraffeFactory  
    {  
        static int nextID;  
    
    public:  
        GIRAFFE_API GiraffeFactory();  
        GIRAFFE_API static int GetNextID();  
        GIRAFFE_API static Giraffe* Create();  
   };  
    ```  
  
     コード ファイルは以下のようになります。  
  
    ```  
    // giraffe.cpp  
    #include "stdafx.h"  
    #include "giraffe.h"  
  
    Giraffe::Giraffe(int id_in) : id(id_in)  
    {  
    }  
  
    int Giraffe::GetID()  
    {  
      return id;  
    }  
  
    int GiraffeFactory::nextID = 0;  
  
    GiraffeFactory::GiraffeFactory()  
    {  
        nextID = 0;  
    }  
  
    int GiraffeFactory::GetNextID()  
    {  
        return nextID;  
    }  
  
    Giraffe* GiraffeFactory::Create()  
    {  
        return new Giraffe(nextID++);  
    }  
  
    int giraffeFunction();  
    ```  
  
     プロジェクト内の他のすべてのもの (stdafx.h、dllmain.cpp) は、標準の Win32 プロジェクト テンプレートの一部です。 これらの手順に従うものの、独自の DLL をまだ使用しない場合は、Win32 プロジェクトを作成してみて、プロジェクト ウィザードで DLL を選択してから、ヘッダー ファイル giraffe.h とコード ファイル giraffe.cpp を追加し、この手順のコードの内容を適切なファイルにコピーします。  
  
     _DLL が定義されている場合 (つまり、プロジェクトが DLL としてビルドされている場合)、__declspec(dllexport) に解決されるマクロ GIRAFFE_API がコードで定義されます。  
  
2.  DLL プロジェクトの [プロジェクトのプロパティ] を開き、構成を **[すべての構成]** に設定します。  
  
3.  [プロジェクトのプロパティ] にある **[C/C++]** の **[全般]** タブで、**[Windows ランタイム拡張機能の使用]** を **[はい (/ZW)]** に設定します。 これにより、コンポーネントの拡張機能 (C++/CX) が使用可能になります。  
  
4.  **ソリューション エクスプローラー**で、プロジェクト ノードを選び、ショートカット メニューを開いて **[プロジェクトのアンロード]** を選びます。 次に、アンロードしたプロジェクト ノードのショートカット メニューを開き、プロジェクト ファイルの編集を選択します。 WindowsTargetPlatformVersion 要素を見つけて、次の要素に置き換えます。  
  
    ```xml  
    <AppContainerApplication>true</AppContainerApplication>  
    <ApplicationType>Windows Store</ApplicationType>  
    <WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>  
    <WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>  
    <ApplicationTypeRevision>10.0</ApplicationTypeRevision>  
    ```  
  
     .vcxproj ファイルを閉じて、ショートカット メニューを再度開き、**[プロジェクトの再読み込み]** を選びます。  
  
     これで、ソリューション エクスプ ローラーがプロジェクトをユニバーサル Windows プロジェクトとして識別するようになります。  
  
5.  プリコンパイル済みヘッダー ファイル名が正しいことを確認します。 Precompiled Headers セクションで、プリコンパイル済みヘッダー ファイルを pch.h から stdafx.h に変更します。 これを行わないと、次のエラーが表示されます。  
  
    ```Output  
    error C2857: '#include' statement specified with the /Ycpch.h command-line option was not found in the source file  
    ```  
  
     問題は、ユニバーサル Windows プロジェクトでプリコンパイル済みヘッダー ファイルに対して別の名前付け規則が使用されていることです。  
  
6.  プロジェクトをビルドします。 互換性のないコマンド ライン オプションに関するエラーが発生する場合があります。 たとえば、頻繁に使用されるオプション [最小リビルドを有効にする (/Gm)] は多くの C++ プロジェクトで既定で設定され、/ZW と互換性がありません。  
  
     ユニバーサル Windows プラットフォーム用にコンパイルする場合、一部の関数は使用できません。 問題があるとそれに関するコンパイラ エラーが表示されます。 ビルドがクリーンになるまでこれらのエラーを解決します。  
  
7.  同じソリューションで UWP アプリの DLL を使用するには、UWP プロジェクト ノードのショートカット メニューを開き、**[追加]、[参照]** の順に選びます。  
  
     **[プロジェクト]、[ソリューション]** の順に選び、DLL プロジェクトの横にあるチェック ボックスをオンにして、**[OK]** ボタンを選びます。  
  
8.  UWP アプリの pch.h ファイルに、ライブラリのヘッダー ファイルを含めます。  
  
    ```  
    #include "..\MyNativeDLL\giraffe.h"  
    ```  
  
9. 通常通り UWP プロジェクトにコードを追加し、関数を呼び出して、DLL から型を生成します。  
  
    ```  
    MainPage::MainPage()  
    {  
        InitializeComponent();  
        GiraffeFactory gf;  
        Giraffe* g = gf.Create();  
        int id = g->GetID();  
    }  
  
    ```  
  
##  <a name="BK_StaticLib"></a> UWP アプリでネイティブ C++ スタティック ライブラリを使用する  
 UWP プロジェクトでネイティブ C++ スタティック ライブラリを使用することはできますが、理解しておくべき制約と制限があります。 C++/CX でのスタティック ライブラリについては、最初にこの[トピック](https://msdn.microsoft.com/library/hh771041.aspx)をご覧ください。 UWP アプリからスタティック ライブラリのネイティブ コードにアクセスすることはできますが、このようなスタティック ライブラリにパブリックな参照型を作成することは推奨されていません。 /ZW オプションを使用してスタティック ライブラリをコンパイルすると、ライブラリアン (実際にはリンカー) により次の警告が表示されます。  
  
```  
LNK4264: archiving object file compiled with /ZW into a static library; note that when authoring Windows Runtime types it is not recommended to link with a static library that contains Windows Runtime metadata  
```  
  
 ただし、/ZW を使用して再コンパイルするのでなければ、UWP でスタティック ライブラリを使用することができます。 参照型を宣言することや C++/CX コンストラクトを使用することはできませんが、単にネイティブ コードのライブラリを使用することが目的であれば、次の手順に従ってそうすることができます。  
  
#### <a name="to-use-a-native-c-static-library-in-a-uwp-project"></a>UWP プロジェクトでネイティブ C++ スタティック ライブラリを使用するには  
  
1.  UWP プロジェクトのプロジェクト プロパティの Linker セクションで、Input プロパティにライブラリへのパスを追加します。 たとえば、出力が *SolutionFolder*\Debug\MyNativeLibrary\MyNativeLibrary.lib に配置されているプロジェクトのライブラリの場合、相対パス `Debug\MyNativeLibrary\MyNativeLibrary.lib` を追加します。  
  
2.  ヘッダー ファイルを参照する include ステートメントを UWP プロジェクトの pch.h に追加し、そのライブラリを使用するコードの追加を開始します。  
  
    ```  
    #include "..\MyNativeLibrary\giraffe.h"  
    ```  
  
     **ソリューション エクスプローラー**の **[参照]** ノードには参照を追加しないでください。 このメカニズムは、Windows ランタイム コンポーネントの場合のみ機能します。  
  
##  <a name="BK_WinRTComponent"></a> C++ ライブラリをWindows ランタイム コンポーネントに移植する  
 UWP アプリからスタティック ライブラリのネイティブ API を使用する場合、そのネイティブ ライブラリのソース コードがあるなら、コードを Windows ランタイム コンポーネントに移植できます。 これはスタティック ライブラリではなく、DLL になります。 これは任意の C++ UWP アプリで使用できますが、スタティック ライブラリの場合とは異なり、言語に関係なく、任意の UWP アプリ コードでクライアントが使用できる参照型およびその他の C++/CX コンストラクトを追加することができます。 したがって、C#、Visual Basic、または JavaScript からこれらの型にアクセスできます。  基本的な手順として、Windows ランタイム コンポーネント プロジェクトを作成して、これにスタティック ライブラリのコードをコピーし、次いで、標準 C++ コンパイルから /ZW コンパイルにコードを移行したことに起因するエラーを解決します。  
  
#### <a name="to-port-a-c-library-to-a-windows-runtime-component"></a>C++ ライブラリを Windows ランタイム コンポーネントに移植するには  
  
1.  Windows ランタイム コンポーネント プロジェクトを作成します。  
  
2.  プロジェクトを閉じます。  
  
3.  Windows のエクスプ ローラーで、プロジェクトを見つけます。 既定で Visual Studio が使用するのは、ドキュメント フォルダー内の Visual Studio 2017\Projects フォルダーです。 移植するコードを含む C++ ライブラリ プロジェクトを見つけます。 C++ ライブラリ プロジェクトから、ソース ファイル (サブディレクトリ内のものも含めたヘッダー ファイル、コード ファイル、その他のすべてのリソース) をコピーし、プロジェクト フォルダーに貼り付けます。元と同じフォルダー構造になるように注意してください。  
  
4.  Windows ランタイム コンポーネント プロジェクトを開き直し、**ソリューション エクスプローラー**でプロジェクト ノードのショートカット メニューを開いて、**[追加]、[既存の項目]** の順に選びます。  
  
5.  元のプロジェクトから追加するすべてのファイルを選択し、[OK] を選択します。 サブフォルダーについても必要に応じてこの操作を繰り返します。  
  
6.  一部のコードが重複している可能性があります。 プリコンパイル済みヘッダーが複数ある場合 (たとえば stdafx.h と pch.h)、保持するものを 1 つ選択します。 include ステートメントなどの必要なコードはすべて、保持する方にコピーしておきます。 次に、プロジェクト プロパティの **[プリコンパイル済みヘッダー]** でもう一方を削除します。このとき、ヘッダー ファイルの名前が正しいことを確認してください。  
  
     プリコンパイル済みヘッダーとして使用するファイルを変更した場合、プリコンパイル済みヘッダー オプションが各ファイルに対して正しいことを確認します。 今度は各 .cpp ファイルを選び、そのプロパティ ウィンドウを開いて、**[作成する (/Yc)]** に設定されている目的のプリコンパイル済みヘッダー以外は、すべて **[使用する (/Yu)]** に設定されていることを確認します。  
  
7.  プロジェクトをビルドし、エラーを解決します。 これらのエラーは、/ZW オプションの使用や新しいバージョンの Windows SDK が原因で発生する場合があります。また、ライブラリが依存するヘッダー ファイルなどの依存関係や、古いプロジェクトと新しいプロジェクトの設定の違いが影響している場合もあります。  
  
8.  パブリックな参照型をプロジェクトに追加するか、通常の型を参照型に変換して、エントリ ポイントをUWP アプリから呼び出す機能に公開します。  
  
9. UWP アプリ プロジェクトからコンポーネントへの参照を追加してコンポーネントをテストし、作成したパブリック API を呼び出すコードを追加します。  
  
## <a name="see-also"></a>関連項目  
 [ユニバーサル Windows プラットフォームへの移植](../porting/porting-to-the-universal-windows-platform-cpp.md)
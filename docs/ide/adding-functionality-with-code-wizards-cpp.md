---
title: "コード ウィザードを使用した機能の追加 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス ウィザード [C++]"
  - "コード ウィザード [C++]"
  - "プロジェクト [C++], 追加 (機能を)"
  - "Visual C++ プロジェクト, 追加 (機能を)"
  - "ウィザード [C++], コード"
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コード ウィザードを使用した機能の追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロジェクトの作成後に、そのプロジェクトの機能を変更または追加する場合があります。  たとえば、新しいクラスを作成したり、新しいメンバー関数やメンバー変数を追加したり、オートメーション メソッドやオートメーション プロパティを追加したりします。  コード ウィザードは、これらの処理を実行できるようにデザインされています。  
  
> [!NOTE]
>  [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)を使用すると、メッセージ ハンドラーを追加し、そのハンドラーにメッセージを対応付けて MFC 仮想関数をオーバーライドできます。  
  
## Visual C\+\+ のコード ウィザードへのアクセス  
 Visual C\+\+ のコード ウィザードにアクセスするには、以下の 3 つの方法があります。  
  
-   \[プロジェクト\] メニューの **\[新しい項目の追加\]** をクリックすると、\[新しい項目の追加\] \(`Add New Item`\) ダイアログ ボックスが表示され、新しいファイルをプロジェクトに追加できます。  \[クラスの追加\] をクリックすると [&#91;クラスの追加&#93;](../ide/add-class-dialog-box.md) ダイアログ ボックスが表示され、プロジェクトに追加するクラスに応じたウィザードを起動できます。  **\[リソースの追加\]** をクリックすると [&#91;リソースの追加&#93;](../Topic/Add%20Resource%20Dialog%20Box.md) ダイアログ ボックスが表示され、プロジェクトに追加するリソースを作成または選択できます。  
  
     クラス ビューでプロジェクトのクラスまたはインターフェイスを強調表示すると、\[プロジェクト\] メニューに以下のコマンドも表示されます。  
  
    -   **インターフェイスの実装** \(コントロール クラスからのみ\)  
  
    -   **関数の追加**  
  
    -   **変数の追加**  
  
    -   接続ポイントの追加 \(ATL クラスのみ\)  
  
    -   メソッドの追加 \(インターフェイスからのみ\)  
  
    -   **プロパティの追加** \(インターフェイスからのみ\)  
  
    -   **イベントの追加** \(コントロール クラスからのみ\)  
  
-   **ソリューション エクスプローラー**で、いずれかのフォルダーを右クリックし、ショートカット メニューの \[追加\] をクリックすると、新規または既存のファイル、フォルダー、項目、クラス、リソース、および Web 参照をプロジェクトに追加できます。  
  
-   [&#91;クラス ビュー&#93; ウィンドウ](http://msdn.microsoft.com/ja-jp/8d7430a9-3e33-454c-a9e1-a85e3d2db925)で、適切なノードを右クリックし、ショートカット メニューの \[追加\] をクリックすると、関数、変数、クラス、プロパティ、メソッド、イベント、インターフェイス、コネクション ポイント、またはその他のコードをプロジェクトに追加できます。  
  
    > [!NOTE]
    >  Visual Studio には、プロジェクトにインターフェイスを追加するウィザードはありません。  [ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)を使用してシンプル オブジェクトを追加することで、ATL プロジェクトにインターフェイスを追加したり、[MFC プロジェクトに ATL サポートを追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)したりできます。  または、プロジェクトの .idl ファイルを開き、次のように入力してインターフェイスを作成します。  
  
    ```  
    interface IMyInterface {  
    };  
  
    ```  
  
     詳細については、「[インターフェイスの実装](../ide/implementing-an-interface-visual-cpp.md)」および「[ATL プロジェクトへのオブジェクトとコントロールの追加](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)」を参照してください。  
  
    |コード ウィザードへのアクセス元|Description|  
    |----------------------|-----------------|  
    |\[新しい項目の追加\]|新しい項目の追加コード ウィザードは、プロジェクトにソース ファイルを追加します。  必要に応じて、プロジェクト ビルド エンジンが使用するファイルが格納される追加のディレクトリを作成します。  \[項目の追加\] をクリックすると以下のコード ウィザードを使用できます。<br /><br /> -   C\+\+ ソース ファイル \(.cpp、.h、.idl、.rc、.srf、.def、.rgs\) の追加<br />-   Web 開発ファイル \(.html、.asp、.css、.xml\) の追加<br />-   ユーティリティ ファイルおよびリソース ファイル \(.bmp、.cur、.ico、.rct、.sql、.txt\) の追加<br /><br /> 通常、これらのコード ウィザードには情報の入力が不要ですが、ファイルが開発ツリーに追加されます。  ファイル名はプロパティ ウィンドウで変更できます。|  
    |ソリューション エクスプローラー|ソリューション エクスプローラーから使用できるコード ウィザードは、項目を右クリックしたときのポインターのフォーカスの位置によって異なります。  項目を右クリックしたときに \[追加\] オプションが表示されない場合は、ポインターを開発ツリーの 1 つ上のレベルに移動し、再度クリックしてください。  コード ウィザードは、ポインターの位置に関係なく、常に開発ツリーの適切な位置に追加コードを配置します。  ソリューション エクスプローラーから使用できるコード ウィザードは以下のとおりです。<br /><br /> -   クラスの追加 \(新しいコード ウィザードを含む \[クラスの追加\] ダイアログ ボックスを開きます\)<br />-   リソースの追加 \(新規作成、インポート、カスタム\)<br />-   Web 参照の追加|  
    |クラス ビュー|クラス ビューから使用できるコード ウィザードは、項目を右クリックしたときのポインターのフォーカスの位置によって異なります。  項目を右クリックしたときに \[追加\] オプションが表示されない場合は、ポインターをクラス ツリーの 1 つ上のレベルに移動し、再度クリックしてください。  コード ウィザードは、ポインターの位置に関係なく、常に開発ツリーの適切な位置に追加コードを配置します。  クラス ビューから使用できるコード ウィザードは以下のとおりです。<br /><br /> -   [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)<br />-   [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)<br />-   [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)<br />-   [インターフェイスの実装](../Topic/Implement%20Interface%20Wizard.md) \(コントロール クラスからのみ\)<br />-   [接続ポイントの追加](../ide/implement-connection-point-wizard.md) \(ATL クラスのみ\)<br />-   [メソッドの追加](../ide/add-method-wizard.md) \(インターフェイスからのみ\)<br />-   [プロパティの追加](../ide/names-add-property-wizard.md) \(インターフェイスからのみ\)<br />-   [イベントの追加](../ide/add-event-wizard.md) \(コントロール クラスからのみ\)<br /><br /> \[クラスの追加\] を選択すると \[クラスの追加\] ダイアログ ボックスが開き、すべての新しいクラスの追加コード ウィザードにアクセスできます。|  
  
## 参照  
 [仮想関数のオーバーライド](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [クラス各部へのジャンプ](../ide/navigating-the-class-structure-visual-cpp.md)   
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Visual C\+\+ プロジェクトの種類](../ide/visual-cpp-project-types.md)   
 [Visual C\+\+ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)
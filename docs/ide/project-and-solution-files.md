---
title: "プロジェクト ファイルとソリューション ファイル | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.files.projectandsolution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".sdf, 参照データベース ファイル"
  - "参照データベース ファイル, .sdf"
  - "ファイルの種類 [C++], メイクファイル"
  - "ファイルの種類 [C++], プロジェクト ファイル"
  - "メイクファイル プロジェクト"
  - "プロジェクト ファイル [C++]"
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# プロジェクト ファイルとソリューション ファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio でプロジェクトを作成すると、以下のファイルが作成されます。  これらのファイルは、ソリューション内のプロジェクト ファイルを管理するために使用されます。  
  
|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|  
|-----------|---------------|--------------------------|--------|  
|*Solname*.sln|*Projname*|ソリューション エクスプローラーでは非表示|*ソリューション* ファイル。  1 つまたは複数のプロジェクトのすべての要素を 1 つのソリューションにまとめます。|  
|*Projname*.suo|*Projname*|ソリューション エクスプローラーでは非表示|*ソリューション オプション* ファイル。  ソリューションのカスタマイズを格納します。これにより、ソリューション内のプロジェクトまたはファイルを開くたびに、指定した外観や動作が再現されます。|  
|*Projname*.vcxproj|*Projname*|ソリューション エクスプローラーでは非表示|*プロジェクト* ファイル。  各プロジェクトに固有の情報を格納します   \(以前のバージョンでは、このファイルは *Projname*.vcproj または *Projname*.dsp という名前でした\)。 Visual C\+\+ プロジェクト ファイルの例については、「[プロジェクト ファイル](../ide/project-files.md)」を参照してください。|  
|*Projname*.sdf|*Projname*|ソリューション エクスプローラーでは非表示|*参照データベース* ファイル。  **定義へ移動**、**すべての参照の検索**、**クラス ビュー**など、参照機能とナビゲーション機能をサポートします。  このファイルは、ヘッダー ファイルの解析によって生成されます。|  
|*Projname.*vcxproj.filters|*Projname*|ソリューション エクスプローラーでは非表示|*フィルター* ファイル。  ソリューションに追加されたファイルを配置する場所を指定します。  たとえば、.h ファイルは **ヘッダー ファイル** ノードに配置されます。|  
|*Projname.*vcxproj.user|*Projname*|ソリューション エクスプローラーでは非表示|*移行ユーザー* ファイル。  プロジェクトが Visual Studio 2008 から移行された後、このファイルには .vsprops ファイルから変換された情報が格納されます。|  
|*Projname*.idl|*Projname*|ソース|\(プロジェクトに固有\) コントロール タイプ ライブラリのインターフェイス記述言語 \(IDL\) ソース コードが含まれます。  このファイルは、Visual C\+\+ でタイプ ライブラリを生成するために使用されます。  生成されたライブラリは、他のオートメーション クライアントにコントロールのインターフェイスを公開します。  詳細については、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] の「[インターフェイス定義 \(IDL\) ファイル](http://msdn.microsoft.com/library/windows/desktop/aa378712)」を参照してください。|  
|Readme.txt|*Projname*|プロジェクト|*read me* ファイル。  アプリケーション ウィザードによって生成され、プロジェクト内のファイルについて記述します。|  
  
## 参照  
 [Visual C\+\+ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)
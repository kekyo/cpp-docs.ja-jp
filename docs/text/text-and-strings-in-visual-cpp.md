---
title: "Visual C++ のテキストと文字列 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ASCII 文字 [C++]"
  - "文字セット [C++]"
  - "文字セット [C++], 文字セットの概要"
  - "文字セット [C++], 非ヨーロッパ"
  - "グローバリゼーション [C++]"
  - "グローバリゼーション [C++], 文字セット"
  - "国際対応のアプリケーション [C++], 国際対応アプリケーションの概要"
  - "日本語の文字 [C++]"
  - "漢字のサポート [C++]"
  - "ローカル文字セット [C++]"
  - "ローカリゼーション [C++]"
  - "ローカリゼーション [C++], 文字セット"
  - "MBCS [C++], 国際対応のプログラミング"
  - "複数言語のサポート [C++]"
  - "非ヨーロッパ文字 [C++]"
  - "移植性 [C++]"
  - "移植性 [C++], 文字セット"
  - "プログラミング [C++], 国際対応"
  - "変換 (コードを) [C++]"
  - "変換 [C++], 文字セット"
  - "Unicode [C++]"
ms.assetid: a1bb27ac-abe5-4c6b-867d-f761d4b93205
caps.latest.revision: 12
caps.handback.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Visual C++ のテキストと文字列
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

国際市場をターゲットにアプリケーションを開発する場合は、地域の文字セットをサポートすることが重要です。  ASCII 文字セットでは、0x00 から 0x7F までの範囲の文字を定義しています。  そのほかに、ASCII 文字セットと同じ 0x00 から 0x7F までの範囲の文字に加え、0x80 から 0xFF までの拡張文字セットも定義している、主にヨーロッパ向けの文字セットもあります。  多くのヨーロッパ系言語の文字と ASCII 文字セットを表現するには、8 ビットの 1 バイト文字セット \(SBCS: Single\-Byte\-Character Set\) で十分です。  ただし、日本語の漢字など、ヨーロッパ以外の文字セットでは、1 バイトのコード体系ですべての文字を表現しきれないため、マルチバイト文字セット \(MBCS: Multibyte\-Character Set\) エンコーディングが必要になります。  
  
## このセクションの内容  
 [Unicode と MBCS](../text/unicode-and-mbcs.md)  
 Visual C\+\+ でサポートする Unicode プログラミングと MBCS プログラミングについて説明します。  
  
 [Unicode のサポート](../text/support-for-unicode.md)  
 1 バイト文字では表現できない文字セットを含むあらゆる文字セットをサポートする Unicode について説明します。  
  
 [マルチバイト文字セット \(MBCS\) のサポート](../text/support-for-multibyte-character-sets-mbcss.md)  
 Unicode の代わりとして、日本語や中国語など、1 バイト文字では表現できない文字セットをサポートする MBCS について説明します。  
  
 [Tchar.h における汎用テキストのマッピング](../Topic/Generic-Text%20Mappings%20in%20Tchar.h.md)  
 多くのデータ型、ルーチン、およびその他のオブジェクトに対する、Microsoft 固有の汎用テキストのマッピングについて説明します。  
  
 [方法: さまざまな文字列型間で変換する](../Topic/How%20to:%20Convert%20Between%20Various%20String%20Types.md)  
 さまざまな Visual C\+\+ 文字列型を他の文字列に変換する方法について説明します。  
  
## 関連項目  
 [国際化](../c-runtime-library/internationalization.md)  
 C ランタイム ライブラリの国際対応のサポートについて説明します。  
  
 [国際化対応のサンプル](http://msdn.microsoft.com/ja-jp/aa8d390c-cf4c-4dd8-9dea-74d81f93f2f8)  
 Visual C\+\+ の国際化のアプローチを示すサンプルへのリンクを提供します。  
  
 [言語および国\/地域識別文字列](../c-runtime-library/locale-names-languages-and-country-region-strings.md)  
 C ランタイム ライブラリの言語および国\/地域識別文字列について説明します。
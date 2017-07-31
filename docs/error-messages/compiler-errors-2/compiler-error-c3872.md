---
title: "コンパイラ エラー C3872 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3872"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3872"
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# コンパイラ エラー C3872
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'char': この文字を識別子で使用することはできません  
  
 C\+\+ コンパイラは、識別子で許可される文字に関する C\+\+11 標準に従います。 識別子では、特定の範囲の文字とユニバーサル文字名しか使用できません。 識別子の最初の文字に追加の制限が適用されます。 許可される文字の一覧とユニバーサル文字名の範囲については、「[C\+\+ 識別子](../../cpp/identifiers-cpp.md)」を参照してください。  
  
 識別子で許可される文字の範囲は、C\+\+\/CLI コードをコンパイルする場合よりも制限が厳しくありません。 \/clr を使用してコンパイルするコード内の識別子は、[標準 ECMA 335: 共通言語基盤 \(CLI\)](http://www.ecma-international.org/publications/standards/Ecma-335.htm) に従う必要があります。  
  
 次の例では警告 C3872 が生成されます。  
  
```  
// C3872.cpp int main() { int abc_\u0040;   // C3872, U+0040 is in base char set int abc_\u3001;   // C3872, U+3001 is not in allowed range int \u30A2_abc_\u3042;   // OK, UCNs in allowed range }  
```
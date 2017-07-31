---
title: "C コマンド ライン引数の解析 | Microsoft Docs"
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
  - "コマンド ライン, 解析"
  - "二重引用符"
  - "解析, コマンド ライン引数"
  - "引用符, コマンド ライン引数"
  - "スタートアップ コード, 解析 (コマンド ライン引数を)"
ms.assetid: ffce8037-2811-45c4-8db4-1ed787859c80
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# C コマンド ライン引数の解析
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 Microsoft C スタートアップ コードは、オペレーティング システムのコマンド ラインで指定された引数を解釈する場合に、次の規則を使用します。  
  
-   引数は、空白 \(スペースまたはタブ\) で区切ります。  
  
-   二重引用符で囲まれた文字列は、空白を含む場合でも、単一の引数と見なされます。  二重引用符で囲んだ文字列を引数に埋め込むこともできます。  キャレット \(**^**\) は、エスケープ文字や区切り記号としては認識されません。  
  
-   円記号を前に付けた二重引用符 \(**\\"**\) は、リテラル二重引用符文字 \(**"**\) として解釈されます。  
  
-   二重引用符の直前にある円記号以外は、円記号 \(\\\) として解釈されます。  
  
-   二重引用符の直前に円記号が偶数個あると、円記号のペア \(**\\\\**\) ごとに 1 個の円記号 \(**\\**\) が `argv` 配列に配置されます。この場合、二重引用符 \(**"**\) は文字列の区切り記号として解釈されます。  
  
-   二重引用符の直前に円記号が奇数個 \(3 個以上\) あると、円記号のペア \(**\\\\**\) ごとに 1 個の円記号 \(**\\**\) が `argv` 配列に格納されます。この場合、二重引用符は残った円記号によりエスケープ シーケンスと見なされます。これにより、リテラル二重引用符 \(**"**\) が `argv` に追加されます。  
  
 この一覧では、コマンド ライン引数のいくつかの例で `argv` に渡される解釈された結果を示して、上記の規則について説明しています。  2 番目、3 番目、および 4 番目の列に表示される出力は、一覧に続く ARGS.C のプログラムからのものです。  
  
|コマンド ライン入力|argv\[1\]|argv\[2\]|argv\[3\]|  
|----------------|---------------|---------------|---------------|  
|`"a b c" d e`|`a b c`|`d`|`e`|  
|`"ab\"c" "\\" d`|`ab"c`|`\`|`d`|  
|`a\\\b d"e f"g h`|`a\\\b`|`de fg`|`h`|  
|`a\\\"b c d`|`a\"b`|`c`|`d`|  
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|  
  
## 例  
  
### コード  
  
```  
// Parsing_C_Commandline_args.c  
// ARGS.C illustrates the following variables used for accessing  
// command-line arguments and environment variables:  
// argc  argv  envp  
//  
  
#include <stdio.h>  
  
int main( int argc, // Number of strings in array argv  
 char *argv[],      // Array of command-line argument strings  
 char **envp )      // Array of environment variable strings  
{  
    int count;  
  
    // Display each command-line argument.  
    printf_s( "\nCommand-line arguments:\n" );  
    for( count = 0; count < argc; count++ )  
        printf_s( "  argv[%d]   %s\n", count, argv[count] );  
  
    // Display each environment variable.  
    printf_s( "\nEnvironment variables:\n" );  
    while( *envp != NULL )  
        printf_s( "  %s\n", *(envp++) );  
  
    return;  
}  
```  
  
## コメント  
 このプログラムからの出力の例は次のとおりです。  
  
```  
Command-line arguments:  
  argv[0]   C:\MSC\TEST.EXE  
  
Environment variables:  
  COMSPEC=C:\NT\SYSTEM32\CMD.EXE  
  
  PATH=c:\nt;c:\binb;c:\binr;c:\nt\system32;c:\word;c:\help;c:\msc;c:\;  
  PROMPT=[$p]   
  TEMP=c:\tmp  
  TMP=c:\tmp  
  EDITORS=c:\binr  
  WINDIR=c:\nt        
```  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [main 関数とプログラム実行](../c-language/main-function-and-program-execution.md)
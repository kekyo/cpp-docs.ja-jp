---
title: "compl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "compl"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "std::compl"
  - "std.compl"
  - "compl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compl 関数"
ms.assetid: e03f6fb5-cb8b-4afa-99c0-905f4105fb34
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# compl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

~ 演算子の代替手段。  
  
## 構文  
  
```  
  
#define compl ~  
  
```  
  
## 解説  
 マクロにより ~ 演算子が生成されます。  
  
## 使用例  
  
```  
// iso646_compl.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   int a = 1, result;  
  
   result = ~a;  
   cout << result << endl;  
  
   result= compl(a);  
   cout << result << endl;  
}  
```  
  
  **\-2**  
**\-2**   
## 必要条件  
 **ヘッダー:** \<iso646.h\>
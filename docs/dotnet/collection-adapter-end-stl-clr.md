---
title: "collection_adapter::end (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::collection_adapter::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "end メンバー [STL/CLR]"
ms.assetid: f953a734-2f17-4b68-9ca4-34f980d08887
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# collection_adapter::end (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

被制御シーケンスの末尾を指定します。  
  
## 構文  
  
```  
iterator end();  
```  
  
## 解説  
 このメンバー関数は、入力反復子を被制御シーケンスの末尾を指し示す前方反復子を返します。  
  
## 使用例  
  
```  
// cliext_collection_adapter_end.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**   
## 必要条件  
 **ヘッダー:** の \<cliext\/アダプター\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [collection\_adapter](../Topic/collection_adapter%20\(STL-CLR\).md)   
 [collection\_adapter::begin](../dotnet/collection-adapter-begin-stl-clr.md)
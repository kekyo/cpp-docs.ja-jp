---
title: "hash_set::size_type (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::size_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size_type メンバー [STL/CLR]"
ms.assetid: 700ce851-d081-4887-a855-8d98d2eadb81
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# hash_set::size_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 要素間の符号付きな間隔の種類。  
  
## 構文  
  
```  
typedef int size_type;  
```  
  
## 解説  
 型は負の要素数を指定します。  
  
## 使用例  
  
```  
// cliext_hash_set_size_type.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Myhash_set::size_type diff = 0;   
    for (Myhash_set::iterator it = c1.begin(); it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
  **b c**  
**end\(\)\- \(\) \= 3 を開始します。**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_set\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::empty](../dotnet/hash-set-empty-stl-clr.md)
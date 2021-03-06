---
title: "set::key_type (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::key_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "key_type メンバー [STL/CLR]"
ms.assetid: 2c057cf7-ac3d-40a6-b7fc-eb1c0a317381
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# set::key_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

順序付けキーの型です。  
  
## 構文  
  
```  
typedef Key key_type;  
```  
  
## 解説  
 この型は、テンプレート パラメーター `Key` のシノニムです。  
  
## 使用例  
  
```  
// cliext_set_key_type.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" using key_type   
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in key_type object   
        Myset::key_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**   
## 必要条件  
 **ヘッダー:** \<cliext および設定\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [設定](../dotnet/set-stl-clr.md)   
 [set::key\_compare](../dotnet/set-key-compare-stl-clr.md)   
 [set::value\_type](../dotnet/set-value-type-stl-clr.md)
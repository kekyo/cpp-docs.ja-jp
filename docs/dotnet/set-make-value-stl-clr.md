---
title: "set::make_value (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::make_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_value メンバー [STL/CLR]"
ms.assetid: 2f71515e-7de1-4139-a68e-72ff2a96aa4a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# set::make_value (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

値オブジェクトを構築します。  
  
## 構文  
  
```  
static value_type make_value(key_type key);  
```  
  
#### パラメーター  
 key  
 使用するキー値。  
  
## 解説  
 このメンバー関数は、キーが `key`である `value_type` オブジェクトを返します。  他のメンバー関数の使用に適したオブジェクトを構成するために使用します。  
  
## 使用例  
  
```  
// cliext_set_make_value.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(Myset::make_value(L'a'));   
    c1.insert(Myset::make_value(L'b'));   
    c1.insert(Myset::make_value(L'c'));   
  
// display contents " a b c"   
    for each (Myset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
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
 [set::key\_type](../dotnet/set-key-type-stl-clr.md)   
 [set::value\_type](../dotnet/set-value-type-stl-clr.md)
---
title: "map::difference_type (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::difference_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "difference_type メンバー [STL/CLR]"
ms.assetid: 22c80391-f97b-4ac4-9e2d-7f4caa2c5ac8
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# map::difference_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 個の要素間の符号付きな間隔の種類。  
  
## 構文  
  
```  
typedef int difference_type;  
```  
  
## 解説  
 型は、負のな要素数を表します。  
  
## 使用例  
  
```  
// cliext_map_difference_type.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Mymap::difference_type diff = 0;   
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (Mymap::iterator it = c1.end(); it != c1.begin(); --it)   
        --diff;   
    System::Console::WriteLine("begin()-end() = {0}", diff);   
    return (0);   
    }  
  
```  
  
  **1 \[\] \[b 2 \[\]c 3\]**  
**end\(\)\- \(\) \= 3 を開始します。**  
**begin\(\)\- end \(\) \= \-3**   
## 必要条件  
 **ヘッダー:** の \<cliext\/マップ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [マップ](../dotnet/map-stl-clr.md)   
 [map::size\_type](../dotnet/map-size-type-stl-clr.md)
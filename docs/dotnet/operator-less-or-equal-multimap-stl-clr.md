---
title: "operator&lt;= (multimap) (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::operator<="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator<= メンバー [STL/CLR]"
ms.assetid: f23cdacd-fb1b-4e87-8e32-497226841871
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&lt;= (multimap) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リストの大小関係 \(以下\) を比較します。  
  
## 構文  
  
```  
template<typename Key,  
    typename Mapped>  
    bool operator<=(multimap<Key, Mapped>% left,  
        multimap<Key, Mapped>% right);  
```  
  
#### パラメーター  
 \[left\]  
 比較の左辺のコンテナー。  
  
 \[right\]  
 比較の右辺のコンテナー。  
  
## 解説  
 演算子関数の戻り値 `!(``right``<``left``)`。  2 個の multimaps が要素によって比較された要素の場合 `left` が `right` の後に順序されていないかどうかをテストするときに使用します。  
  
## 使用例  
  
```  
// cliext_multimap_operator_le.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultimap c2;   
    c2.insert(Mymultimap::make_value(L'a', 1));   
    c2.insert(Mymultimap::make_value(L'b', 2));   
    c2.insert(Mymultimap::make_value(L'd', 4));   
  
// display contents " [a 1] [b 2] [d 4]"   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] <= [a b c] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
  **1 \[\] \[b 2 \[\]c 3\]**  
 **1 \[\] \[b 2 \[\]d 4\]**  
**\[\] \<b c \= b c \[\]当てはまります。**  
**\[b \= b c d\] \<\[\] false です。**   
## 必要条件  
 **ヘッダー:** の \<cliext\/マップ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [operator\=\= \(multimap\)](../dotnet/operator-equality-multimap-stl-lr.md)   
 [operator\!\= \(multimap\)](../Topic/operator!=%20\(multimap\)%20\(STL-CLR\).md)   
 [operator\< \(multimap\)](../dotnet/operator-less-than-multimap-stl-clr.md)   
 [operator\>\= \(multimap\)](../Topic/operator%3E=%20\(multimap\)%20\(STL-CLR\).md)   
 [operator\> \(multimap\)](../dotnet/operator-greater-than-multimap-stl-clr.md)
---
title: "hash_multimap::bucket_count (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::bucket_count"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bucket_count メンバー [STL/CLR]"
ms.assetid: 63b7e08e-16fb-42e5-b592-d1fd29c47637
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# hash_multimap::bucket_count (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

バケット数をカウントします。  
  
## 構文  
  
```  
int bucket_count();  
```  
  
## 解説  
 このメンバー関数は、現在のバケット数を返します。  ハッシュ テーブルのサイズを決定するために使用します。  
  
## 使用例  
  
```  
// cliext_hash_multimap_bucket_count.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1 = gcnew Myhash_multimap;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect current parameters   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    System::Console::WriteLine();   
  
// change max_load_factor and redisplay   
    c1.max_load_factor(0.25f);   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    System::Console::WriteLine();   
  
// rehash and redisplay   
    c1.rehash(100);   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    return (0);   
    }  
  
```  
  
  **1 \[\] \[b 2 \[\]c 3\]**  
**bucket\_count\(\) \= 16**  
**load\_factor\(\) \= 0.1875**  
**max\_load\_factor\(\) \= 4**  
**bucket\_count\(\) \= 16**  
**load\_factor\(\) \= 0.1875**  
**max\_load\_factor\(\) \= 0.25**  
**bucket\_count\(\) \= 128**  
**load\_factor\(\) \= 0.0234375**  
**max\_load\_factor\(\) \= 0.25**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_map\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::load\_factor](../dotnet/hash-multimap-load-factor-stl-clr.md)   
 [hash\_multimap::max\_load\_factor](../Topic/hash_multimap::max_load_factor%20\(STL-CLR\).md)
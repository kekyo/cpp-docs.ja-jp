---
title: "hash_set::to_array (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_set::to_array
dev_langs: C++
helpviewer_keywords: to_array member [STL/CLR]
ms.assetid: 2aa61f13-85b8-4aa4-91b4-69ddcc5064dc
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 13af64f7d5ae9ee71fc3ab5c2f8e64a11492e034
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="hashsettoarray-stlclr"></a>hash_set::to_array (STL/CLR)
被制御シーケンスを新しい配列にコピーします。  
  
## <a name="syntax"></a>構文  
  
```  
cli::array<value_type>^ to_array();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数では、被制御シーケンスを格納する配列を返します。 使用する配列形式の被制御シーケンスのコピーを入手します。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_set_to_array.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.insert(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c d  
a b c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)
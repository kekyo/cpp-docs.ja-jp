---
title: "vector::front (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::front
dev_langs: C++
helpviewer_keywords: front member [STL/CLR]
ms.assetid: 37a36157-8220-4d5b-85b5-c6a63211a322
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e9b82e3088585000dc97755eff9dd760134b579a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="vectorfront-stlclr"></a>vector::front (STL/CLR)
最初の要素にアクセスします。  
  
## <a name="syntax"></a>構文  
  
```  
reference front();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数では、空でない必要があります、被制御シーケンスの最初の要素への参照を返します。 これを使用するには存在することがわかっている場合に、最初の要素を読み書きします。  
  
## <a name="example"></a>例  
  
```  
// cliext_vector_front.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front() = {0}", c1.front());   
  
// alter first item and reinspect   
    c1.front() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
front() = a  
 x b c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/vector >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [ベクトル (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::back (STL/CLR)](../dotnet/vector-back-stl-clr.md)   
 [vector::back_item (STL/CLR)](../dotnet/vector-back-item-stl-clr.md)   
 [vector::front_item (STL/CLR)](../dotnet/vector-front-item-stl-clr.md)
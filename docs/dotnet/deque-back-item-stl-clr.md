---
title: "deque::back_item (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::deque::back_item
dev_langs: C++
helpviewer_keywords: back_item member [STL/CLR]
ms.assetid: b112636a-2f18-4eb0-abd6-076acdabeff7
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d20a8ffdfa84c56c4716df31a8f4c3951566cead
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="dequebackitem-stlclr"></a>deque::back_item (STL/CLR)
最後の要素にアクセスします。  
  
## <a name="syntax"></a>構文  
  
```  
property value_type back_item;  
```  
  
## <a name="remarks"></a>コメント  
 プロパティでは、空でない必要があります、被制御シーケンスの最後の要素にアクセスします。 これを使用するには存在することがわかっている場合に、最後の要素を読み書きします。  
  
## <a name="example"></a>例  
  
```  
// cliext_deque_back_item.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back_item = {0}", c1.back_item);   
  
// alter last item and reinspect   
    c1.back_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back_item = c  
 a b x  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::back (STL/CLR)](../dotnet/deque-back-stl-clr.md)   
 [deque::front (STL/CLR)](../dotnet/deque-front-stl-clr.md)   
 [deque::front_item (STL/CLR)](../dotnet/deque-front-item-stl-clr.md)
---
title: "queue::pop (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::queue::pop
dev_langs: C++
helpviewer_keywords: pop member [STL/CLR]
ms.assetid: 38f6c03b-e8f8-4663-b3d6-18314cdc8e7d
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: de17790b127ad62c35db835c9555e7c410764812
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="queuepop-stlclr"></a>queue::pop (STL/CLR)
最後の要素を削除します。  
  
## <a name="syntax"></a>構文  
  
```  
void pop();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、空でない必要があります、被制御シーケンスの最後の要素を削除します。 使用するバックに 1 つの要素によって、キューを短くします。  
  
## <a name="example"></a>例  
  
```  
// cliext_queue_pop.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop();   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
b c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/キュー >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [キュー (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::push (STL/CLR)](../dotnet/queue-push-stl-clr.md)
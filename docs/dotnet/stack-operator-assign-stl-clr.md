---
title: "stack::operator= (STL/CLR) | Microsoft Docs"
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
  - "cliext::stack::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= メンバー [STL/CLR]"
ms.assetid: 6f23b5fc-667e-4c6c-b43a-88b30da2ecac
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# stack::operator= (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

被制御シーケンスを置き換えます。  
  
## 構文  
  
```  
stack <Value, Container>% operator=(stack <Value, Container>% right);  
```  
  
#### パラメーター  
 \[right\]  
 コピーするコンテナーのアダプター。  
  
## 解説  
 このメンバー演算子は、オブジェクトに `right` を返します `*this`をコピーします。  これを使用して、被制御シーケンスを `right` の被制御シーケンスのコピーに置き換えることができます。  
  
## 使用例  
  
```  
// cliext_stack_operator_as.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
    c2 = c1;   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
 **b c**   
## 必要条件  
 **ヘッダー:** \<cliext とスタック\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [スタック](../dotnet/stack-stl-clr.md)   
 [stack::assign](../Topic/stack::assign%20\(STL-CLR\).md)
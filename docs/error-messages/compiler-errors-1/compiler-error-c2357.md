---
title: "コンパイラ エラー C2357 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2357
dev_langs:
- C++
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b3804f0ee55284aabcd46b0f45c557ccc79cbb8a
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2357"></a>コンパイラ エラー C2357
'identifier': 'type' 型の関数である必要があります  
  
 コードの宣言のバージョンが、`atexit`コンパイラによって内部的に宣言された関数のバージョンに一致しません。 宣言`atexit`次のようにします。  
  
```  
int __cdecl atexit(void (__cdecl *)());  
```  
  
 詳細については、次を参照してください。 [init_seg](../../preprocessor/init-seg.md)です。  
  
 次の例では、C2357 が生成されます。  
  
```  
// C2357.cpp  
// compile with: /c  
// C2357 expected  
#pragma warning(disable : 4075)  
// Uncomment the following line to resolve.  
// int __cdecl myexit(void (__cdecl *)());  
#pragma init_seg(".mine$m",myexit)  
```

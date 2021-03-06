---
title: "auto_gcroot:: ~ auto_gcroot |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- auto_gcroot::~auto_gcroot
- ~auto_gcroot
- auto_gcroot.~auto_gcroot
- msclr::auto_gcroot::~auto_gcroot
- msclr.auto_gcroot.~auto_gcroot
dev_langs: C++
helpviewer_keywords: auto_gcroot::~auto_gcroot
ms.assetid: 3c970d43-0cb1-4b27-8bee-0394d91b4739
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 46326050e25e62ab05eae44a3c96dbd82fa75e35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="autogcrootautogcroot"></a>auto_gcroot::~auto_gcroot
`auto_gcroot`デストラクターです。  
  
## <a name="syntax"></a>構文  
  
```  
~auto_gcroot();  
```  
  
## <a name="remarks"></a>コメント  
 また、デストラクターは、所有されているオブジェクトを破棄します。  
  
## <a name="example"></a>例  
  
```  
// msl_auto_gcroot_dtor.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
public:  
   ClassA() { Console::WriteLine( "ClassA constructor" ); }  
   ~ClassA() { Console::WriteLine( "ClassA destructor" ); }  
};  
  
int main()  
{  
   // create a new scope for a:  
   {  
      auto_gcroot<ClassA^> a = gcnew ClassA;  
   }  
   // a goes out of scope here, invoking its destructor  
   // which in turns destructs the ClassA object.  
  
   Console::WriteLine( "done" );  
}  
```  
  
```Output  
ClassA constructor  
ClassA destructor  
done  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー ファイル** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>関連項目  
 [auto_gcroot メンバー](../dotnet/auto-gcroot-members.md)   
 [auto_gcroot::release](../dotnet/auto-gcroot-release.md)   
 [auto_gcroot::auto_gcroot](../dotnet/auto-gcroot-auto-gcroot.md)
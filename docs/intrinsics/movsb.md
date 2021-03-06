---
title: "_ _movsb |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __movsb
dev_langs: C++
helpviewer_keywords:
- movsb instruction
- rep movsb instruction
- __movsb intrinsic
ms.assetid: ba5469f6-f797-4cd2-bee8-74c7666c26d4
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d5ed046555b102c77b8213fc8755220d1f2d0777
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="movsb"></a>__movsb
**Microsoft 固有の仕様**  
  
 移動の文字列を生成します (`rep movsb`) 命令します。  
  
## <a name="syntax"></a>構文  
  
```  
void __movsb(   
   unsigned char* Destination,   
   unsigned const char* Source,   
   size_t Count   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `Destination`  
 コピー先へのポインター。  
  
 [入力] `Source`  
 コピーのソースへのポインター。  
  
 [入力] `Count`  
 コピーするバイト数。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__movsb`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 結果を最初`Count`バイトを指す`Source`にコピーされます、`Destination`文字列。  
  
 このルーチンは、組み込みとしてのみ使用できます。  
  
## <a name="example"></a>例  
  
```  
// movsb.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__movsb)  
  
int main()  
{  
    unsigned char s1[100];  
    unsigned char s2[100] = "A big black dog.";  
    __movsb(s1, s2, 100);  
  
    printf_s("%s %s", s1, s2);  
}  
```  
  
```Output  
A big black dog. A big black dog.  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
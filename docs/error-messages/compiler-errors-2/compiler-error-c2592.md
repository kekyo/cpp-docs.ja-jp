---
title: "コンパイラ エラー C2592 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2592
dev_langs:
- C++
helpviewer_keywords:
- C2592
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7f5d1ba0dec5b555f50c9fd6848e2d5a38020fff
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2592"></a>コンパイラ エラー C2592
'class': 'base_class_2' は、'base_class_1' から継承されるので、再指定することはできません  
  
 他の基底クラスから継承していない基底クラスのみを指定できます。 この場合は、`base_class_1` が既に `base_class_2` を継承しているため、`class` の指定で必要になるのは `base_class_1` のみです。
---
title: "IUnknown |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IUnknown
dev_langs: C++
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f750cea17029a76f56edaa3dc6531554fa81901a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="iunknown"></a>IUnknown
[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)は、その他のすべての COM インターフェイスの基本インターフェイスです。  このインターフェイスは、3 つのメソッドを定義します。 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)、 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、および[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)です。 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)ユーザーは、使用インターフェイスに別のインターフェイスへのポインターのオブジェクトを確認してください。 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)と[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)インターフェイスの参照カウントを実装します。  
  
## <a name="see-also"></a>関連項目  
 [COM の概要](../atl/introduction-to-com.md)   
 [IUnknown とインターフェイスの継承](http://msdn.microsoft.com/library/windows/desktop/ms692713)


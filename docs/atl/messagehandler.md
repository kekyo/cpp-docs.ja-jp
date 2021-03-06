---
title: "メッセージ ハンドラ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MessageHandler
dev_langs: C++
helpviewer_keywords: MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd6828f5c6b4f89b7d939e4fd909e72e3039b69f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="messagehandler"></a>メッセージ ハンドラ
**メッセージ ハンドラ**の 2 番目のパラメーターで識別される関数の名前を指定、`MESSAGE_HANDLER`メッセージ マップ マクロです。  
  
## <a name="syntax"></a>構文  
  
```  
 
    LRESULT 
    MessageHandler 
 (
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>パラメーター  
 `uMsg`  
 メッセージを指定します。  
  
 `wParam`  
 その他のメッセージに固有の情報です。  
  
 `lParam`  
 その他のメッセージに固有の情報です。  
  
 `bHandled`  
 メッセージ マップ セット`bHandled`に**TRUE**する前に`MessageHandler`と呼びます。 場合`MessageHandler`、メッセージを完全に処理しませんに設定する必要があります`bHandled`に**FALSE**を示すメッセージがさらに処理を必要があります。  
  
## <a name="return-value"></a>戻り値  
 メッセージの処理の結果。 正常終了した場合は 0 を返します。  
  
## <a name="remarks"></a>コメント  
 メッセージ マップでこのメッセージ ハンドラーを使用しての例は、次を参照してください。 [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler)です。  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウの実装](../atl/implementing-a-window.md)   
 [メッセージ マップ](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)


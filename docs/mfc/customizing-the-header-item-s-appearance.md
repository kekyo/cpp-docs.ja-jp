---
title: "ヘッダー項目 &#39; のカスタマイズ s 外観 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 494372aa3e6dcc418a6ffdacbb7b06635a010310
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="customizing-the-header-item39s-appearance"></a>ヘッダー項目 &#39; のカスタマイズの外観
設定して、 *dwStyle*パラメーター最初をヘッダー コントロールを作成するとき ([CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create)) 外観を定義することができます、およびヘッダーの動作の項目またはヘッダーの自体を制御します。  
  
 スタイルを設定して、目的のサンプリングを次に示します。  
  
-   プッシュ ボタンのようになりますヘッダー項目を使用して、`HDS_BUTTONS`スタイル。  
  
     Microsoft Outlook で行われるように、特定の列でデータの並べ替えなど、ヘッダー項目のマウス クリックに応答するアクションを実行する場合は、このスタイルを使用します。  
  
-   ヘッダー項目の外観「ホット トラッキング」にマウス カーソルを使用して、`HDS_HOTTRACK`スタイル。  
  
     ホット トラッキング マウス ポインターがそれ以外の場合フラット内の項目 3 D のアウトラインを表示バー。  
  
-   ヘッダー コントロールを非表示にすることを示すために使用して、`HDS_HIDDEN`スタイル。  
  
     `HDS_HIDDEN`スタイルは、ヘッダー コントロールがデータのコンテナーとコントロールのビジュアルではなくとして使用するものであることを示します。 このスタイルは、コントロールが自動的に非表示されませんが、代わりの動作に影響`CHeaderCtrl::Layout`です。 戻り値、 **cy**のメンバー、`WINDOWPOS`構造体は 0 になりますをコントロールは、ユーザーに表示できないする必要があります。  
  
 これらのプロパティの詳細については、次を参照してください。[項目](http://msdn.microsoft.com/library/windows/desktop/bb775238)Windows SDK に含まれています。 ヘッダー コントロールに項目を追加する方法の詳細については、次を参照してください。[ヘッダー コントロールへの項目の追加](../mfc/adding-items-to-the-header-control.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)


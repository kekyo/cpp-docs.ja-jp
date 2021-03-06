---
title: "リスト コントロールの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dd187bf945e2bcf018575db8d45e4d653c5b869b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="creating-the-list-control"></a>リスト コントロールの作成
一覧を制御する方法 ([CListCtrl](../mfc/reference/clistctrl-class.md)) が作成されるクラスを使用してまたはコントロールを直接使用するしているかどうかによって異なります[CListView](../mfc/reference/clistview-class.md)代わりにします。 使用する場合`CListView`フレームワークは、そのドキュメント/ビューの作成のシーケンスの一部として、ビューを構築します。 リスト ビューを作成するには、リスト コントロールにも (この 2 つは同じもの) が作成されます。 ビューので、コントロールが作成された[OnCreate](../mfc/reference/cwnd-class.md#oncreate)ハンドラー関数。 この場合、コントロールが呼び出しを使用して、項目を追加するための準備ができて[GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl)です。  
  
### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>ダイアログ ボックスで直接 CListCtrl を使用するには  
  
1.  ダイアログ エディターでダイアログ テンプレート リソース リスト コントロールを追加します。 そのコントロールの ID を指定します  
  
2.  使用して、[メンバー変数の追加ウィザード](../ide/adding-a-member-variable-visual-cpp.md)型のメンバー変数を追加する`CListCtrl`コントロールのプロパティにします。 このメンバーを使用するを呼び出すと`CListCtrl`メンバー関数。  
  
3.  使用するリスト コントロールの通知メッセージのダイアログ クラスのハンドラー関数にマップする [プロパティ] ウィンドウを処理する必要があります (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。  
  
4.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)のスタイルを設定、`CListCtrl`です。 参照してください[リスト コントロール スタイルの変更](../mfc/changing-list-control-styles.md)です。 これにより、ビューを後で変更できますが、コントロールでは、取得する"view"の種類が決まります。  
  
### <a name="to-use-clistctrl-in-a-nondialog-window"></a>以外のウィンドウで CListCtrl を使用するには  
  
1.  ビューまたはウィンドウのクラスでは、コントロールを定義します。  
  
2.  コントロールの呼び出します[作成](../mfc/reference/clistctrl-class.md#create)メンバー関数は、可能性のあるで[フィルターと並べ替え順序](../mfc/reference/cview-class.md#oninitialupdate)、親ウィンドウの可能性がありますの早期[OnCreate](../mfc/reference/cwnd-class.md#oncreate)ハンドラー関数 (ユーザー場合サブクラス化コントロール)。 コントロールのスタイルを設定します。  
  
## <a name="see-also"></a>関連項目  
 [CListCtrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)


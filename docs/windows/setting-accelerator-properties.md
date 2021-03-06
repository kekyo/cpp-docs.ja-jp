---
title: "アクセラレータのプロパティを設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d8a83b155b5e0a350d5c578a8dccfb9040cec3df
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="setting-accelerator-properties"></a>アクセラレータのプロパティの設定
アクセラレータのプロパティを設定することができます、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)いつでもできます。 また、アクセラレータ エディターを使用して、アクセラレータ テーブルでアクセラレータのプロパティを変更することもできます。 プロパティ ウィンドウを使用しても、アクセラレータ エディターを使用しても、変更の結果は同じです。編集はすぐにアクセラレータ テーブルに反映されます。  
  
 各アクセラレータの 3 つのプロパティがある[ID](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160/locales/en-US):  
  
-   [修飾子プロパティ](../windows/accelerator-modifier-property.md)コントロール、アクセラレータ キーの組み合わせを設定します。  
  
    > [!NOTE]
    >  プロパティ ウィンドウでは、このプロパティは 3 つの独立したブール型プロパティ (Alt、Ctrl、Shift) として表示され、すべて個別に制御できます。  
  
-   [キー プロパティ](../windows/accelerator-key-property.md)アクセラレータとして使用する実際のキーを設定します。  
  
-   [Type プロパティ](../windows/accelerator-type-property.md)として仮想 (VIRTKEY) と ASCII/ANSI キーが解釈されるかどうかを決定します。  
  

  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [定義済みのアクセラレータ キー](../windows/predefined-accelerator-keys.md)   
 [リソース エディター](../windows/resource-editors.md)   
 [アクセラレータ エディター](../windows/accelerator-editor.md)
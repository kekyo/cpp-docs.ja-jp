---
title: "Cmanualaccessor::addparameterentry |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CManualAccessor::AddParameterEntry
- ATL.CManualAccessor.AddParameterEntry
- CManualAccessor.AddParameterEntry
- AddParameterEntry
- ATL::CManualAccessor::AddParameterEntry
dev_langs: C++
helpviewer_keywords: AddParameterEntry method
ms.assetid: 9048b164-052b-41b1-a861-227fc529e0b5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c2e364ce947baa800611f50b67add748a47472fd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cmanualaccessoraddparameterentry"></a>CManualAccessor::AddParameterEntry
パラメーターのエントリの構造体をパラメーターの入力を追加します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void AddParameterEntry(  
   DBORDINAL nOrdinal,  
   DBTYPE wType,  
   DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL,  
   DBPARAMIO eParamIO = DBPARAMIO_INPUT   
) throw ( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 `nOrdinal`  
 [in]パラメーターの数。  
  
 `wType`  
 [in]データ型です。  
  
 `nColumnSize`  
 [in]列のサイズ (バイト単位)。  
  
 `pData`  
 [in]バッファーに格納されている列のデータへのポインター。  
  
 `pLength`  
 [in]必要な場合は、フィールド長へのポインター。  
  
 `pStatus`  
 [in]必要な場合に、列の状態にバインドする変数へのポインター。  
  
 *eParamIO*  
 [in]バインディングが関連付けられているパラメーターが入力、入力/出力、または出力パラメーターであるかどうかを指定します。  
  
## <a name="remarks"></a>コメント  
 この関数を使用するには、まず[CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)   
 [Cmanualaccessor::addbindentry](../../data/oledb/cmanualaccessor-addbindentry.md)   
 [DBViewer サンプル](../../visual-cpp-samples.md)
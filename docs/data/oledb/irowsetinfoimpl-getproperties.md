---
title: "Irowsetinfoimpl::getproperties |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetInfoImpl.GetProperties
- IRowsetInfoImpl.GetProperties
- ATL::IRowsetInfoImpl::GetProperties
- IRowsetInfoImpl::GetProperties
- GetProperties
dev_langs: C++
helpviewer_keywords: GetProperties method
ms.assetid: 62c12063-28e0-4a06-ad4d-21c5c1e9ccea
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b66571e08b18f9bf42b35293bef0485f6a154bbf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetinfoimplgetproperties"></a>IRowsetInfoImpl::GetProperties
プロパティの現在の設定を返します、 **DBPROPSET_ROWSET**グループ。  
  
## <a name="syntax"></a>構文  
  
```  
  
      STDMETHOD ( GetProperties )(  
   const ULONG cPropertyIDSets,  
   const DBPROPIDSET rgPropertyIDSets[],  
   ULONG* pcPropertySets,  
   DBPROPSET** prgPropertySets   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[irowsetinfo:](https://msdn.microsoft.com/en-us/library/ms719611.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetInfoImpl クラス](../../data/oledb/irowsetinfoimpl-class.md)   
 [Irowsetinfoimpl::getreferencedrowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)   
 [IRowsetInfoImpl::GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)
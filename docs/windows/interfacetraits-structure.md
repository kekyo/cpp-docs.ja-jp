---
title: "InterfaceTraits 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::InterfaceTraits
dev_langs: C++
helpviewer_keywords: InterfaceTraits structure
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 494942ce3c50889cae7a8867dc2b86ed6a609313
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="interfacetraits-structure"></a>InterfaceTraits 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template<  
   typename I0  
>  
struct __declspec(novtable) InterfaceTraits;  
template<  
   typename CloakedType  
>  
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;  
  
template<>  
struct __declspec(novtable) InterfaceTraits<Nil>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `I0`  
 インターフェイスの名前。  
  
 `CloakedType`  
 RuntimeClass、Implements、および ChainInterfaces ことなく、一連のがインターフェイスはインターフェイス Id をサポートします。  
  
## <a name="remarks"></a>コメント  
 インターフェイスの一般的な特徴を実装します。  
  
 2 番目のテンプレートは、クロークされているインターフェイスに特殊化です。 3 番目のテンプレートは、Nil パラメーターに特殊化です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`Base`|`I0` テンプレート パラメーターのシノニムです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[InterfaceTraits::CanCastTo メソッド](../windows/interfacetraits-cancastto-method.md)|指定したポインターをへのポインターにキャストできるかどうかを示す`Base`です。|  
|[InterfaceTraits::CastToBase メソッド](../windows/interfacetraits-casttobase-method.md)|ポインターへのポインターをキャスト`Base`です。|  
|[InterfaceTraits::CastToUnknown メソッド](../windows/interfacetraits-casttounknown-method.md)|IUnknown へのポインターへのポインターをキャストします。|  
|[InterfaceTraits::FillArrayWithIid メソッド](../windows/interfacetraits-fillarraywithiid-method.md)|インターフェイス ID を割り当てます`Base`インデックス引数で指定された配列の要素にします。|  
|[InterfaceTraits::Verify メソッド](../windows/interfacetraits-verify-method.md)|ベースが正しく派生したことを確認します。|  
  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[InterfaceTraits::IidCount 定数](../windows/interfacetraits-iidcount-constant.md)|Id が現在の InterfaceTraits オブジェクトに関連付けられているインターフェイスの数を保持します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `InterfaceTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)
---
title: "runtime_exception クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
dev_langs:
- C++
helpviewer_keywords:
- runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 399d2531c06285012df12d703b4cda6e18469c38
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="runtimeexception-class"></a>runtime_exception クラス
C++ Accelerated Massive Parallelism (AMP) ライブラリ内の例外の基本型。  
  
### <a name="syntax"></a>構文  
  
```  
class runtime_exception : public std::exception;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[runtime_exception コンス トラクター](#ctor)|`runtime_exception` クラスの新しいインスタンスを初期化します。|  
|[~ runtime_exception デストラクター](#dtor)|`runtime_exception` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[get_error_code](#runtime_exception__get_error_code)|例外が発生したエラー コードを返します。|  

  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator=](#operator_eq)|指定された `runtime_exception` オブジェクトの内容をこのオブジェクトにコピーします。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `runtime_exception`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  

## <a name="runtime_exception__ctor"></a>runtime_exception コンス トラクター  
クラスの新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```  
runtime_exception(  
    const char * _Message,  
    HRESULT _Hresult ) throw();  
  
explicit runtime_exception(  
    HRESULT _Hresult ) throw();  
  
runtime_exception(  
    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 この例外の原因になったエラーの説明。  
  
 `_Hresult`  
 この例外の原因になったエラーの HRESULT。  
  
 `_Other`  
 コピーする `runtime_exception` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `runtime_exception` オブジェクト。  

## <a name="dtor"></a>~ runtime_exception デストラクター  
オブジェクトを破棄します。  
  
### <a name="syntax"></a>構文  
  
```  
virtual ~runtime_exception() throw();  
```  
  
## <a name="runtime_exception__get_error_code"></a>get_error_code   
例外が発生したエラー コードを返します。  
  
### <a name="syntax"></a>構文  
  
```  
HRESULT get_error_code() const throw();  
```  
  
### <a name="return-value"></a>戻り値  
 この例外の原因になったエラーの HRESULT。  
  
## <a name="runtime_exception__operator_eq"></a>  operator=   
  指定された `runtime_exception` オブジェクトの内容をこのオブジェクトにコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
runtime_exception & operator= (    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピーする `runtime_exception` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `runtime_exception` オブジェクトへの参照。  
  

  
## <a name="see-also"></a>関連項目  
 [Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)


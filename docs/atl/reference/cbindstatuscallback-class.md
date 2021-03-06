---
title: "次のクラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::Download
- ATLCTL/ATL::CBindStatusCallback::GetBindInfo
- ATLCTL/ATL::CBindStatusCallback::GetPriority
- ATLCTL/ATL::CBindStatusCallback::OnDataAvailable
- ATLCTL/ATL::CBindStatusCallback::OnLowResource
- ATLCTL/ATL::CBindStatusCallback::OnObjectAvailable
- ATLCTL/ATL::CBindStatusCallback::OnProgress
- ATLCTL/ATL::CBindStatusCallback::OnStartBinding
- ATLCTL/ATL::CBindStatusCallback::OnStopBinding
- ATLCTL/ATL::CBindStatusCallback::StartAsyncDownload
- ATLCTL/ATL::CBindStatusCallback::m_dwAvailableToRead
- ATLCTL/ATL::CBindStatusCallback::m_dwTotalRead
- ATLCTL/ATL::CBindStatusCallback::m_pFunc
- ATLCTL/ATL::CBindStatusCallback::m_pT
- ATLCTL/ATL::CBindStatusCallback::m_spBindCtx
- ATLCTL/ATL::CBindStatusCallback::m_spBinding
- ATLCTL/ATL::CBindStatusCallback::m_spMoniker
- ATLCTL/ATL::CBindStatusCallback::m_spStream
dev_langs:
- C++
helpviewer_keywords:
- asynchronous data transfer [C++]
- data transfer [C++]
- data transfer [C++], asynchronous
- CBindStatusCallback class
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 50a0a27528f402cda5906658cd2c9cf57a5908e8
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cbindstatuscallback-class"></a>次のクラス
このクラスは、`IBindStatusCallback` インターフェイスを実装します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS |   BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>  
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx
 <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 クラスは、データが受信されたときに呼び出される関数を含む、です。  
  
 *nBindFlags*  
 によって返されるバインド フラグを指定[GetBindInfo](#getbindinfo)します。 既定の実装を非同期にバインディングが設定するには、データ オブジェクトの最新バージョンを取得およびディスク キャッシュで取得したデータを格納しません。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|コンストラクターです。|  
|[次:: ~ 次](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBindStatusCallback::Download](#download)|ダウンロード プロセスを開始する静的メソッドを作成、`CBindStatusCallback`オブジェクト、および呼び出し`StartAsyncDownload`します。|  
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|非同期モニカーを作成するバインドの種類に関する情報を要求によって呼び出されます。|  
|[CBindStatusCallback::GetPriority](#getpriority)|バインド操作の優先度を取得する非同期モニカーによって呼び出されます。 ATL の実装を返します`E_NOTIMPL`します。|  
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|使用可能になったら、アプリケーションにデータを提供するには、呼び出されます。 データを読み取りし、データを使用するように渡される関数を呼び出します。|  
|[CBindStatusCallback::OnLowResource](#onlowresource)|リソースが少ないときに呼び出されます。 ATL の実装を返します`S_OK`します。|  
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|オブジェクトのインターフェイス ポインターをアプリケーションに渡すための非同期モニカーによって呼び出されます。 ATL の実装を返します`S_OK`します。|  
|[CBindStatusCallback::OnProgress](#onprogress)|データのダウンロード処理の進行状況を示すために呼び出されます。 ATL の実装を返します`S_OK`します。|  
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|バインドを開始したときに呼び出されます。|  
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|非同期データ転送が停止したときに呼び出されます。|  
|[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)|使用可能なバイトを初期化し、URL、および呼び出しからのプッシュ型のストリーム オブジェクトを作成をゼロに読み取られたバイト数`OnDataAvailable`たびにデータを利用できます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|読み取り可能バイト数。|  
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|読み取られたバイトの合計数。|  
|[CBindStatusCallback::m_pFunc](#m_pfunc)|関数へのポインターは、データがあるときに呼び出されます。|  
|[CBindStatusCallback::m_pT](#m_pt)|非同期データ転送を要求しているオブジェクトへのポインター。|  
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|ポインター、 [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755)現在のバインド操作のためのインターフェイスです。|  
|[CBindStatusCallback::m_spBinding](#m_spbinding)|ポインター、`IBinding`現在のバインド操作のためのインターフェイスです。|  
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|ポインター、 [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)インターフェイスを使用する URL。|  
|[CBindStatusCallback::m_spStream](#m_spstream)|ポインター、 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)データ転送用のインターフェイスです。|  
  
## <a name="remarks"></a>コメント  
 `CBindStatusCallback` クラスは、`IBindStatusCallback` インターフェイスを実装します。 `IBindStatusCallback`非同期データ転送の通知を受信できるように、アプリケーションで実装する必要があります。 システムによって提供される非同期モニカーを使用して`IBindStatusCallback`非同期データに関する情報を送受信する方法と、オブジェクトの間に転送します。  
  
 通常、`CBindStatusCallback`オブジェクトは、特定のバインド操作に関連付けられています。 たとえば、 [ASYNC](../../visual-cpp-samples.md)サンプルでは、URL プロパティを設定するときに作成、`CBindStatusCallback`オブジェクトへの呼び出しで`Download`:  
  
 [!code-cpp[NVC_ATL_Windowing #&86;](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]  
  
 非同期モニカーは、コールバック関数を使用して`OnData`データがあるときに、アプリケーションを呼び出す。 非同期モニカーは、システムによって提供されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 `IBindStatusCallback`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `CBindStatusCallback`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="cbindstatuscallback"></a>CBindStatusCallback::CBindStatusCallback  
 コンストラクターです。  
  
```
CBindStatusCallback();
```  
  
### <a name="remarks"></a>コメント  
 非同期データ転送に関する通知を受信するオブジェクトを作成します。 通常、バインド操作ごとに&1; つのオブジェクトが作成されます。  
  
 また、コンス トラクターを初期化[この](#m_pt)と[m_pFunc](#m_pfunc)に**NULL**します。  
  
##  <a name="dtor"></a>次:: ~ 次  
 デストラクターです。  
  
```
~CBindStatusCallback();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="download"></a>CBindStatusCallback::Download  
 作成、`CBindStatusCallback`オブジェクトと呼び出し`StartAsyncDownload`指定された URL からデータを非同期的にダウンロードを開始します。  
  
```
static HRESULT Download(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pT*  
 [in]非同期データ転送を要求しているオブジェクトへのポインター。 `CBindStatusCallback`オブジェクトがこのオブジェクトのクラスでテンプレート化されます。  
  
 *pFunc*  
 [in]読み取られるデータを受け取る関数へのポインター。 関数型のオブジェクトのクラスのメンバーである`T`です。 参照してください[このポインターは](#startasyncdownload)構文と例です。  
  
 `bstrURL`  
 [in]データを取得する URL です。 有効な URL またはファイル名を指定できます。 ことはできません**NULL**します。 例:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in]**IUnknown**のコンテナーです。 **NULL**既定です。  
  
 `bRelative`  
 [in]URL が相対パスまたは絶対かどうかを示すフラグです。 **FALSE**既定を絶対には、URL を意味します。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 によってオブジェクトに送信されるデータがあるたびに`OnDataAvailable`します。 `OnDataAvailable`データを読み取り、指す関数を呼び出す*pFunc* (たとえば、データを保管するため、画面に出力する場合)。  
  
##  <a name="getbindinfo"></a>CBindStatusCallback::GetBindInfo  
 モニカー バインドする方法を指示するには、呼び出されます。  
  
```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```  
  
### <a name="parameters"></a>パラメーター  
 *pgrfBSCF*  
 [out]ポインター **BINDF** bind 操作を実行する方法を示す列挙値。 既定では、次の列挙値に設定します。  
  
 **BINDF_ASYNCHRONOUS**非同期ダウンロードします。  
  
 **BINDF_ASYNCSTORAGE** `OnDataAvailable`返します**E_PENDING**データが利用できない場合まだデータが使用可能になるまでのブロックではなく。  
  
 **BINDF_GETNEWESTVERSION**バインド操作は、データの最新バージョンを取得する必要があります。  
  
 **BINDF_NOWRITECACHE**バインド操作では、ディスク キャッシュで取得したデータを保存しないでいます。  
  
 *pbindinfo*  
 [入力、出力]ポインター、**されていました**構造体の詳細については、オブジェクトが発生するバインディングを希望する方法を提供します。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、非同期にして、データ プッシュ モデルを使用するバインディングを設定します。 データ プッシュ モデルでは、モニカーは、バインドの非同期操作し、新しいデータがあるたびに継続的にクライアントに通知します。  
  
##  <a name="getpriority"></a>CBindStatusCallback::GetPriority  
 バインド操作の優先度を取得する非同期モニカーによって呼び出されます。  
  
```
STDMETHOD(GetPriority)(LONG* pnPriority);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnPriority*  
 [out]アドレス、**長い**成功した場合、優先順位を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
##  <a name="m_dwavailabletoread"></a>CBindStatusCallback::m_dwAvailableToRead  
 読み取り可能なバイト数を格納するために使用します。  
  
```
DWORD m_dwAvailableToRead;
```  
  
### <a name="remarks"></a>コメント  
 0 に初期化された`StartAsyncDownload`します。  
  
##  <a name="m_dwtotalread"></a>CBindStatusCallback::m_dwTotalRead  
 非同期データ転送で総バイト数を読み取る。  
  
```
DWORD m_dwTotalRead;
```  
  
### <a name="remarks"></a>コメント  
 毎回増加`OnDataAvailable`は実際に読み取るバイト数によって呼び出されます。 0 に初期化された`StartAsyncDownload`します。  
  
##  <a name="m_pfunc"></a>CBindStatusCallback::m_pFunc  
 関数が指す`m_pFunc`によって呼び出される`OnDataAvailable`(たとえば、データを保管するため、画面に出力する場合など) の使用可能なデータの読み取り後です。  
  
```
ATL_PDATAAVAILABLE m_pFunc;
```  
  
### <a name="remarks"></a>コメント  
 関数が指す`m_pFunc`オブジェクトのクラスのメンバーであるし、は、次の構文。  
  
```  
void Function_Name(  
   CBindStatusCallback<T>* pbsc,  
   BYTE* pBytes,  
   DWORD dwSize  
   );  
```  
  
##  <a name="m_pt"></a>CBindStatusCallback::m_pT  
 非同期データ転送を要求しているオブジェクトへのポインター。  
  
```
T* m_pT;
```  
  
### <a name="remarks"></a>コメント  
 `CBindStatusCallback`オブジェクトがこのオブジェクトのクラスでテンプレート化されます。  
  
##  <a name="m_spbindctx"></a>CBindStatusCallback::m_spBindCtx  
 ポインター、 [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755)バインド コンテキスト (特定のモニカー バインド操作に関する情報を格納するオブジェクト) へのアクセスを提供するインターフェイスです。  
  
```
CComPtr<IBindCtx> m_spBindCtx;
```  
  
### <a name="remarks"></a>コメント  
 初期化された`StartAsyncDownload`します。  
  
##  <a name="m_spbinding"></a>CBindStatusCallback::m_spBinding  
 ポインター、`IBinding`現在のバインド操作のインターフェイスです。  
  
```
CComPtr<IBinding> m_spBinding;
```  
  
### <a name="remarks"></a>コメント  
 初期化された`OnStartBinding`で公開される`OnStopBinding`します。  
  
##  <a name="m_spmoniker"></a>CBindStatusCallback::m_spMoniker  
 ポインター、 [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)インターフェイスを使用する URL。  
  
```
CComPtr<IMoniker> m_spMoniker;
```  
  
### <a name="remarks"></a>コメント  
 初期化された`StartAsyncDownload`します。  
  
##  <a name="m_spstream"></a>CBindStatusCallback::m_spStream  
 ポインター、 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)現在のバインド操作のインターフェイスです。  
  
```
CComPtr<IStream> m_spStream;
```  
  
### <a name="remarks"></a>コメント  
 初期化された`OnDataAvailable`から、 **STGMEDIUM**ときに構造体、 **BCSF**フラグは**BCSF_FIRSTDATANOTIFICATION**と解放、 **BCSF**フラグは**BCSF_LASTDATANOTIFICATION**します。  
  
##  <a name="ondataavailable"></a>CBindStatusCallback::OnDataAvailable  
 システム提供の非同期モニカー呼び出し`OnDataAvailable`使用可能になったら、オブジェクトにデータを提供します。  
  
```
STDMETHOD(  
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```  
  
### <a name="parameters"></a>パラメーター  
 *grfBSCF*  
 [in]A **BSCF**列挙値。 次のいずれか: **BSCF_FIRSTDATANOTIFICATION**、 **BSCF_INTERMEDIARYDATANOTIFICATION**、または**知らせる**します。  
  
 `dwSize`  
 [in]バインドの開始時から使用可能なデータのバイト単位での累積時間。 あるデータの量は使用されませんまたは特定の量が利用できないことを示す、0 にすることができます。  
  
 *pformatetc*  
 [in]ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682242)利用可能なデータの形式を格納する構造体。 形式がない場合、 **CF_NULL**します。  
  
 *pstgmed*  
 [in]ポインター、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms695269)で現在利用できる実際のデータを保持する構造体。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 `OnDataAvailable`データを読み取り、(たとえば、データを保管するため、画面に出力する場合)、オブジェクトのクラスのメソッドを呼び出します。 参照してください[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)詳細です。  
  
##  <a name="onlowresource"></a>CBindStatusCallback::OnLowResource  
 リソースが少ないときに呼び出されます。  
  
```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwReserved`  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
##  <a name="onobjectavailable"></a>CBindStatusCallback::OnObjectAvailable  
 オブジェクトのインターフェイス ポインターをアプリケーションに渡すための非同期モニカーによって呼び出されます。  
  
```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```  
  
### <a name="parameters"></a>パラメーター  
 `riid`  
 要求されたインターフェイスのインターフェイス id です。 使用されません。  
  
 `punk`  
 IUnknown インターフェイスのアドレスです。 使用されません。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
##  <a name="onprogress"></a>CBindStatusCallback::OnProgress  
 データのダウンロード処理の進行状況を示すために呼び出されます。  
  
```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```  
  
### <a name="parameters"></a>パラメーター  
 `ulProgress`  
 符号なし長整数。 使用されません。  
  
 `ulProgressMax`  
 符号なし長整数未使用。  
  
 `ulStatusCode`  
 符号なし長整数。 使用されません。  
  
 `szStatusText`  
 文字列値のアドレスです。 使用されません。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
##  <a name="onstartbinding"></a>CBindStatusCallback::OnStartBinding  
 データ メンバーを設定[m_spBinding](#m_spbinding)に、`IBinding`でポインター`pBinding`します。  
  
```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwReserved`  
 将来使用するために予約されています。  
  
 `pBinding`  
 [in]現在のアドレスは、操作をバインドします。 NULL は指定できません。 クライアントは、バインド オブジェクトへの参照を保持するには、このポインターの AddRef を呼び出す必要があります。  
  
##  <a name="onstopbinding"></a>CBindStatusCallback::OnStopBinding  
 リリース、`IBinding`データ メンバー内のポインター [m_spBinding](#m_spbinding)します。  
  
```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```  
  
### <a name="parameters"></a>パラメーター  
 `hresult`  
 Bind 操作からステータス コードが返されます。  
  
 szStatusText  
 文字列値のアドレスです。  
  
### <a name="remarks"></a>コメント  
 システム提供の非同期モニカー バインド操作の終了を示すによって呼び出されます。  
  
##  <a name="startasyncdownload"></a>CBindStatusCallback::StartAsyncDownload  
 指定された URL からデータを非同期的にダウンロードを開始します。  
  
```
HRESULT StartAsyncDownload(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pT*  
 [in]非同期データ転送を要求しているオブジェクトへのポインター。 `CBindStatusCallback`オブジェクトがこのオブジェクトのクラスでテンプレート化されます。  
  
 *pFunc*  
 [in]読み込まれているデータを受け取る関数へのポインター。 関数型のオブジェクトのクラスのメンバーである`T`です。 参照してください**解説**構文と例です。  
  
 `bstrURL`  
 [in]データを取得する URL です。 有効な URL またはファイル名を指定できます。 ことはできません**NULL**します。 例:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in]**IUnknown**のコンテナーです。 **NULL**既定です。  
  
 `bRelative`  
 [in]URL が相対パスまたは絶対かどうかを示すフラグです。 **FALSE**既定を絶対には、URL を意味します。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 によってオブジェクトに送信されるデータがあるたびに`OnDataAvailable`します。 `OnDataAvailable`データを読み取り、指す関数を呼び出す*pFunc* (たとえば、データを保管するため、画面に出力する場合)。  
  
 関数が指す*pFunc*オブジェクトのクラスのメンバーであるし、は、次の構文。  
  
 `void Function_Name(`  
  
 `CBindStatusCallback<T>*` `pbsc` `,`  
  
 `BYTE*` `pBytes` `,`  
  
 `DWORD` `dwSize`  
  
 `);`  
  
 次の例では (から取得した、 [ASYNC](../../visual-cpp-samples.md)サンプル)、関数`OnData`テキスト ボックスに、受信したデータを書き込みます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&87;](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)


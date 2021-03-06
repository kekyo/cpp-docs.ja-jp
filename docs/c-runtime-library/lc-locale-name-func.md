---
title: ___lc_locale_name_func | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: ___lc_locale_name_func
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords: ___lc_locale_name_func
dev_langs: C++
helpviewer_keywords: ___lc_locale_name_func
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a60ca29a61d423186c8b53f23aa9e4d2941f8c57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="lclocalenamefunc"></a>___lc_locale_name_func
内部 CRT 関数。 スレッドの現在のロケール名を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
wchar_t** ___lc_locale_name_func(void);  
```  
  
## <a name="return-value"></a>戻り値  
 スレッドの現在のロケール名を含む文字列へのポインター。  
  
## <a name="remarks"></a>コメント  
 `___lc_locale_name_func` は、CRT データのスレッド ローカル ストレージから現在のロケール名を取得するために、他の CRT 関数によって使用される内部 CRT 関数です。 この情報は、[_get_current_locale](../c-runtime-library/reference/get-current-locale.md) 関数または [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) 関数を使用して取得することもできます。  
  
 内部 CRT 関数は実装固有であり、各リリースでの変更の対象です。 コード内では使用しないことをお勧めします。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`___lc_locale_name_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>関連項目  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale、_wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)
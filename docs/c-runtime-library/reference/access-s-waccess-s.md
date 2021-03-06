---
title: "_access_s、_waccess_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _access_s
- _waccess_s
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- waccess_s
- access_s
- _waccess_s
- _access_s
dev_langs:
- C++
helpviewer_keywords:
- access_s function
- taccess_s function
- _taccess_s function
- waccess_s function
- _access_s function
- _waccess_s function
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
caps.latest.revision: 28
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 051c2e6a6b0315e2ca4ab3192f28a370d969ec5b
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="accesss-waccesss"></a>_access_s、_waccess_s
ファイルの読み取り/書き込みアクセス許可を決定します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_access, _waccess](../../c-runtime-library/reference/access-waccess.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _access_s(   
   const char *path,   
   int mode   
);  
errno_t _waccess_s(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `path`  
 ファイルまたはディレクトリ パス。  
  
 `mode`  
 アクセス許可の設定。  
  
## <a name="return-value"></a>戻り値  
 ファイルに特定のモードが設定されている場合、各関数は 0 を返します。 指定したファイルが存在しないか、特定のモードでアクセスできない場合、関数はエラー コードを返します。 この場合、関数は次のようにエラー コードをセットから返し、`errno` も同じ値に設定します。  
  
 `EACCES`  
 アクセスが拒否されました。 ファイルのアクセス許可の設定では、指定したアクセスは許可されません。  
  
 `ENOENT`  
 ファイル名またはパスが見つかりません。  
  
 `EINVAL`  
 無効なパラメーター。  
  
 詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 ファイルを使用すると、`_access_s` 関数は、指定したファイルが存在し、`mode` 値で指定されているとおりにアクセスできるかどうかを判断します。 ディレクトリを使用すると、`_access_s` は指定されたディレクトリが存在するかどうかだけを判断します。 [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] 以降のオペレーティング システムでは、すべてのディレクトリに読み取りおよび書き込みアクセスできます。  
  
|モード値|ファイル チェックの目的|  
|----------------|---------------------|  
|00|存在のみ|  
|02|書き込みアクセス許可|  
|04|読み取りアクセス許可|  
|06|読み取りおよび書き込みアクセス許可|  
  
 ファイルの読み取りおよび書き込みアクセス許可では、ファイルを開く権限を確認するには不十分です。 たとえば、ファイルが別のプロセスによってロックされている場合、`_access_s` が 0 を返してもアクセスできない可能性があります。  
  
 `_waccess_s` 関数は、`_access_s` 関数のワイド文字バージョンです。 `_waccess_s` 関数の引数 `path` は、ワイド文字列です。 それ以外では、`_waccess_s` と `_access_s` の動作は同じです。  
  
 これらの関数では、パラメーターの検証が行われます。 `path` が `NULL` または `mode` が有効なモードを指定しない場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_taccess_s`|`_access_s`|`_access_s`|`_waccess_s`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_access_s`|\<io.h>|\<errno.h>|  
|`_waccess_s`|\<wchar.h> または \<io.h>|\<errno.h>|  
  
## <a name="example"></a>例  
 この例では、`_access_s` を使用して、crt_access_s.c という名前のファイルが存在し、書き込みが許可されているかどうかを確認します。  
  
```  
// crt_access_s.c  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    errno_t err = 0;  
  
    // Check for existence.   
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )  
    {  
        printf_s( "File crt_access_s.c exists.\n" );  
  
        // Check for write permission.   
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )  
        {  
            printf_s( "File crt_access_s.c does have "  
                      "write permission.\n" );  
        }  
        else  
        {  
            printf_s( "File crt_access_s.c does not have "  
                      "write permission.\n" );  
        }  
    }  
    else  
    {  
        printf_s( "File crt_access_s.c does not exist.\n" );  
    }  
}  
```  
  
```Output  
File crt_access_s.c exists.  
File crt_access_s.c does not have write permission.  
```  
  
## <a name="see-also"></a>関連項目  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_access、_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_chmod、_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_stat、_wstat 関数](../../c-runtime-library/reference/stat-functions.md)

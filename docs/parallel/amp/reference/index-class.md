---
title: "index クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
dev_langs:
- C++
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
caps.latest.revision: 20
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 52c19da3cb8de10c3963ca3b795cac1babb3dc7a
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="index-class"></a>index クラス
定義、 *N*の次元のインデックス pographics cpp amp.md します。  
  
## <a name="syntax"></a>構文  
  
```  
template <int _Rank>  
class index;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Rank`  
 ランク (次元数)。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[インデックスのコンス トラクター](#ctor)|`index` クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator--](#operator--)|`index` オブジェクトの各要素をデクリメントします。|  
|[operator(mod) =](#operator_mod_eq)|その要素がある数で除算された場合、`index` オブジェクトの各要素の剰余を計算します。|  
|[operator*=](#operator_star_eq)|`index` オブジェクトの各要素をある数で乗算します。|  
|[operator/=](#operator_div_eq)|`index` オブジェクトの各要素をある数で除算します。|  
|[index::operator\[\]](#operator_at)|指定したインデックス位置にある要素を返します。|  
|[operator++](#operator_add_add)|`index` オブジェクトの各要素をインクリメントします。|  
|[operator+=](#operator_add_eq)|指定した数を `index` オブジェクトの各要素に加算します。|  
|[operator=](#operator_eq)|指定された `index` オブジェクトの内容をこのオブジェクトにコピーします。|  
|[operator-=](#operator_-_eq)|指定した数を `index` オブジェクトの各要素から減算します。|  

  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[rank 定数](#rank)|`index` オブジェクトのランクを格納します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `index`  
  
## <a name="remarks"></a>コメント  
 `index`構造体の座標ベクターを表します*N*一意の場所を指定する整数、 *N*-次元空間です。 ベクターの値は最上位から最下位へ順に並べ替えられます。 使用してコンポーネントの値を取得する[演算子 =](#operator_eq)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp.h  
  
 **名前空間:** Concurrency  


## <a name="index_ctor"></a>インデックスのコンス トラクター
Index クラスの新しいインスタンスを初期化します。

```  
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
``` 

### <a name="parameters"></a>パラメーター

_Array  
ランク値を持つ&1; 次元配列。  
_I  
1 次元インデックスのインデックス位置。  
_I0  
最上位の次元の長さ。  
_I1  
最上位の次の次元の長さ。  
_I2  
最下位の次元の長さ。  
_Other  
新しいインデックス オブジェクトの基になるインデックス オブジェクトです。  

## <a name="operator--"></a>-演算子
デクリメント インデックス オブジェクトの各要素。  
```  
index<_Rank>& operator--() restrict(amp,cpu);  

index operator--(
   int
) restrict(amp,cpu);
```  
### <a name="return-values"></a>戻り値
前置演算子のインデックス オブジェクト (* この)。 後置演算子は、新しいインデックス オブジェクトです。

## <a name="operator_mod_eq"></a>operator(mod) =   
その要素が指定された数で除算したときに、インデックス オブジェクトの各要素の剰余 (余り) を計算します。

```  
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```  
### <a name="parameters"></a>パラメーター
_Rhs、剰余を検索するで除算する数値。
Index オブジェクトの値を返します。

## <a name="operator_star_eq"></a>演算子 * =   
指定したインデックス オブジェクト内の各要素を乗算します。
```
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター
_Rhs に乗算する数値。

## <a name="operator_div_eq"></a>演算子/= 
Index オブジェクト内の各要素を指定した数で除算します。

```
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>パラメーター
_Rhs で除算する数値。

## <a name="operator_at"></a>  operator\[\]  
指定した位置にあるインデックスのコンポーネントを返します。

```
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター
_Index 0 からランク-1 までの整数。

### <a name="return-value"></a>戻り値
指定したインデックス位置にある要素。

### <a name="remarks"></a>コメント
次の例では、インデックスのコンポーネント値を表示します。
```  
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator_add_add"></a>+ + 演算子   
Index オブジェクトの各要素をインクリメントします。
```  
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```  
### <a name="return-value"></a>戻り値
前置演算子のインデックス オブジェクト (* この)。 後置演算子は、新しいインデックス オブジェクトです。

## <a name="operator_add_eq"></a>operator + =   
Index オブジェクトの各要素に指定された数を追加します。
```  
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>パラメーター
_Rhs 加算する数。

### <a name="return-value"></a>戻り値
インデックス オブジェクトです。

## <a name="operator_eq"></a>  operator=   
これには、指定したインデックス オブジェクトの内容をコピーします。
```  
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>パラメーター
_Other からコピー先のインデックス オブジェクトです。

### <a name="return-value"></a>戻り値
このインデックス オブジェクトへの参照。

## <a name="operator_-_eq"></a>-= 演算子
Index オブジェクトの各要素から指定した数を減算します。
```  
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```  
### <a name="parameters"></a>パラメーター
_Rhs 減算する数。

### <a name="return-value"></a>戻り値
インデックス オブジェクトです。   

## <a name="rank"></a>ランク  
  Index オブジェクトのランクを取得します。
```
static const int rank = _Rank;
``` 
## <a name="see-also"></a>関連項目  
 [Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)


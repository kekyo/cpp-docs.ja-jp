---
title: "less 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xfunctional/std::less
dev_langs: C++
helpviewer_keywords:
- less struct
- less function
ms.assetid: 39349da3-11cd-4774-b2cc-b46af5aae5d7
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 723881fd2f46addf6b7e68a9672d5a7c546ca7d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="less-struct"></a>less 構造体
引数に対して "より小さい" 演算 (`operator<`) を実行する二項述語。  
  
## <a name="syntax"></a>構文  
  
```
template <class Type = void>
struct less : public binary_function <Type, Type, bool>  
{
    bool operator()(const Type& Left, const Type& Right) const;
 };

// specialized transparent functor for operator<
template <>
struct less<void>  
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) <std::forward<U>(Right));
 };
```  
  
#### <a name="parameters"></a>パラメーター  
 `Type`、`T`、`U`  
 指定または推論された型のオペランドを受け取る `operator<` をサポートする任意の型。  
  
 `Left`  
 より小さい演算の左オペランド。 特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。 特殊化されたテンプレートは、推論された型 `T` の左辺値および右辺値参照引数の完全転送を行います。  
  
 `Right`  
 より小さい演算の右オペランド。 特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。 特殊化されたテンプレートは、推論された型 `U` の左辺値および右辺値参照引数の完全転送を行います。  
  
## <a name="return-value"></a>戻り値  
 `Left < Right` の結果。 特殊化されたテンプレートは、結果の完全転送を行います。結果には `operator<` によって返された型が含まれます。  
  
## <a name="remarks"></a>コメント  
 二項述語 `less`< `Type`> は、型 `Type` の要素値のセットの、等価クラスへの厳密弱順序を提供します。ただし、その型がそのように順序付けられる標準的な数学的要件を満たす場合のみです。 任意のポインター型に対する特殊化によって、要素の完全な順序付けが生成されます。この場合、一意の値を持つすべての要素が、相互の値に基づいて並べ替えられます。  
  
## <a name="example"></a>例  
  
```cpp  
// functional_less.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
struct MyStruct {  
   MyStruct(int i) : m_i(i){}  
  
   bool operator < (const MyStruct & rhs) const {  
      return m_i < rhs.m_i;  
   }     
  
   int m_i;  
};  
  
int main() {  
   using namespace std;  
   vector <MyStruct> v1;  
   vector <MyStruct>::iterator Iter1;  
   vector <MyStruct>::reverse_iterator rIter1;  
  
   int i;  
   for ( i = 0 ; i < 7 ; i++ )       
       v1.push_back( MyStruct(rand()));  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )   
cout << Iter1->m_i << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   sort( v1.begin( ), v1.end( ), less<MyStruct>());  
  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )   
cout << Iter1->m_i << " ";  
   cout << ")" << endl;  
 }  
```  
  
## <a name="output"></a>出力  
  
```
Original vector v1 = (41 18467 6334 26500 19169 15724 11478)
Sorted vector v1 = (41 6334 11478 15724 18467 19169 26500)
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<functional>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)




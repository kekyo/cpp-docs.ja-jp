---
title: "error_condition クラス | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::error_condition
- error_condition
- system_error/std::error_condition::value_type
- system_error/std::error_condition::assign
- system_error/std::error_condition::category
- system_error/std::error_condition::clear
- system_error/std::error_condition::message
- system_error/std::error_condition::operator bool
dev_langs:
- C++
helpviewer_keywords:
- error_condition class
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
caps.latest.revision: 16
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: a9171a3f28109f38e3ff3844797e242c669f36c2
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="errorcondition-class"></a>error_condition クラス
ユーザー定義のエラー コードを表します。  
  
## <a name="syntax"></a>構文  
  
```
class error_condition;
```  
  
## <a name="remarks"></a>コメント  
 `error_condition` 型のオブジェクトは、エラー コード値を格納するほか、レポートされたユーザー定義のエラーに使用されるエラー コードの[カテゴリ](../standard-library/error-category-class.md)を表すオブジェクトを指すポインターも格納します。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[error_condition](#error_condition)|`error_condition` 型のオブジェクトを構築します。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[value_type](#value_type)|格納されたエラー コード値を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[assign](#assign)|エラー コード値とカテゴリをエラー条件に割り当てます。|  
|[category](#category)|エラー カテゴリを返します。|  
|[clear](#clear)|エラー コード値とカテゴリをクリアします。|  
|[message](#message)|エラー コードの名前を返します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator==](#op_eq_eq)|`error_condition` オブジェクト間の同等性をテストします。|  
|[operator!=](#op_neq)|`error_condition` オブジェクト間の不等性をテストします。|  
|[operator<](#op_lt)|`error_condition` オブジェクトが比較のために渡される `error_code` オブジェクトより小さいかどうかをテストします。|  
|[operator=](#op_eq)|`error_condition` オブジェクトに新しい列挙値を代入します。|  
|[operator bool](#op_bool)|`error_condition` 型の変数をキャストします。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<system_error>  
  
 **名前空間:** std  
  
##  <a name="assign"></a>  error_condition::assign  
 エラー コード値とカテゴリをエラー条件に割り当てます。  
  
```
void assign(value_type val, const error_category& _Cat);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`val`|`error_code` に格納するエラー コード値。|  
|`_Cat`|`error_code` に格納するエラー カテゴリ。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、エラー コード値としての `val` と `_Cat` を指すポインターを格納します。  
  
##  <a name="category"></a>  error_condition::category  
 エラー カテゴリを返します。  
  
```
const error_category& category() const;
```  
  
### <a name="return-value"></a>戻り値  
 格納されたエラー カテゴリへの参照  
  
### <a name="remarks"></a>コメント  
  
##  <a name="clear"></a>  error_condition::clear  
 エラー コード値とカテゴリをクリアします。  
  
```
clear();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数はゼロ エラー コード値と [generic_category](../standard-library/system-error-functions.md#generic_category) を指すポインターを格納します。  
  
##  <a name="error_condition"></a>  error_condition::error_condition  
 `error_condition` 型のオブジェクトを構築します。  
  
```
error_condition();

error_condition(value_type val, const error_category& _Cat);

template <class _Enum>
error_condition(_Enum _Errcode,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_code>::type* = 0);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`val`|`error_condition` に格納するエラー コード値。|  
|`_Cat`|`error_condition` に格納するエラー カテゴリ。|  
|`_Errcode`|`error_condition` に格納する列挙値。|  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターはゼロ エラー コード値と [generic_category](../standard-library/system-error-functions.md#generic_category) を指すポインターを格納します。  
  
 2 番目のコンストラクターは、エラー コード値としての `val` と [error_category](http://msdn.microsoft.com/en-us/6fe57a15-63a1-4e79-8af4-6738e43e19c8) を指すポインターを格納します。  
  
 3 番目のコンストラクターは、エラー コード値としての `(value_type)_Errcode` と [generic_category](../standard-library/system-error-functions.md#generic_category) を指すポインターを格納します。  
  
##  <a name="message"></a>  error_condition::message  
 エラー コードの名前を返します。  
  
```
string message() const;
```  
  
### <a name="return-value"></a>戻り値  
 エラー コードの名前を表す `string`。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は `category().message(value())` を返します。  
  
##  <a name="op_eq_eq"></a>  error_condition::operator==  
 `error_condition` オブジェクト間の同等性をテストします。  
  
```
bool operator==(const error_condition& right) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`right`|等しいかどうかをテストするオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが等しい場合は **true**、オブジェクトが等しくない場合は **false**。  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、`category() == right.category() && value == right.value()` を返します。  
  
##  <a name="op_neq"></a>  error_condition::operator!=  
 `error_condition` オブジェクト間の不等性をテストします。  
  
```
bool operator!=(const error_condition& right) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`right`|不等性をテストするオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 `error_condition` オブジェクトが、`right` に渡される `error_condition` オブジェクトに等しくない場合は **true**。それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、`!(*this == right)` を返します。  
  
##  <a name="op_lt"></a>  error_condition::operator&lt;  
 `error_condition` オブジェクトが比較のために渡される `error_code` オブジェクトより小さいかどうかをテストします。  
  
```
bool operator<(const error_condition& right) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`right`|比較される `error_condition` オブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 `error_condition` オブジェクトが、比較対象として渡された `error_condition` より小さい場合は **true**。それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、`category() < right.category() || category() == right.category() && value < right.value()` を返します。  
  
##  <a name="op_eq"></a>  error_condition::operator=  
 `error_condition` オブジェクトに新しい列挙値を代入します。  
  
```
template <class _Enum>
error_condition(_Enum error,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_condition>::type&
 operator=(Enum _Errcode);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Errcode`|`error_condition` オブジェクトに代入する列挙値。|  
  
### <a name="return-value"></a>戻り値  
 メンバー関数によって新しい列挙値が代入される `error_condition` オブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、エラー コード値としての `(value_type)error` と [generic_category](../standard-library/system-error-functions.md#generic_category) を指すポインターを格納します。 `*this` を返します。  
  
##  <a name="op_bool"></a>  error_condition::operator bool  
 `error_condition` 型の変数をキャストします。  
  
```
explicit operator bool() const;
```  
  
### <a name="return-value"></a>戻り値  
 `error_condition` オブジェクトのブール値。  
  
### <a name="remarks"></a>コメント  
 この演算子は、[値](#value)が 0 と等しくない場合に限り、`true` に変換できる値が返されます。 戻り値の型は、`void *` またはその他の既知のスカラー型ではなく、`bool` 型にのみ変換可能です。  
  
##  <a name="value"></a>  error_condition::value  
 格納されたエラー コード値を返します。  
  
```
value_type value() const;
```  
  
### <a name="return-value"></a>戻り値  
 [value_type](#value_type) 型の格納されたエラー コード値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="value_type"></a>  error_condition::value_type  
 格納されたエラー コード値を表す型。  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>コメント  
 この型定義は `int` のシノニムです。  
  
## <a name="see-also"></a>関連項目  
 [error_category クラス](../standard-library/error-category-class.md)   
 [<system_error>](../standard-library/system-error.md)




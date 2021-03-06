---
title: "const (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- const_cpp
dev_langs:
- C++
helpviewer_keywords:
- const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 8a6a238f28ec8f84cd127b4af88a84edb26506ee
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="const-c"></a>const (C++)
データの宣言を変更するときに、 **const**キーワードは、オブジェクトまたは変数は変更可能なを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      const declaration ;  
member-function const ;  
```  
  
## <a name="const-values"></a>const の値  
 **Const**キーワードは、変数の値は定数であり、プログラマがそれを変更しないようにするようにコンパイラに指示するを指定します。  
  
```  
// constant_values1.cpp  
int main() {  
   const int i = 5;  
   i = 10;   // C3892  
   i++;   // C2105  
}  
```  
  
 C++ では、使用することができます、 **const**キーワードの代わりに、 [#define](../preprocessor/hash-define-directive-c-cpp.md)プリプロセッサ ディレクティブの定数値を定義します。 定義されている値**const**型がチェックされ、定数式の代わりに使用することができます。 C++ では、使用して配列のサイズを指定することができます、 **const**次のように変数。  
  
```  
// constant_values2.cpp  
// compile with: /c  
const int maxarray = 255;  
char store_char[maxarray];  // allowed in C++; not allowed in C  
```  
  
 C では、定数値は既定で外部リンケージに設定されるため、ソース ファイルでのみ指定できます。 C++ では、定数値は既定で内部リンケージに設定されるため、ヘッダー ファイルで指定できます。  
  
 **Const**ポインター宣言でキーワードを使用することもできます。  
  
```  
// constant_values3.cpp  
int main() {  
   char *mybuf = 0, *yourbuf;  
   char *const aptr = mybuf;  
   *aptr = 'a';   // OK  
   aptr = yourbuf;   // C3892  
}  
```  
  
 として宣言された変数へのポインター **const**としても宣言されているポインターにのみ割り当てることができます**const**です。  
  
```  
// constant_values4.cpp  
#include <stdio.h>  
int main() {  
   const char *mybuf = "test";  
   char *yourbuf = "test2";  
   printf_s("%s\n", mybuf);  
  
   const char *bptr = mybuf;   // Pointer to constant data  
   printf_s("%s\n", bptr);  
  
   // *bptr = 'a';   // Error  
}  
```  
  
 定数データへのポインターを関数パラメーターとして使用して、ポインターを通じて渡されるパラメーターが関数によって変更されないようにすることができます。  
  
 として宣言されているオブジェクトの**const**、できるだけ定数メンバー関数を呼び出します。 これによって、定数オブジェクトは変更されなくなります。  
  
```  
birthday.getMonth();    // Okay  
birthday.setMonth( 4 ); // Error  
```  
  
 非定数オブジェクトに対して、定数または非定数のメンバー関数を呼び出すことができます。 使用してメンバー関数をオーバー ロードできますも、 **const**キーワードです。 これにより、定数および非定数オブジェクトに対して呼び出される関数のバージョンが異なる。  
  
 コンス トラクターまたはデストラクターを宣言することはできません、 **const**キーワード。  
  
## <a name="const-member-functions"></a>const のメンバー関数  
 メンバー関数を宣言する、 **const**キーワードは、関数が呼び出されますが、オブジェクトを変更しない「読み取り専用」関数を指定します。 定数メンバー関数は、非静的データ メンバーを変更またはメンバー定数でない関数を呼び出すことはできません。定数メンバー関数を宣言するには、配置、 **const**キーワードの引数リストの閉じかっこの後にします。 **Const**キーワードは、宣言と定義の両方で必要です。  
  
```  
// constant_member_function.cpp  
class Date  
{  
public:  
   Date( int mn, int dy, int yr );  
   int getMonth() const;     // A read-only function  
   void setMonth( int mn );   // A write function; can't be const  
private:  
   int month;  
};  
  
int Date::getMonth() const  
{  
   return month;        // Doesn't modify anything  
}  
void Date::setMonth( int mn )  
{  
   month = mn;          // Modifies data member  
}  
int main()  
{  
   Date MyDate( 7, 4, 1998 );  
   const Date BirthDate( 1, 18, 1953 );  
   MyDate.setMonth( 4 );    // Okay  
   BirthDate.getMonth();    // Okay  
   BirthDate.setMonth( 4 ); // C2662 Error  
}  
```  
  
## <a name="c-and-c-const-differences"></a>C と C++ での const の相違点  
 として変数を宣言するときに**const** C ソース コード ファイルでこれを行うとします。  
  
```  
const int i = 2;  
```  
  
 そして、次のように、この変数を別のモジュールで使用できます。  
  
```  
extern const int i;  
```  
  
 C++ では、同じ動作を取得、宣言する必要がありますが、 **const**変数として。  
  
```  
extern const int i = 2;  
```  
  
 C ソース コード ファイルで使用できるように C++ ソース コード ファイルで `extern` 変数を宣言する場合は、次のコードを使用してください。  
  
```  
extern "C" const int x=10;  
```  
  
 C++ コンパイラによる名前修飾を防止します。  
  
## <a name="remarks"></a>コメント  
 次のメンバー関数のパラメーター リストと、 **const**関数が呼び出されますが、オブジェクトを変更していないキーワードを指定します。  
  
 詳細については**const**、次のトピックを参照してください。  
    
-   [const ポインターと volatile ポインター](../cpp/const-and-volatile-pointers.md)  
  
-   [型修飾子 (C 言語リファレンス)](../c-language/type-qualifiers.md)  
  
-   [volatile](../cpp/volatile-cpp.md)  
  
-   [#define](../preprocessor/hash-define-directive-c-cpp.md)です。  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)

---
title: "コンパイラの警告 (レベル 1) C4930 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4930
dev_langs: C++
helpviewer_keywords: C4930
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 457124730ea38f1e91f7dab0c709568f23cf6fc2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4930"></a>コンパイラの警告 (レベル 1) C4930
'プロトタイプ': プロトタイプ関数が呼び出されません (でした変数の定義が対象としていますか?)  
  
 未使用の関数プロトタイプが検出されました。 プロトタイプは、変数の宣言として用意されていますが場合、は、開く/閉じるかっこを削除します。  
  
 次の例では、C4930 が生成されます。  
  
```  
// C4930.cpp  
// compile with: /W1  
class Lock {  
public:  
   int i;  
};  
  
void f() {  
   Lock theLock();   // C4930  
   // try the following line instead  
   // Lock theLock;  
}  
  
int main() {  
}  
```  
  
 C4930 は、コンパイラは関数のプロトタイプの宣言と関数呼び出しの間で区別できないときも発生します。  
  
 次の例では、C4930 が生成されます。  
  
```  
// C4930b.cpp  
// compile with: /EHsc /W1  
  
class BooleanException  
{  
   bool _result;  
  
public:  
   BooleanException(bool result)  
      : _result(result)  
   {  
   }  
  
   bool GetResult() const  
   {  
      return _result;  
   }  
};  
  
template<class T = BooleanException>  
class IfFailedThrow  
{  
public:  
   IfFailedThrow(bool result)  
   {  
      if (!result)  
      {  
         throw T(result);  
      }  
   }  
};  
  
class MyClass  
{  
public:  
   bool MyFunc()  
   {  
      try  
      {  
         IfFailedThrow<>(MyMethod()); // C4930  
  
         // try one of the following lines instead  
         // IfFailedThrow<> ift(MyMethod());  
         // IfFailedThrow<>(this->MyMethod());  
         // IfFailedThrow<>((*this).MyMethod());  
  
         return true;  
      }  
      catch (BooleanException e)  
      {  
         return e.GetResult();  
      }  
   }  
  
private:  
   bool MyMethod()  
   {  
      return true;  
   }  
};  
  
int main()  
{  
   MyClass myClass;  
   myClass.MyFunc();  
}  
```  
  
 上記のサンプルで、引数を受け取らないメソッドの結果は、名前のないローカル クラス変数のコンス トラクターに引数として渡されます。 呼び出しは、ローカル変数の名前を付けるか、オブジェクト インスタンスを適切なメンバーへのポインター演算子と共にメソッドの呼び出しを付けることによりあいまいさを解決できます。
---
title: "方法: for each を使用して配列を反復処理する | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配列 [C++], 反復処理 (for each を使用して)"
ms.assetid: ddc88ce2-69e1-44fc-af84-5b6f62fcb9e3
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 方法: for each を使用して配列を反復処理する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、配列の [for each、in](../dotnet/for-each-in.md) キーワードを使用する方法を示します。  
  
## 使用例  
 このサンプルでは、参照型の配列の `for each` を使用する方法を示します。複数の次元の配列の次元ではない、`for each` ループは配列に繰り返さないことに注意してください。  
  
```  
// for_each_arrays.cpp  
// compile with: /clr  
using namespace System;  
ref struct MyClass {  
   void Test() { Console::WriteLine("in MyClass"); }  
};  
  
ref struct MyClass2 {  
   void Test() { Console::WriteLine("in MyClass2"); }  
};  
  
int main() {  
   array<MyClass ^> ^ MyArray = gcnew array<MyClass ^>(2);  
  
   int i = 0;  
   for each ( MyClass ^ c in MyArray ) {  
      Console::Write("{0} = ", i++);  
      c -> Test();  
   }  
  
   Console::WriteLine();  
  
   array< MyClass2 ^, 2 > ^ MyArray2 = gcnew array< MyClass2 ^, 2 >(2, 2);  
   i = 0;  
   for each ( MyClass2 ^ c in MyArray2 ) {  
      Console::Write("{0} = ", i++);  
      c -> Test();  
   }  
  
   array< MyClass2 ^, 2 > ^ MyArray3 = gcnew array< MyClass2 ^, 2 >(2, 0);  
   i = 0;  
   for each ( MyClass2 ^ c in MyArray3 ) {  
      Console::Write("{0} = ", i++);  
      c -> Test();  
   }  
}  
```  
  
  **MyClass に \= 0**  
**MyClass に \= 1**  
**MyClass2 の \= 0**  
**MyClass2 の \= 1**  
**MyClass2 の \= 2**  
**MyClass2 の \= 3**   
## 使用例  
 このサンプルでは <xref:System.Collections.ArrayList>を反復処理 <xref:System.Collections.IEnumerable>を実装する各を示します。  
  
```  
// for_each_arrays_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Collections;  
  
int main() {  
   int retval = 0;  
  
   ArrayList ^ arr = gcnew ArrayList();  
   arr->Add(10);  
   arr->Add(20);  
   arr->Add(30);  
  
   for each ( int c in arr )  
      retval += c;  
   Console::WriteLine(retval);  
}  
```  
  
  **60**   
## 使用例  
 このサンプルでは、配列の配列を反復処理する方法を示します。  
  
```  
// for_each_arrays_3.cpp  
// compile with: /clr  
using namespace System;  
  
#define ARRAY_SIZE 2  
  
int main() {  
   int i, j;  
  
   // Declares an array of managed arrays of Int32.  
   array< array< Int32 > ^ > ^ IntArray = gcnew array<array< Int32 > ^>(ARRAY_SIZE);  
  
   for (i = 0 ; i < ARRAY_SIZE ; i++) {  
      IntArray[i] = gcnew array< Int32 >(ARRAY_SIZE);  
         for ( int j = 0 ; j < ARRAY_SIZE ; j++ )   
            IntArray[i][j] = i + 10;  
   }  
  
   for (i = 0 ; i < ARRAY_SIZE ; i++)  
      for (int j = 0 ; j < ARRAY_SIZE ; j++)  
         Console::WriteLine("IntArray[{0}] = {1}", i, IntArray[i][j]);  
   Console::WriteLine();  
  
   for each (array<Int32> ^ xyz in IntArray)  
      for each ( int c in xyz )  
         Console::WriteLine(c);  
}  
```  
  
  **IntArray \[\] 0 \= 10**  
**IntArray \[\] 0 \= 10**  
**IntArray \[\] 1 \= 11**  
**IntArray \[\] 1 \= 11**  
**10**  
**10**  
**11**  
**11**   
## 参照  
 [for each、in](../dotnet/for-each-in.md)
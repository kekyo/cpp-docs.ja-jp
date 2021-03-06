---
title: "型およびメンバーの非推奨化 (C + + CX) |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.prod: windows-client-threshold
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 0fbed1c29feccc6a999545daab6be8bd9ccfc7f9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="deprecating-types-and-members-ccx"></a>型およびメンバーの非推奨化 (C++/CX)
C + + CX、プロデューサーおよびコンシューマーを使用して用の Windows ランタイム型とメンバーの非推奨、[推奨されなくなった](http://msdn.microsoft.com/en-us/8b02ad36-3b5f-4361-888b-e6a99040e57c)属性はサポートされています。 この属性が適用された API を利用すると、その API は推奨されておらず、代替 API の使用を推奨する警告メッセージがコンパイル時に表示されます。 独自のパブリック型およびメソッドでこの属性を適用し、独自のカスタム メッセージを提供することもできます。  
  
> [!CAUTION]
>  [Deprecated](http://msdn.microsoft.com/en-us/8b02ad36-3b5f-4361-888b-e6a99040e57c)属性は、Windows ランタイム型でのみ使用します。 標準 C++ のクラスおよびメンバーの場合は、 [__declspec(deprecated)](http://msdn.microsoft.com/library/044swk7y.aspx)を使用します。  
  
### <a name="example"></a>例  
 次の例では、たとえば Windows ランタイム コンポーネントで、独自のパブリック API を非推奨にする方法を示します。 型 [Windows:Foundation::Metadata::DeprecationType](http://msdn.microsoft.com/en-us/ee01e63d-37d0-4273-accc-fca174f88bfa) 型の 2 番目のパラメーターは、API が非推奨であるか、削除済みであるかを指定します。 現在 DeprecationType::Deprecated という値のみがサポートされています。 属性の 3 番目のパラメーターは、属性の適用対象である [Windows::Foundation::Metadata::Platform](http://msdn.microsoft.com/en-us/1eae292d-1ab7-4d97-a58c-b0beffd51ef5) を指定します。  
  
```  
  
namespace wfm = Windows::Foundation::Metadata;  
  
public ref class Bicycle sealed  
{  
  
public:  
    property double Speed;  
  
    [wfm::Deprecated("Use the Speed property to compute the angular speed of the wheel", wfm::DeprecationType::Deprecate, 0x0)]  
    double ComputeAngularVelocity();  
};  
```  
  
## <a name="supported-targets"></a>サポート対象  
 次の表では、Deprecated 属性を適用できるコンストラクトを示します:  
  
||  
|-|  
|XAML コントロール|  
|delegate|  
|event|  
|列挙型フィールド|  
|enum|  
|struct|  
|メソッド|  
|クラス|  
|interface|  
|property|  
|構造体のフィールド|  
|パラメーター化されたコンストラクター|  
  
## <a name="see-also"></a>関連項目  
 [型システム](../cppcx/type-system-c-cx.md)   
 [Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)
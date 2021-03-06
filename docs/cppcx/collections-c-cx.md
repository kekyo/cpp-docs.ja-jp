---
title: "コレクション (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
caps.latest.revision: 35
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 35
---
# コレクション (C++/CX)
[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) プログラムでは、標準テンプレート ライブラリ \(STL\) コンテナー、または他の任意のユーザー定義コレクション型を自由に使用できます。 ただし、XAML コントロールまたは JavaScript クライアントに渡す場合など、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] アプリケーション バイナリ インターフェイス \(ABI\) 間で双方向にコレクションを渡す場合は、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コレクション型を使用する必要があります。  
  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] はコレクションおよび関連する型のインターフェイスを定義し、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は collection.h ヘッダー ファイルで具象 C\+\+ 実装を提供します。 この図は、コレクション型間のリレーションシップを示しています。  
  
 ![コレクション型を示す C&#43;&#43;&#47;CX 継承ツリー](../cppcx/media/cppcxcollectionsinheritancetree.png "CPPCXCollectionsInheritanceTree")  
  
-   [Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md)は [std::vector クラス](../Topic/vector%20Class%201.md)と似ています。  
  
-   [Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)は [std::map class クラス](../standard-library/map-class.md)と似ています。  
  
-   [Platform::Collections::VectorView クラス](../cppcx/platform-collections-vectorview-class.md)と [Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)は `Vector` と `Map` の読み取り専用のバージョンです。  
  
-   反復子は [Platform::Collections 名前空間](../cppcx/platform-collections-namespace.md)で定義されます。 これらの反復子は、STL 反復子の要件を満たし、任意の [Windows::Foundation::Collections](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.aspx) インターフェイス型や [Platform::Collections](../cppcx/platform-collections-namespace.md) 具象型で [std::find](http://msdn.microsoft.com/library/021e9ef9-8817-409f-92ee-cd7104867361)、[std::count\_if](http://msdn.microsoft.com/library/b785887c-83cd-4099-becc-3284dee05295) などの STL アルゴリズムを使えるようにします。 これは、たとえば、C\# で作成された [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントで 1 つのコレクションを繰り返して、それに STL アルゴリズムを適用できることを意味します。  
  
    > [!IMPORTANT]
    >  プロキシ反復子 `VectorIterator` と `VectorViewIterator` は、プロキシ オブジェクト `VectoryProxy<T>` と `ArrowProxy<T>` を利用して、STL コンテナーでの使用を有効にします。 詳細については、この記事で後述する「VectorProxy 要素」を参照してください。  
  
-   [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] コレクション型は、STL コンテナーがサポートしているのと同じスレッド セーフの保証をサポートしています。  
  
-   [Windows::Foundation::Collections::IObservableVector](http://msdn.microsoft.com/library/windows/apps/br226052.aspx) と [Windows::Foundation::Collections::IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) は、コレクションがさまざまな方法で変更されるときに発生するイベントを定義します。 これらのインターフェイスを実装すると、[Platform::Collections::Map](../cppcx/platform-collections-map-class.md) と [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) は、XAML コレクションとのデータ バインドをサポートします。 たとえば、`Vector` にデータ バインドされている `Grid` がある場合、コレクションに項目を追加すると、変更がグリッド UI に反映されます。  
  
## ベクターの使用  
 クラスがシーケンス コンテナーを別の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントに渡す必要がある場合、[Windows::Foundation::Collections:: IVector\<T\>](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) をパラメーターや戻り値の型として使うか、[Platform::Collections::Vector\<T\>](../cppcx/platform-collections-vector-class.md) を具象実装として使います。 パブリックの戻り値またはパラメーターで `Vector` 型を使用しようとすると、コンパイラ エラー C3986 が発生します。 このエラーは、`Vector` を `IVector` に変更することで解決できます。  
  
> [!IMPORTANT]
>  独自のプログラム内のシーケンスを渡している場合は、`Vector` か `std::vector` のどちらかを使用します。それらの方が `IVector` より効率的であるためです。 ABI を介してコンテナーを渡す場合にのみ、`IVector` を使用します。  
>   
>  Windows ランタイムの型システムは、ジャグ配列の概念をサポートしていないため、IVector\<Platform::Array\<T\>\> を戻り値またはメソッド パラメーターとして渡すことはできません。 ABI を通じてジャグ配列またはシーケンスのシーケンスを渡すには、`IVector<IVector<T>^>` を使用します。  
  
 `Vector<T>` は、コレクションでの項目の追加、削除、およびアクセスに必要なメソッドを提供します。暗黙的に `IVector<T>` に変換可能です。`Vector<T>` のインスタンスで STL アルゴリズム使用することもできます。 次の例は、基本的な使用法をいくつか示しています。[begin 関数](../cppcx/begin-function.md)と [end 関数](../cppcx/end-function.md)は `Platform::Collections` 名前空間のもので、`std` 名前空間のものではありません。  
  
 [!code-cpp[cx_collections#01](../snippets/cpp/VS_Snippets_Misc/cx_collections/cpp/class1.cpp#01)]  
  
 `std::vector` を使用する既存のコードがあり、それを [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントで再使用する場合は、`Vector` または反復子のペアを取る `std::vector` コンストラクターの 1 つを使用して、ABI を介してコレクションを渡すポイントに `Vector` を構築します。 次の例は、`Vector` からの効率的な初期化のために `std::vector` 移動コンストラクターを使用する方法を示しています。 移動操作の後、元の `vec` 変数は有効でなくなります。  
  
 [!code-cpp[cx_collections#02](../snippets/cpp/VS_Snippets_Misc/cx_collections/cpp/class1.cpp#02)]  
  
 今後のいつか、ABI を介して渡す必要がある文字列ベクターがある場合、その文字列を最初に `std::wstring` 型として作成するのかそれとも `Platform::String^` 型として作成するのかを決定する必要があります。 その文字列に対して多くの処理を実行する必要がある場合、`wstring` を使用します。 それ以外の場合は、文字列を `Platform::String^` 型として作成して、後で変換するコストを回避してください。 また、これらの文字列を `std:vector` と `Platform::Collections::Vector` のどちらに内部的に埋め込むのかも決定する必要があります。 一般に、`std::vector` を使用し、ABI を介してコンテナーを渡す場合にのみ、そこから `Platform::Vector` を作成します。  
  
## ベクターにおける値の型  
 [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) に格納される要素は、暗黙的にまたは指定したカスタム [std::equal\_to](../standard-library/equal-to-struct.md) 比較子を使用するかして、等値比較をサポートする必要があります。 すべての参照型とすべてのスカラー型は、暗黙的に等値比較をサポートしています。[Windows::Foundation::DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx) などの非スカラー値型の場合や、カスタム比較 \(`objA->UniqueID == objB->UniqueID` など\) の場合、カスタム関数オブジェクトを提供する必要があります。  
  
  
  
## VectorProxy 要素  
 [Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md) と [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) により、[IVector\<T\>](http://msdn.microsoft.com/en-us/library/windows/apps/br206631.aspx) コンテナーで `range for` ループや [std::sort](http://msdn.microsoft.com/library/9b0a4fc1-5131-4c73-9c2e-d72211f2d0ae) などのアルゴリズムを使えるようになります。 ただし、C\+\+ ポインターの逆参照を使って `IVector` 要素にアクセスすることはできません。これらの要素には、[GetAt](http://msdn.microsoft.com/library/windows/apps/br206634.aspx) メソッドと [SetAt](http://msdn.microsoft.com/library/windows/apps/br206642.aspx) メソッドを使ってアクセスすることしかできません。 したがって、これらの反復子は、STL の要求に従って、`Platform::Details::VectorProxy<T>` プロキシ クラスおよび `Platform::Details::ArrowProxy<T>` プロキシ クラスを使用して `*`、`->`、`[]` の各演算子を介した個々の要素へのアクセスを提供します。 厳密には、`IVector<Person^> vec` が指定されている場合、`*begin(vec)` の型は `VectorProxy<Person^>` になります。 ただし、プロキシ オブジェクトは、ほとんどの場合、コードに対して透過的です。 これらのプロキシ オブジェクトは反復子によって内部でのみ使用されるため文書化されませんが、その機構の動作がわかっていると便利です。  
  
 `range for` コンテナーに対して `IVector` ループを使用する場合は、`auto&&` を使用して反復子変数が `VectorProxy` 要素に正しくバインドされるようにします。`auto` または `auto&` を使用すると、コンパイラ警告 C4239 が発生し、警告テキストに `VectoryProxy` が示されます。  
  
 `range for` に対する `IVector<Person^>` ループ処理の例を次に示します。 実行が 64 行のブレークポイントで停止していることに注意してください。**\[クイック ウォッチ\]** ウィンドウには、反復子変数 `p` が実際には `VectorProxy<Person^>` メンバー変数と `m_v` メンバー変数を持つ `m_i` であることが示されています。 ただし、この変数で `GetType` を呼び出すと、`Person` インスタンス `p2` と同一の型が返されます。`VectorProxy` と `ArrowProxy` が **\[クイック ウォッチ\]**、デバッガーの一部のコンパイラ エラー、またはその他の場所に表示される場合でも、通常はそれらについて明示的にコーディングする必要はありません。  
  
 ![範囲ベースの for ループ内にある VectorProxy](../cppcx/media/vectorproxy-1.png "VectorProxy\_1")  
  
 プロキシ オブジェクトに関してコーディングする必要があるのは、`dynamic_cast` 要素コレクションで特定の型の XAML オブジェクトを探している場合など、要素で `UIElement` を実行する必要がある場合です。 この場合は、最初に [Platform::Object](../cppcx/platform-object-class.md)^ に要素をキャストし、その後に動的キャストを実行する必要があります。  
  
```  
  
void FindButton(UIElementCollection^ col)  
{  
    // Use auto&& to avoid warning C4239  
    for (auto&& elem : col)  
    {  
        Button^ temp = dynamic_cast<Button^>(static_cast<Object^>(elem));  
        if (nullptr != temp)  
        {  
            // Use temp...  
        }  
    }  
}  
```  
  
## マップの使用  
 この例では、[Platform::Collections::Map](../cppcx/platform-collections-map-class.md) で項目の挿入と検索を行う方法と、`Map` を読み取り専用の [Windows::Foundation::Collections::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) 型として返す方法を示しています。  
  
 [!code-cpp[cx_collections#04](../snippets/cpp/VS_Snippets_Misc/cx_collections/cpp/class1.cpp#04)]  
  
 一般に、内部マップ機能については、パフォーマンス上の理由で `std::map` 型を優先します。 ABI を介してコンテナーを渡す必要がある場合は、[std::map](../standard-library/map-class.md) から [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) を構築し、`Map` を [Windows::Foundation::Collections::IMap](http://msdn.microsoft.com/library/windows/apps/br226042.aspx) として返します。 パブリックの戻り値またはパラメーターで `Map` 型を使用しようとすると、コンパイラ エラー C3986 が発生します。 このエラーは、`Map` を `IMap` に変更することで解決できます。 たとえば、実行するルックアップや挿入の数が多くなく、ABI を介して頻繁にコレクションを渡すなどの場合、最初から `Platform::Collections::Map` を使用し `std::map` を変換するコストを回避した方がコストを抑えられることがあります。 どちらの場合も、`IMap` のルックアップ操作と挿入操作は、3 つの種類で最もパフォーマンスが低いので避けます。 ABI を介してコンテナーを渡すポイントでのみ、`IMap` に変換します。  
  
## マップにおける値の型  
 [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) 内の要素は、順序付きです。`Map` に格納しようとする要素は、厳密な弱い順序付けに基づき、"より小さい" 比較をサポートする必要があります。このために、暗黙的な比較、または開発者が指定したカスタム比較子 [stl::less](../standard-library/less-struct.md) が使用されます。 スカラー型では、この比較を暗黙的にサポートしています。`Windows::Foundation::DateTime` などの非スカラー値型、またはカスタム比較 \(`objA->UniqueID < objB->UniqueID` など\) の場合、カスタム比較子を提供する必要があります。  
  
## コレクション型  
 コレクションは、シーケンス コレクションと関連コレクションそれぞれの変更可能バージョンと読み取り専用バージョンという 4 つのカテゴリに分類されます。 さらに、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は、コレクションのアクセスを簡単にする 3 つの反復子クラスを提供することによりコレクションを拡張します。 反復子の簡単な説明については、「[反復子](../standard-library/iterators.md)」を参照してください。  
  
 変更可能なコレクションの要素は変更できますが、*ビュー*と呼ばれる読み取り専用コレクションの要素は読み取りしか実行できません。[Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) コレクションまたは [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md) コレクションの要素には、反復子またはコレクションの [Vector::GetAt メソッド](../cppcx/vector-getat-method.md) とインデックスを使用してアクセスできます。 関連コレクションの要素は、コレクションの [Map::Lookup メソッド](../cppcx/map-lookup-method.md) またはキーを使用することによりアクセスできます。  
  
 [Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)  
 変更可能な関連コレクション。 マップ要素は、キーと値のペアです。 キーを検索してその関連付けられた値を取得することと、キーと値のペアをすべて繰り返すことの両方がサポートされています。  
  
 `Map` と `MapView` は、`<K, V, C = std::less<K>>` で template 宣言されるので、比較子をカスタマイズできます。  さらに、`Vector` と `VectorView` は `<T, E = std::equal_to<T>>` で template 宣言されるので、`IndexOf()` の動作をカスタマイズできます。 これは、値の構造体の `Vector` と `VectorView` について特に重要です。 たとえば、Vector\<Windows::Foundation::DateTime\> を作成するには、カスタム比較子を指定する必要があります。DateTime は \=\= 演算子をオーバーロードしないからです。  
  
 [Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)  
 `Map` の読み取り専用バージョン。  
  
 [Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md)  
 変更可能なシーケンス コレクション。`Vector<T>` は、定数時間ランダム アクセス操作と償却定数時間の[追加](../cppcx/vector-append-method.md)操作をサポートしています。  
  
 [Platform::Collections::VectorView クラス](../cppcx/platform-collections-vectorview-class.md)  
 `Vector` の読み取り専用バージョン。  
  
 [Platform::Collections::InputIterator クラス](../cppcx/platform-collections-inputiterator-class.md)  
 STL 入力反復子の要件を満たす STL の反復子。  
  
 [Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)  
 変更可能な STL ランダム アクセス反復子の要件を満たす STL 反復子。  
  
 [Platform::Collections::VectorViewIterator クラス](../cppcx/platform-collections-vectorviewiterator-class.md)  
 STL の `const` ランダム アクセス反復子の要件を満たす STL 反復子。  
  
### begin\(\) および end\(\) 関数  
 STL を使用した `Vector`、`VectorView`、`Map`、`MapView`、および任意の `Windows::Foundation::Collections` オブジェクトの処理を簡単にするために、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は、[begin 関数](../cppcx/begin-function.md) および [end 関数](../cppcx/end-function.md) 非メンバー関数のオーバーロードをサポートしています。  
  
 次の表は、使用できる反復子と関数の一覧を示しています。  
  
|反復子|関数|  
|---------|--------|  
|[Platform::Collections::VectorIterator\<T\>](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> \([Windows::Foundation::Collections:: IVector\<T\>](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) と int を内部に格納します。\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md)\([Windows::Foundation::Collections:: IVector\<T\>](http://msdn.microsoft.com/library/windows/apps/br206631.aspx)\)|  
|[Platform::Collections::VectorViewIterator\<T\>](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> \([IVectorView\<T\>](http://msdn.microsoft.com/library/windows/apps/br226058.aspx)^ と int を内部に格納します。\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md) \([IVectorView\<T\>](http://msdn.microsoft.com/library/windows/apps/br226058.aspx)^\)|  
|[Platform::Collections::InputIterator\<T\>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> \([IIterator\<T\>](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ と T を内部に格納します。\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md) \([IIterable\<T\>](http://msdn.microsoft.com/library/windows/apps/br226024.aspx)\)|  
|[Platform::Collections::InputIterator\<IKeyValuePair\<K, V\>^\>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> \([IIterator\<T\>](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ と T を内部に格納します。\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md) \([IMap\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226042.aspx).|  
|[Platform::Collections::InputIterator\<IKeyValuePair\<K, V\>^\>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> \([IIterator\<T\>](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ と T を内部に格納します。\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md) \([Windows::Foundation::Collections::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx)\)|  
  
### コレクション変更イベント  
 `Vector` と `Map` は、XAML コレクションでのデータ バインドをサポートしていますが、これは、コレクション オブジェクトが変更またはリセットされたとき、またはコレクションのいずれかの要素が挿入、削除、または変更されたときに発生するイベントを実装することで実現されています。 データ バインドをサポートする独自の型を作成できます。ただし、`Map` と `Vector` から継承することはできません。これらの型はシールされているためです。  
  
 [Windows::Foundation::Collections::VectorChangedEventHandler](http://msdn.microsoft.com/library/windows/apps/br206656.aspx) デリゲートと [Windows::Foundation::Collections::MapChangedEventHandler](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) デリゲートは、コレクション変更イベントのイベント ハンドラーのシグネチャを指定します。[Windows::Foundation::Collections::CollectionChange](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx) パブリック列挙型クラス、 `Platform::Collection::Details::MapChangedEventArgs`、`Platform::Collections::Details::VectorChangedEventArgs` ref クラスは、イベントの原因を特定するためにイベント引数を格納します。 \* `EventArgs` 型は `Details` 名前空間で定義されますが、これは、`Map` か `Vector` を使用するときには、それらを明示的に作成および利用する必要がないためです。  
  
## 参照  
 [型システム](../cppcx/type-system-c-cx.md)   
 [Built\-in Types](http://msdn.microsoft.com/ja-jp/acc196fd-09da-4882-b554-6c94685ec75f)   
 [Visual C\+\+ の言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)
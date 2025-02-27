---
title: XAML のマークアップ拡張機能の概要
ms.date: 03/30/2017
helpviewer_keywords:
- markup extensions [XAML Services], custom
- XAML [XAML Services], markup extensions
ms.assetid: 261b2b11-2dc0-462f-8c66-55b8c9c6e436
ms.openlocfilehash: 68c03589294bcc8b58f1142331d4a889f0f18a3b
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736493"
---
# <a name="markup-extensions-for-xaml-overview"></a>XAML のマークアップ拡張機能の概要

マークアップ拡張機能は、プリミティブでも特定の XAML 型でもない値を取得するための XAML の手法です。 属性による使用では、マークアップ拡張機能は、左中かっこ `{` でマークアップ拡張機能スコープに入り、右中かっこ `}` で終了するという、既知の文字シーケンスを使用します。 .NET Framework XAML サービスを使用する場合は、System.Xaml アセンブリから XAML 言語の定義済みのマークアップ拡張機能をいくつか使用できます。 また、System.Xaml で定義された <xref:System.Windows.Markup.MarkupExtension> クラスからサブクラスを作成し、独自のマークアップ拡張機能を定義することもできます。 または、そのフレームワークを既に参照している場合は、特定のフレームワークによって定義されたマークアップ拡張機能を使用できます。

マークアップ拡張機能の使用にアクセスした XAML オブジェクト ライターは、 <xref:System.Windows.Markup.MarkupExtension> オーバーライドのサービス接続ポイントを通じて、カスタム <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A?displayProperty=nameWithType> クラスにサービスを提供することができます。 このサービスを使用すると、使用に関するコンテキスト、オブジェクト ライターの特定の機能、XAML スキーマ コンテキストなどを取得することができます。

<a name="XAML_Defined_Markup_Extensions"></a>
## <a name="xaml-defined-markup-extensions"></a>XAML で定義されたマークアップ拡張機能

XAML 言語をサポートするため、.NET Framework XAML サービスによっていくつかのマークアップ拡張機能が実装されています。 これらのマークアップ拡張機能は、言語としての XAML の仕様の部分に対応しています。 これらは、通常、一般的に使用される構文では `x:` プレフィックスによって識別できます。 これらの XAML 言語要素の .NET Framework XAML サービスの実装はすべて、@no__t 0 の基底クラスから派生します。

> [!NOTE]
> `x:` プレフィックスは、XAML 稼働環境のルート要素で、XAML 言語の名前空間を標準的な XAML 名前空間にマッピングするために使用します。 たとえば、さまざまな特定のフレームワークの Visual Studio プロジェクトとページテンプレートでは、この`x:`マッピングを使用して XAML ファイルが開始されます。 独自の XAML 名前空間のマッピングに別のプレフィックス トークンを選択することもできますが、このドキュメントでは、既定の `x:` マッピングを、独自の固有なフレームワークの既定の XAML 名前空間や他の任意の CLR 名前空間または XML 名前空間ではなく、XAML 言語の XAML 名前空間の一部として定義されているエンティティを識別する手段と想定します。

### <a name="xtype"></a>x:Type

`x:Type` は、名前を指定した型の <xref:System.Type> オブジェクトを提供します。 この機能は、基になる CLR 型やそれから派生した型をグループ化のモニカーまたは識別子として使用する遅延メカニズムの中で最も頻繁に使用されます。 具体的な例には、WPF のスタイルとテンプレート、およびそれらにおける `TargetType` プロパティの使用があります。 詳細については、「 [x:Type のマークアップ拡張機能](x-type-markup-extension.md)」を参照してください。

### <a name="xstatic"></a>x:Static

`x:Static` は、直接的にはプロパティの値の型ではなくても、その型に評価することができる値型コード エンティティから、静的な値を生成します。 これは、型定義で既知の定数として既に存在する値を指定するときに便利です。 詳細については、「 [x:Static のマークアップ拡張機能](x-static-markup-extension.md)」を参照してください。

### <a name="xnull"></a>x:Null

`x:Null` は、XAML メンバーに対する値として `null` を指定します。 特定の型の設計やフレームワークの広義の概念によっては、 `null` がプロパティの既定値に該当しない場合や、空の文字列属性の暗黙的な値に該当しない場合もあります。 詳細については、「 [x:Null のマークアップ拡張機能](x-null-markup-extension.md)」を参照してください。

### <a name="xarray"></a>x:Array

`x:Array` は、XAML 構文での一般的な配列の作成をサポートします。基本要素とコントロール モデルで提供されているコレクションのサポートをあえて使用しない場合に使用します。 詳細については、「 [x:Array Markup Extension](x-array-markup-extension.md)」を参照してください。 XAML 2009 では、厳密に言うと、拡張機能としてではなく言語プリミティブとして配列にアクセスします。 詳細については、「 [XAML 2009 言語機能](xaml-2009-language-features.md)」を参照してください。

### <a name="xreference"></a>x:Reference

`x:Reference` は XAML 2009 に含まれており、元 (2006) の言語セットの拡張機能です。 `x:Reference` は、オブジェクト グラフにある別の既存のオブジェクトへの参照を表します。 このオブジェクトは、その `x:Name`によって識別されます。 詳細については、「 [x:Reference のマークアップ拡張機能](x-reference-markup-extension.md)」を参照してください。

### <a name="other-x-constructs"></a>その他の x:作成

XAML 言語機能をサポートするための他の `x:` コンストラクトも存在しますが、マークアップ拡張機能としては実装されていません。 詳細については[、「XAML 名前空間 (x:)」を参照してください。言語機能](xaml-namespace-x-language-features.md)。

<a name="the_markupextension_base_class"></a>

## <a name="the-markupextension-base-class"></a>MarkupExtension 基底クラス

System.Xaml の XAML リーダーと XAML ライターの既定の実装と対話できるカスタム マークアップ拡張機能を定義するには、抽象クラス <xref:System.Windows.Markup.MarkupExtension> からクラスを派生します。 このクラスには、オーバーライドする 1 つのメソッドとして、 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>があります。 また、マークアップ拡張機能で使用する引数をサポートする追加のコンストラクターと、それに対応する設定可能なプロパティも定義する必要があります。

カスタム マークアップ拡張機能は、 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>を通じて、マークアップ拡張機能が XAML プロセッサによって実際に起動された環境を報告するサービス コンテキストにアクセスします。 読み込みパスでは、これは通常 <xref:System.Xaml.XamlObjectWriter>です。 保存パスでは、これは通常 <xref:System.Xaml.XamlXmlWriter>です。 これらはそれぞれ、サービス プロバイダー パターンを実装する内部 XAML サービス プロバイダー コンテキスト クラスとして、サービス コンテキストを報告します。 使用できるサービスと、これらのサービスが何を表現するかについての詳細については、「 [XAML の型コンバーターおよびマークアップ拡張機能](type-converters-and-markup-extensions-for-xaml.md)」を参照してください。

マークアップ拡張機能クラスは、パブリックなアクセス レベルを使用する必要があります。XAML プロセッサは、マークアップ拡張機能のサービスを使用するために、そのマークアップ拡張機能のサポート クラスをいつでもインスタンス化できる必要があるからです。

<a name="naming_the_support_type"></a>
## <a name="defining-the-support-type-for-a-custom-markup-extension"></a>カスタム マークアップ拡張機能のサポート型の定義

.NET Framework XAML サービス、または .NET Framework XAML サービスに基づいて構築されたフレームワークを使用する場合は、2 種類の方法でマークアップ拡張機能のサポート型に名前を付けることができます。 型名は、XAML オブジェクト ライターが XAML 内でマークアップ拡張機能の使用を検出したときに、マークアップ拡張機能のサポート型にアクセスして呼び出しを試みる方法に関連しています。 次のいずれかの方法で名前を付けます。

- XAML マークアップの使用トークンと完全に一致する型名を付ける。 たとえば、 `{Collate ...}` 拡張機能の使用をサポートするためには、サポート型に `Collate`という名前を付けます。
- 使用トークンの文字列に `Extension`サフィックスを付加した型名を付ける。 たとえば、 `{Collate ...}` 拡張機能の使用をサポートするためには、サポート型に `CollateExtension`という名前を付けます。

検索は、まずサフィックス `Extension`が付加されたクラス名、次にサフィックス `Extension` が付加されていないクラス名という順序で行われます。
  
マークアップを使用する観点からは、サフィックス `Extension` を使用名の一部に含めることは有効です。 ただし、この場合、 `Extension` は完全にクラス名の一部として扱われます。したがって、サポート クラスにサフィックス `Extension` が付いていない場合、XAML オブジェクト ライターはその使用についてマークアップ拡張機能のサポート クラスを解決できません。

### <a name="the-parameterless-constructor"></a>パラメーターなしのコンストラクター

すべてのマークアップ拡張機能のサポート型について、パブリックなパラメーターなしのコンストラクターを公開する必要があります。 XAML オブジェクトライターがオブジェクト要素の使用からマークアップ拡張機能をインスタンス化する場合は、パラメーターなしのコンストラクターが必要です。 マークアップ拡張機能でオブジェクト要素の使用がサポートされることは、特にシリアル化の場合には、正当な予想です。 ただし、マークアップ拡張機能の属性による使用だけをサポートする場合は、パブリック コンストラクターなしでマークアップ拡張機能を実装することができます。  

マークアップ拡張機能の使用に引数がない場合は、使用をサポートするためにパラメーターなしのコンストラクターが必要です。

<a name="constructor_patterns_and_positional_arguments_for_a_custom_markup_extension"></a>
## <a name="constructor-patterns-and-positional-arguments-for-a-custom-markup-extension"></a>カスタム マークアップ拡張機能のコンストラクター パターンと位置指定引数

引数の意図された使用方法のあるマークアップ拡張機能については、パブリック コンストラクターは、意図された使用方法のモードに対応する必要があります。 つまり、有効な使用方法として位置指定引数を 1 つ使用するようにマークアップ拡張機能が設計されている場合であれば、その位置指定引数を取る 1 つの入力パラメーターを使用するパブリック コンストラクターをサポートする必要があります。

たとえば、 `Collate` マークアップ拡張機能が、モードを表す位置指定引数 ( `CollationMode` 列挙定数として指定される) が 1 つのモードのみをサポートするとします。 この場合は、次の形式のコンストラクターが必要になります。

```csharp
public Collate(CollationMode collationMode) {...}
```

基本的なレベルでは、マークアップ拡張機能に渡される引数は、マークアップの属性値から転送されるので、文字列です。 すべての引数を文字列にし、入力をそのレベルで処理することができます。 ただし、マークアップ拡張機能の引数がサポート クラスに渡される前に実行される特定の処理にアクセスすることもできます。

この処理では、概念としては、マークアップ拡張機能を「作成するオブジェクト」と見なして、そのメンバー値を設定します。 設定するように指定された各プロパティは、作成するオブジェクトに指定されたメンバーが設定される場合と同じように、XAML が解析される時点で評価されます。 次の 2 つの重要な違いがあります。
  
- 前述のように、マークアップ拡張機能のサポート型では、XAML でインスタンス化するために、パラメーターなしのコンストラクターを持つ必要はありません。 オブジェクトの構築は、テキスト構文で使用できる引数が位置指定引数または名前付き引数のいずれかとしてトークン化および評価されるまで遅延され、その時点で適切なコンストラクターが呼び出されます。
- マークアップ拡張機能の使用は入れ子にすることができます。 最も内側のマークアップ拡張機能が最初に評価されます。 そのため、そのような使用を想定して、いずれかの構築パラメーターを、生成するために値コンバーター (マークアップ拡張機能など) を必要とする型として宣言できます。

このような処理への依存については、前の例で説明したとおりです。 .NET Framework XAML サービスの XAML オブジェクト ライターは、列挙定数の名前を、ネイティブ レベルでの列挙値に処理します。

また、マークアップ拡張機能の位置指定パラメーターのテキスト構文を処理する際にも、構築引数にある型に関連付けた型コンバーターに依存するようにできます。

引数が位置指定引数と呼ばれるのは、使用の中でトークンに出会う順序が、割り当てられたコンストラクター パラメーターの位置的な順序に対応するからです。 たとえば、次のようなコンストラクター シグネチャについて考えてみます。

```csharp
public Collate(CollationMode collationMode, object collateThis) {...}
```

XAML プロセッサは、このマークアップ拡張機能に対して、2 つの位置指定引数を予期します。 `{Collate AlphaUp,{x:Reference circularFile}}`という使用があった場合、 `AlphaUp` トークンが最初のパラメーターに送られ、 `CollationMode` 列挙体の名前付き定数として評価されます。 内側の `x:Reference` の結果は 2 つ目のパラメーターに送られ、オブジェクトとして評価されます。

XAML で規定されているマークアップ拡張構文と処理の規則では、引数が位置指定引数の場合でも名前付き引数の場合でも、引数の区切り記号としてコンマが使用されます。

### <a name="duplicate-arity-of-positional-arguments"></a>位置指定引数の重複するアリティ

XAML オブジェクト ライターが位置指定引数によるマークアップ拡張機能の使用を検出したときに、同じ数の引数 (重複するアリティ) を受け取る複数のコンストラクターが存在している場合でも、必ずしもエラーには該当しません。 実際の動作は、カスタマイズ可能な XAML スキーマ コンテキスト設定である <xref:System.Xaml.XamlSchemaContextSettings.SupportMarkupExtensionsWithDuplicateArity%2A>によって異なります。 <xref:System.Xaml.XamlSchemaContextSettings.SupportMarkupExtensionsWithDuplicateArity%2A> が `true`である場合は、重複するアリティのみを理由に、XAML オブジェクト ライターから例外がスローされることはありません。 それ以上の動作は、厳密には定義されていません。 基本的な設計では、スキーマ コンテキストには特定のパラメーターに対応する型情報が設定されており、明示的なキャストを試みて、重複する候補から最もよく一致するシグネチャを確認できる、ということを前提としています。 それでも、XAML オブジェクト ライターで実行されている特定のスキーマ コンテキストによってテストが行われ、そのテストに合格するシグネチャが存在しない場合に、例外がスローされる可能性があります。

既定では、 <xref:System.Xaml.XamlSchemaContextSettings.SupportMarkupExtensionsWithDuplicateArity%2A> は .NET Framework XAML サービスの CLR ベースの `false` で <xref:System.Xaml.XamlSchemaContext> になります。 したがって、バッキング型のコンストラクターに重複するアリティが存在している状況で、マークアップ拡張機能の使用を検出した場合に、既定の <xref:System.Xaml.XamlObjectWriter> が例外をスローします。

<a name="named_arguments_for_a_custom_markup_extension"></a>   
## <a name="named-arguments-for-a-custom-markup-extension"></a>カスタムマークアップ拡張機能の名前付き引数

XAML によって指定されるマークアップ拡張機能は、使用の際に名前付き引数の形式を使用することもできます。 トークン化の最初のレベルでは、テキスト構文は引数に分割されます。 引数内に等号 (=) が存在すると、引数は名前付き引数として識別されます。 このような引数は、名前と値のペアにトークン化されます。 この場合の名前は、マークアップ拡張機能のサポート型の、パブリックに設定可能なプロパティの名前を指定します。 名前付き引数の使用をサポートする場合は、これらのパブリックに設定可能なプロパティを用意する必要があります。 プロパティは、パブリックである限りは、継承プロパティを指定できます。

<a name="accessing_service_provider_context_from_a_markup_extension_implementation"></a>
## <a name="accessing-service-provider-context-from-a-markup-extension-implementation"></a>マークアップ拡張機能の実装からサービス プロバイダーのコンテキストにアクセスする

使用可能なサービスは、すべての値コンバーターの場合と同じです。 ただし、それぞれの値コンバーターがサービス コンテキストを受け取る方法が違います。 サービスへのアクセスと、使用できるサービスについては、「 [XAML の型コンバーターおよびマークアップ拡張機能](type-converters-and-markup-extensions-for-xaml.md)」のトピックをご覧ください。

<a name="property_element_usage_of_a_markup_extension"></a>
## <a name="property-element-usage-of-a-markup-extension"></a>マークアップ拡張機能のプロパティ要素の使用

マークアップ拡張機能の使用のシナリオは、多くの場合、属性を使用したマークアップ拡張機能の使用を中心にして設計されます。 ただし、プロパティ要素による使用をサポートするバッキング クラスを定義することも可能です。

マークアップ拡張機能のプロパティ要素の使用をサポートするには、パラメーターなしのパブリックコンストラクターを定義します。 これは、静的コンストラクターではなく、インスタンス コンストラクターにする必要があります。 XAML プロセッサは通常、マークアップから処理するオブジェクト要素のパラメーターなしのコンストラクターを呼び出す必要があり、これにはオブジェクト要素としてマークアップ拡張クラスが含まれているため、これが必要になります。 さらに複雑なシナリオとして、クラスに対して既定以外の構築パスを定義することもできます。 (詳細については、「 [X:FactoryMethod ディレクティブ](x-factorymethod-directive.md)」を参照してください)。ただし、マークアップ拡張機能の目的では、これらのパターンを使用しないことをお勧めします。未加工のマークアップのデザイナーにとってもユーザーにとっても、使用パターンの検出が非常に困難になるからです。

<a name="attributing_for_a_custom_markup_extension"></a>
## <a name="attributing-for-a-custom-markup-extension"></a>カスタムマークアップ拡張機能の属性

デザイン環境と、特定の XAML オブジェクト ライターのシナリオのどちらをサポートするためにも、マークアップ拡張機能のサポート型にいくつかの CLR 属性を設定する必要があります。 これらの属性は、目的のマークアップ拡張機能の使用を報告します。

 <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute> は、 <xref:System.Type> が返すオブジェクトの型の <xref:System.Windows.Markup.ArrayExtension.ProvideValue%2A> 情報を報告します。 純粋なシグネチャとしては、 <xref:System.Windows.Markup.ArrayExtension.ProvideValue%2A> は <xref:System.Object>を返します。 ただし、コンシューマーの種類によっては、戻り値の型についてさらに詳細な情報が必要になる場合があります。 バインディングには、以下の項目が含まれます。

- マークアップ拡張機能の使用に関して、型を認識したサポートを提供できるデザイナーや IDE を実現するための情報。
- ターゲット クラスに対する `SetMarkupExtension` ハンドラーの高度な実装のための情報。特定の既知の <xref:System.Windows.Markup.MarkupExtension> 実装を名前で分岐して判別するのではなく、リフレクションに基づいてマークアップ拡張機能の戻り値の型を判別できるようになります。

<a name="serialization_of_markup_extension_usages"></a>   
## <a name="serialization-of-markup-extension-usages"></a>マークアップ拡張機能の使用のシリアル化

XAML オブジェクト ライターによってマークアップ拡張機能の使用が処理され、 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>が呼び出されると、かつてマークアップ拡張機能の使用だったコンテキストは XAML ノード ストリームに残りますが、オブジェクト グラフには残りません。 オブジェクト グラフでは、値だけが保持されます。 元のマークアップ拡張機能の使用をシリアル化された出力として保持する、設計シナリオとしての必要性や他の理由がある場合は、読み込みパスの XAML ノード ストリームからマークアップ拡張機能の使用を追跡するための独自のインフラストラクチャを設計する必要があります。 読み込みパスからノード ストリームの要素を再作成し、ノード ストリームの該当する位置に値を代入しながら、それらを XAML ライターで再生して保存パスにシリアル化する、という動作を実装できます。

<a name="markup_extensions_in_the_xaml_node_stream"></a>
## <a name="markup-extensions-in-the-xaml-node-stream"></a>XAML ノードストリームのマークアップ拡張機能

読み込みパスで XAML ノード ストリームを処理している場合、マークアップ拡張機能の使用は、オブジェクトとしてノード ストリーム内に登場します。

マークアップ拡張機能の使用で位置指定引数が使用される場合、その使用は初期化の値が設定された開始オブジェクトとして表されます。 大まかなテキスト表現では、ノード ストリームは次のようになります。

 `StartObject` (<xref:System.Xaml.XamlType> はマークアップ拡張機能の定義の型であり、戻り値の型ではありません)

 `StartMember` ( <xref:System.Xaml.XamlMember> の名前は `_InitializationText`)

 `Value` (値は、途中に区切り記号を含む文字列形式の位置指定引数)

 `EndMember`

 `EndObject`

名前付き引数によるマークアップ拡張機能の使用は、その名前のメンバー (それぞれにテキスト文字列値が設定されている) を持つオブジェクトとして表されます。

実際にマークアップ拡張機能の `ProvideValue` 実装を呼び出すには、XAML スキーマ コンテキストが必要です。その呼び出しには、型マッピングと、マークアップ拡張機能のサポート型インスタンスの作成が必要であるからです。 これは、マークアップ拡張機能の使用が、既定の .NET Framework XAML サービスのノード ストリーム内でこのような形式に保たれている理由の 1 つです。多くの場合、読み込みパスのリーダー部分では、必要な XAML スキーマ コンテキストを利用できません。

保存パスで XAML ノード ストリームを処理している場合は、通常、シリアル化するオブジェクトが当初はマークアップ拡張機能の使用と `ProvideValue` の結果によって提供されたことを知らせる情報はオブジェクト グラフ表現の中に存在しません。 マークアップ拡張機能の使用をラウンドトリップさせ、オブジェクト グラフのその他の変化もキャプチャする必要があるシナリオでは、元の XAML 入力に由来するマークアップ拡張機能の使用の情報を保存するため、独自の手法を考案する必要があります。 たとえば、マークアップ拡張機能の使用を復元するには、保存パス上のノード ストリームを処理してマークアップ拡張機能の使用を復元するか、元の XAML とラウンドトリップされた XAML に対して何らかのマージ処理を実行することができます。 WPF などの一部の XAML 実装フレームワークでは、中間の型 (式) を使用して、マークアップ拡張機能の使用が値を提供したケースを表す場合があります。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Markup.MarkupExtension>
- [XAML の型コンバーターおよびマークアップ拡張機能](type-converters-and-markup-extensions-for-xaml.md)
- [マークアップ拡張機能と WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)

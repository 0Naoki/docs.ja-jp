---
title: Visual Basic 内の組
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
ms.openlocfilehash: fdca36e47d0b1234a8964d7475354a726a61f085
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524578"
---
# <a name="tuples-visual-basic"></a>タプル (Visual Basic)

Visual Basic 2017 以降、Visual Basic 言語では、組の作成とタプルの要素へのアクセスが簡単になるタプルの組み込みサポートが提供されています。 組は、特定の数と値のシーケンスを持つ軽量なデータ構造です。 組をインスタンス化するときは、各値 (または要素) の数値とデータ型を定義します。 たとえば、2組 (またはペア) には2つの要素があります。 1つ目は `Boolean` 値、2番目のは `String` です。 タプルを使用すると、複数の値を1つのオブジェクトに簡単に格納できるので、多くの場合、メソッドから複数の値を返すための軽量な方法として使用されます。

> [!IMPORTANT]
> 組のサポートには <xref:System.ValueTuple> 型が必要です。 .NET Framework 4.7 がインストールされていない場合は、nuget ギャラリーから入手できる NuGet パッケージ `System.ValueTuple` を追加する必要があります。 このパッケージがないと、"定義済みの型 ' ValueTuple (,,,) ' が定義またはインポートされていません" のようなコンパイルエラーが発生することがあります。

## <a name="instantiating-and-using-a-tuple"></a>タプルのインスタンス化と使用

組をインスタンス化するには、コンマ区切り値の im かっこを囲みます。 これらの値はそれぞれ、タプルのフィールドになります。 たとえば、次のコードでは、`Date` が最初の値、`String` が2番目の値、3番目の値が `Boolean` であるトリプル (または3タプル) を定義しています。

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

既定では、組内の各フィールドの名前は、タプル内のフィールドの1から始まる位置と共に `Item` 文字列で構成されます。 この3つのタプルでは、`Date` フィールドが `Item1`、`String` フィールドが `Item2`、`Boolean` フィールドが `Item3` ます。 次の例では、前のコード行でインスタンス化されたタプルのフィールドの値を表示します。

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

Visual Basic タプルのフィールドは読み取り/書き込み可能です。タプルをインスタンス化した後は、その値を変更できます。 次の例では、前の例で作成した組の3つのフィールドのうち2つを変更し、結果を表示します。

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>名前付きタプルのインスタンス化と使用

組のフィールドに既定の名前を使用するのではなく、独自の名前をタプルの要素に割り当てることで、*名前付きタプル*をインスタンス化できます。 タプルのフィールドには、割り当てられた名前*または*既定の名前を使用してアクセスできます。 次の例では、前と同じ3つのタプルをインスタンス化しますが、最初のフィールド `EventDate`、2番目の `Name`、3番目の `IsHoliday` を明示的に指定する点が異なります。 次に、フィールドの値を表示して変更し、フィールドの値を再度表示します。

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>推論されたタプル要素の名前

Visual Basic 15.3 以降では、Visual Basic タプル要素の名前を推論できます。明示的に割り当てる必要はありません。 推論されたタプル名は、一連の変数から組を初期化するときに、タプル要素名を変数名と同じにする場合に便利です。

次の例では、明示的に指定された3つの要素、`state`、`stateName`、および `capital` を含む `stateInfo` 組を作成します。 要素の名前付けでは、タプルの初期化ステートメントによって、名前付きの要素が同じ名前の変数の値に割り当てられることに注意してください。

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]

要素と変数の名前が同じであるため、次の例に示すように、Visual Basic コンパイラはフィールドの名前を推論できます。

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

推論されたタプル要素名を有効にするには、Visual Basic プロジェクト (\* .vbproj) ファイルで使用する Visual Basic コンパイラのバージョンを定義する必要があります。

```xml
<PropertyGroup>
  <LangVersion>15.3</LangVersion>
</PropertyGroup>
```

バージョン番号は、15.3 以降の任意のバージョンの Visual Basic コンパイラにすることができます。 特定のコンパイラのバージョンをハードコーディングするのではなく、`LangVersion` の値として "Latest" を指定して、システムにインストールされている最新バージョンの Visual Basic コンパイラでコンパイルすることもできます。

詳細については、「 [Visual Basic 言語バージョンの設定](../../../language-reference/configure-language-version.md)」を参照してください。

場合によっては、Visual Basic コンパイラが候補名からタプル要素名を推測できず、タプルフィールドは、`Item1`、`Item2` などの既定の名前を使用してのみ参照できます。次のようなものがあります。

- 候補名は、`Item3`、`Rest`、`ToString` などの組メンバーの名前と同じです。

- 候補名が組で重複しています。

フィールド名の推定に失敗した場合、Visual Basic はコンパイラエラーを生成せず、実行時にスローされる例外も生成しません。 代わりに、`Item1` や `Item2` など、定義済みの名前でタプルフィールドを参照する必要があります。

## <a name="tuples-versus-structures"></a>タプルと構造体

Visual Basic タプルは、値型であり、いずれかの種類の**ValueTuple**ジェネリック型のインスタンスです。 たとえば、前の例で定義されている `holiday` 組は、<xref:System.ValueTuple%603> 構造のインスタンスです。 データの軽量コンテナーとして設計されています。 組は、複数のデータ項目を持つオブジェクトを簡単に作成できるようにするため、カスタム構造体に含まれる機能の一部が不足しています。 次の設定があります。

- カスタムメンバー。 組に対して独自のプロパティ、メソッド、またはイベントを定義することはできません。

- 検査. フィールドに割り当てられたデータを検証することはできません。

- 不変性. Visual Basic 組は変更可能です。 これに対して、カスタム構造体を使用すると、インスタンスを変更可能にするかどうかを制御できます。

カスタムメンバー、プロパティとフィールドの検証、または不変性が重要な場合は、Visual Basic [Structure](../../../language-reference/statements/structure-statement.md)ステートメントを使用してカスタム値型を定義する必要があります。

Visual Basic 組は、その**valuetuple**型のメンバーを継承します。 フィールドに加えて、次のメソッドがあります。

| メンバー | 説明 |
| ---|---|
| CompareTo | 現在の組と、同じ数の要素を持つ別の組とを比較します。 |
| 次の値に等しい | 現在の組が別の組またはオブジェクトと等しいかどうかを判断します。 |
| GetHashCode | 現在のインスタンスのハッシュコードを計算します。 |
| ToString | この組の文字列表現を返します。このタプルは `(Item1, Item2...)` の形式をとります。 `Item1` と `Item2` は組のフィールドの値を表します。 |

さらに、 **Valuetuple**型は <xref:System.Collections.IStructuralComparable> および <xref:System.Collections.IStructuralEquatable> インターフェイスを実装します。これにより、顧客比較子を定義できます。

## <a name="assignment-and-tuples"></a>割り当てとタプル

Visual Basic は、同じ数のフィールドを持つタプル型間の割り当てをサポートしています。 次のいずれかに該当する場合は、フィールドの種類を変換できます。

- ソースとターゲットのフィールドの型は同じです。

- ソース型からターゲット型への拡大 (または暗黙的) の変換が定義されています。

- `Option Strict` が `On`、変換元の型から変換先の型への縮小 (または明示的) 変換が定義されています。 ソース値が対象の型の範囲外の場合、この変換によって例外がスローされる可能性があります。

他の変換は、割り当てでは考慮されません。 タプル型間で許可されている割り当ての種類を見てみましょう。

以降の例で使用されている変数について考えます。

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

最初の2つの変数 `unnamed` と `anonymous` には、フィールドにセマンティック名が指定されていません。 フィールド名は、既定の `Item1` と `Item2` です。 最後の2つの変数 `named` と `differentName` には、セマンティックフィールド名があります。 この 2 つのタプルでは、フィールド名が異なっていることに注意してください。

これらの4つの組のフィールドの数 ("アリティ" と呼ばれる) は同じであり、それらのフィールドの型は同じです。 このため、これらの割り当てはすべて機能します。

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

タプルの名前が割り当てられていないことに注意してください。 フィールドの値は、タプルのフィールドの順序に従って割り当てられます。

最後に、`named` の最初のフィールドが `Integer` である場合でも、`named` タプルを `conversion` 組に割り当てることができることに注意してください。 `conversion` の最初のフィールドは `Long` です。 @No__t_0 を `Long` に変換することは、拡大変換であるため、この割り当ては成功します。

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

フィールドの数が異なるタプルを割り当てることはできません。

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>メソッドの戻り値としてのタプル

メソッドは、1つの値のみを返すことができます。 しかし、多くの場合、メソッド呼び出しを使用して複数の値を返す必要があります。 この制限を回避するには、いくつかの方法があります。

- メソッドによって返される値を表すプロパティまたはフィールドを持つカスタムクラスまたは構造体を作成できます。 そのため、重いソリューションです。このためには、メソッド呼び出しから値を取得するだけの目的を持つカスタム型を定義する必要があります。

- メソッドから1つの値を返すことができ、残りの値は、メソッドへの参照で渡すことによって返されます。 これには、変数をインスタンス化する際のオーバーヘッドが含まれ、参照渡しで渡す変数の値が誤って上書きされるリスクがあります。

- 複数の戻り値を取得するためのライトウェイトソリューションを提供するタプルを使用できます。

たとえば、.NET の**TryParse**メソッドは、解析操作が成功したかどうかを示す `Boolean` 値を返します。 解析操作の結果は、メソッドへの参照によって渡される変数に返されます。 通常、<xref:System.Int32.TryParse%2A?displayProperty=nameWithType> などの解析メソッドを呼び出すと、次のようになります。

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

独自のメソッドで <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> メソッドへの呼び出しをラップすると、解析操作からタプルを返すことができます。 次の例では、`NumericLibrary.ParseInteger` によって <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> メソッドが呼び出され、2つの要素を持つ名前付きタプルが返されます。

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

その後、次のようなコードを使用してメソッドを呼び出すことができます。

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>.NET Framework 内の組と組の Visual Basic

Visual Basic タプルは、.NET Framework 4.7 で導入された、 **ValueTuple**ジェネリック型の1つのインスタンスです。 .NET Framework には、一連の汎用的な**Tuple**クラスも含まれています。 ただし、これらのクラスは、Visual Basic 組と、次のようなさまざまな方法での**ValueTuple**ジェネリック型とは異なります。

- **組**クラスの要素は、`Item1`、`Item2` などという名前のプロパティです。 Visual Basic 組と**valuetuple**型では、tuple 要素はフィールドです。

- **組**のインスタンスまたは**valuetuple**インスタンスの要素にわかりやすい名前を割り当てることはできません。 Visual Basic を使用すると、フィールドの意味を伝える名前を割り当てることができます。

- **タプル**インスタンスのプロパティは読み取り専用です。タプルは変更できません。 Visual Basic 組と**valuetuple**型では、タプルフィールドは読み取り/書き込み可能です。タプルは変更可能です。

- ジェネリック**タプル**型は参照型です。 これらの**タプル**型を使用することは、オブジェクトを割り当てることを意味します。 ホット パスでは、これがアプリケーションのパフォーマンスに大きな影響を及ぼすことがあります。 Visual Basic 組と**Valuetuple**型は値型です。

@No__t_0 クラスの拡張メソッドを使用すると、Visual Basic 組と .NET **Tuple**オブジェクト間で簡単に変換できます。 **Totuple**メソッドは、Visual Basic タプルを .net **tuple**オブジェクトに変換し、 **tovaluetuple**メソッドは .net**タプル**オブジェクトを Visual Basic タプルに変換します。

次の例では、組を作成し、それを .NET **tuple**オブジェクトに変換して、Visual Basic タプルに変換して戻します。 次に、この組を元のタプルと比較して、等しいかどうかを確認します。

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>関連項目

- [Visual Basic の言語リファレンス](index.md)

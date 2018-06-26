---
title: C# 7.1 の新機能
description: C# 7.1 の新機能の概要。
ms.date: 08/16/2017
ms.openlocfilehash: 565db102284424f9d8f6fa04ec9c74b52c9da0e6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728655"
---
# <a name="whats-new-in-c-71"></a>C# 7.1 の新機能

C# 7.1 は C# 言語の最初のポイント リリースです。 この言語のリリース サイクルが増えたことになります。 新機能は間もなく使用できます。理論的には、各々の新機能が用意できたときに使用できます。 C# 7.1 では、特定のバージョンの言語に合わせるようにコンパイラを構成する機能が追加されます。 ツールをアップグレードする決定と言語バージョンをアップグレードする決定を分けることができます。

C# 7.1 では、[言語バージョン選択](../language-reference/configure-language-version.md)構成要素、3 つの新しい言語機能、新しいコンパイラ動作が追加されます。

このリリースの新しい言語機能は次のとおりです。

* [`async` `Main` メソッド](#async-main)
  - アプリケーションのエントリ ポイントに `async` 修飾子を設定できます。
* [`default` リテラル式](#default-literal-expressions)
  - ターゲットの種類を推論できるとき、既定の値式で既定のリテラル式を使用できます。
* [推論されたタプル要素の名前](#inferred-tuple-element-names)
  - タプル要素の名前は、多くの場合、タプル初期化から推論できます。

最後に、コンパイラには、[参照アセンブリ生成](#reference-assembly-generation)を制御する 2 つのオプション、`/refout` と `/refonly` があります。

ポイント リリースで最新の機能を使用するには、[コンパイラ言語バージョンを構成](../language-reference/configure-language-version.md)し、バージョンを選択する必要があります。

## <a name="async-main"></a>async main

*async main* メソッドにより、`Main` メソッドで `await` を使用できます。
以前は次のように記述する必要がありました。

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

それが次のように記述できるようになりました。

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

プログラムによって終了コードが返されない場合、<xref:System.Threading.Tasks.Task> を返す `Main` メソッドを宣言できます。

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

プログラミング ガイドの [async main](../programming-guide/main-and-command-args/index.md) トピックに詳細があります。

## <a name="default-literal-expressions"></a>既定のリテラル式

既定のリテラル式は既定の値式の拡張版です。
これらの式によって変数が初期化され、既定値になります。 以前は次のように記述していました。

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

それが今では、初期化の右項で種類を省略できるようになりました。

```csharp
Func<string, bool> whereClause = default;
```

この拡張の詳細は、C# プログラミング ガイドの[既定の値式](../programming-guide/statements-expressions-operators/default-value-expressions.md)に関するトピックにあります。

この拡張では、[既定のキーワード](../language-reference/keywords/default.md)の解析ルールも一部変更されています。

## <a name="inferred-tuple-element-names"></a>推論されたタプル要素の名前

この機能は、C# 7.0 で導入されたタプル機能の小規模拡張です。 タプルを何度初期化しても、代入の右項に使用される変数は、タプル要素に使用するものと同じ名前になります。

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

タプル要素の名前は、C# 7.1 でタプルの初期化に使用される変数から推測できます。

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

この機能の詳細については、[タプル](../tuples.md)に関するトピックを参照してください。

## <a name="reference-assembly-generation"></a>参照アセンブリ生成

*参照専用アセンブリ*を生成する新しい 2 つのコンパイラ オプション [/refout](../language-reference/compiler-options/refout-compiler-option.md) と [/refonly](../language-reference/compiler-options/refonly-compiler-option.md) があります。
リンク先のトピックには、オプションと参照アセンブリに関する詳細があります。

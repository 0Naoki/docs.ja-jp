---
title: ulong キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
ms.openlocfilehash: 97db22612e900658746f40cd117ff941135027a1
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235021"
---
# <a name="ulong-c-reference"></a>ulong (C# リファレンス)

`ulong` キーワードは、次の表に示されたサイズと範囲に従って値を格納する整数型を示します。

|型|範囲|サイズ|.NET 型|
|----------|-----------|----------|-------------------------|
|`ulong`|0 ～ 18,446,744,073,709,551,615|符号なし 64 ビット整数|<xref:System.UInt64?displayProperty=nameWithType>|

## <a name="literals"></a>リテラル

`ulong` 変数を宣言し、10 進リテラル、16 進リテラル、または (C# 7.0 以降) バイナリ リテラルを割り当てることによって初期化できます。  整数リテラルが `ulong` の範囲外にある場合 (つまり、<xref:System.UInt64.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.UInt64.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。

次の例では、整数 7,934,076,125 を 10 進リテラル、16 進リテラル、バイナリ リテラルで表したものが、`ulong` 値に割り当てられています。

[!code-csharp[ulong](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]

> [!NOTE]
> 16 進リテラルを表すにはプレフィックス `0x` または `0X` を使い、バイナリ リテラルを表すにはプレフィックス `0b` または `0B` を使います。 10 進リテラルには、プレフィックスはありません。

C# 7.0 以降では、読みやすさを強化するためにいくつかの機能が追加されています。

- C# 7.0 では、桁区切り記号としてアンダースコア文字 (`_`) が使用できます。
- C# 7.2 では、プレフィックスの後に、`_` をバイナリまたは 16 進リテラルの桁区切り記号として使用できます。 10 進リテラルは先頭にアンダー スコアを持つことはできません。

以下にいくつか例を示します。

[!code-csharp[long](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]

整数リテラルには、型を表すサフィックスを含めることもできます。 サフィックス `UL` または `ul` は、数値リテラルを `ulong` 値として明確に示します。 リテラル値が <xref:System.Int64.MaxValue?displayProperty=nameWithType> を超える場合、`L` サフィックスは `ulong` を表します。 また、リテラル値が <xref:System.UInt32.MaxValue?displayProperty=nameWithType> を超える場合、`U` または `u` サフィックスは `ulong` を表します。 次の例では、`ul` サフィックスを使って long 整数を示しています。

[!code-csharp[ulsuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

サフィックスがない整数リテラルの型は、以下の型のうちその値を表すことができる最初のものになります。

1. [int](int.md)
2. [uint](uint.md)
3. [long](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a>コンパイラのオーバーロード解決

サフィックスは、オーバーロードされたメソッドの呼び出しでよく使用されます。 たとえば、`ulong` パラメーターと [int](int.md) パラメーターを使用するオーバーロードされたメソッドがあるとします。

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ulong l) {}
```

サフィックスを `ulong` パラメーターと共に使用すると、正しい型が呼び出されます。次に例を示します。

```csharp
SampleMethod(5);    // Calling the method with the int parameter
SampleMethod(5UL);  // Calling the method with the ulong parameter
```

## <a name="conversions"></a>変換

`ulong` から [float](float.md)、[double](double.md)、[decimal](decimal.md) への暗黙の型変換が組み込まれています。

`ulong` から整数型への暗黙的な変換は行われません。 たとえば、次の代入ステートメントは、明示的なキャストを使用しない場合、コンパイル エラーになります。

```csharp
long long1 = 8UL;   // Error: no implicit conversion from ulong
```

[byte](byte.md)、[ushort](ushort.md)、[uint](uint.md)、または [char](char.md) から `ulong` への、定義済みの暗黙的な変換が組み込まれています。

浮動小数点型から `ulong` への暗黙の型変換はありません。 たとえば、次のステートメントは、明示的なキャストを使用しない場合、コンパイラ エラーになります。

```csharp
// Error -- no implicit conversion from double:
ulong x = 3.0;
// OK -- explicit conversion:
ulong y = (ulong)3.0;
```

浮動小数点型と整数型の混在する算術式の詳細については、「[float](float.md)」と「[double](double.md)」を参照してください。

暗黙的な数値変換規則について詳しくは、「[暗黙的な数値変換の一覧表](implicit-numeric-conversions-table.md)」をご覧ください。

## <a name="c-language-specification"></a>C# 言語仕様

詳細については、「[C# 言語仕様](../language-specification/index.md)」の[整数型](~/_csharplang/spec/types.md#integral-types)に関するセクションを参照してください。 言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。

## <a name="see-also"></a>関連項目

- <xref:System.UInt64>
- [C# リファレンス](../index.md)
- [C# プログラミング ガイド](../../programming-guide/index.md)
- [C# のキーワード](index.md)
- [整数型の一覧表](integral-types-table.md)
- [組み込み型の一覧表](built-in-types-table.md)
- [暗黙的な数値変換の一覧表](implicit-numeric-conversions-table.md)
- [明示的な数値変換の一覧表](explicit-numeric-conversions-table.md)

---
title: 整数数値型 - C# リファレンス
description: 各整数数値型の範囲、ストレージ サイズ、および使用方法について説明します。
ms.date: 10/22/2019
f1_keywords:
- byte
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- sbyte
- short
- short_CSharpKeyword
- ushort
- ushort_CSharpKeyword
- int_CSharpKeyword
- int
- uint
- uint_CSharpKeyword
- long_CSharpKeyword
- long
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
- byte keyword [C#]
- sbyte keyword [C#]
- short keyword [C#]
- ushort keyword [C#]
- int keyword [C#]
- uint keyword [C#]
- long keyword [C#]
- ulong keyword [C#]
ms.openlocfilehash: c255711e4b165fdca27d50c6bd0f2debfe15ae25
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773867"
---
# <a name="integral-numeric-types--c-reference"></a>整数数値型 (C# リファレンス)

**整数数値型**は**単純型**のサブセットであり、[*リテラル*](#integer-literals)を使用して初期化できます。 すべての整数型は、値型でもあります。 すべての整数数値型では、[算術](../operators/arithmetic-operators.md)、[ビット論理](../operators/bitwise-and-shift-operators.md)、[比較](../operators/comparison-operators.md)、[等値](../operators/equality-operators.md)演算子がサポートされています。

## <a name="characteristics-of-the-integral-types"></a>整数型の特性

C# では、次の定義済みの整数型がサポートされています。

|C# 型/キーワード|範囲|サイズ|.NET 型|
|----------|-----------|----------|-------------|
|`sbyte`|-128 ～ 127|符号付き 8 ビット整数|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|0 ～ 255|符号なし 8 ビット整数|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|-32,768 ～ 32,767|符号付き 16 ビット整数|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|0 ～ 65,535|符号なし 16 ビット整数|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|-2,147,483,648 ～ 2,147,483,647|符号付き 32 ビット整数|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|0 ～ 4,294,967,295|符号なし 32 ビット整数|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|-9,223,372,036,854,775,808 から 9,223,372,036,854,775,807|符号付き 64 ビット整数|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|0 ～ 18,446,744,073,709,551,615|符号なし 64 ビット整数|<xref:System.UInt64?displayProperty=nameWithType>|

上の表で、左端の列にある各 C# 型のキーワードは、対応する .NET 型の別名です。 これらは交換可能です。 たとえば、次の宣言では同じ型の変数が宣言されています。

```csharp
int a = 123;
System.Int32 b = 123;
```

各整数型の既定値はゼロ (`0`) です。 各整数型には、その型の最小値と最大値を指定する `MinValue` および `MaxValue` 定数があります。

<xref:System.Numerics.BigInteger?displayProperty=nameWithType> 構造体を使用して、上限や下限のない符号付き整数を表します。

## <a name="integer-literals"></a>整数リテラル

次の整数リテラルがあります。

- "*10 進*": プレフィックスなし
- "*16 進*": `0x` または `0X` プレフィックスを使用します
- "*バイナリ*": `0b` または `0B` プレフィックスを使用します (C# 7.0 以降で使用できます)

次のコードは、それぞれの例を示しています。

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

前述の例は、C# 7.0 以降でサポートされている "*桁区切り記号*" としての `_` の使用法も示しています。 数字区切り記号は、あらゆる種類の数値リテラルで使用できます。

整数リテラルの型は、そのサフィックスによって次のように決まります。

- サフィックスがないリテラルの型は、`int`、`uint`、`long`、`ulong` の型のうちその値を表すことができる最初のものになります。
- リテラルのサフィックスが `U` または `u` の場合、その型は、`uint`、`ulong` の型のうちその値を表すことができる最初のものになります。
- リテラルのサフィックスが `L` または `l` の場合、その型は、`long`、`ulong` の型のうちその値を表すことができる最初のものになります。

  > [!NOTE]
  > 小文字の `l` はサフィックスとして使用できます。 ただし、文字の `l` は数字の `1` と混同しやすいため、コンパイラから警告が出されます。 わかりやすくするために `L` を使用してください。

- リテラルのサフィックスが `UL`、`Ul`、`uL`、`ul`、`LU`、`Lu`、`lU`、または `lu` の場合、その型は `ulong` です。

整数リテラルで表される値が <xref:System.UInt64.MaxValue?displayProperty=nameWithType> を超えると、コンパイル エラー [CS1021](../../misc/cs1021.md) が発生します。

整数リテラルの決定された型が `int` で、その値が変換先の型の範囲内にある場合、リテラルで表される値は暗黙的に `sbyte`、`byte`、`short`、`ushort`、`uint`、または `ulong` に変換されます。

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

前の例で示したように、リテラルの値が変換先の型の範囲内にない場合、コンパイラ エラー [CS0031](../../misc/cs0031.md) が発生します。

また、キャストを使用して、整数リテラルによって表される値を、指定された型のリテラル以外の型に変換することもできます。

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a>変換

任意の整数数値型を他の整数数値型に変換することができます。 変換先の型に変換元の型のすべての値を格納できる場合、変換は暗黙的に実行されます。 それ以外の場合、明示的な変換を呼び出すには、[キャスト演算子 `()`](../operators/type-testing-and-cast.md#cast-operator-) を使用する必要があります。 詳細については、「[Built-in numeric conversions](numeric-conversions.md)」(組み込みの数値変換) を参照してください。

## <a name="c-language-specification"></a>C# 言語仕様

詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。

- [整数型](~/_csharplang/spec/types.md#integral-types)
- [整数リテラル](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [組み込み型の一覧表](../keywords/built-in-types-table.md)
- [浮動小数点型](floating-point-numeric-types.md)
- [数値結果テーブルの書式設定](../keywords/formatting-numeric-results-table.md)
- [.NET における数値](../../../standard/numerics.md)

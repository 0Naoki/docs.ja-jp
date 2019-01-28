---
title: bool キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 958b58b31193dbf4c03709e4ab7ba38f7f30e0ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590483"
---
# <a name="bool-c-reference"></a>bool (C# リファレンス)

`bool` キーワードは <xref:System.Boolean?displayProperty=nameWithType> の別名です。 ブール値 ([true](true-literal.md) と [false](false-literal.md)) を格納する変数を宣言するために使われます。

> [!NOTE]
> 値 `null` も格納できるブール変数が必要な場合は、`bool?` を使います。 詳細については、「[Null 許容型の使用](../../programming-guide/nullable-types/using-nullable-types.md)」の記事の「[bool? 型](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type)」セクションを参照してください。

## <a name="literals"></a>リテラル

`bool` 変数にはブール値を代入できます。 また、`bool` として評価される式も `bool` 変数に代入できます。

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

`bool` 変数の既定値は `false` です。 `bool?` 変数の既定値は `null` です。

## <a name="conversions"></a>変換

C++ では、`bool` 型の値を `int` 型の値に変換できます。つまり、`false` はゼロと同等であり、`true` はゼロ以外の値と同等です。 C# では、`bool` 型と他の型の間に変換はありません。 たとえば、次の `if` ステートメントは C# では無効です。

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

`int` 型の変数をテストするには、0 などの値と明示的に比較する必要があります。次はその例です。

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a>例

この例のプログラムは、キーボードから文字された文字がアルファベットかどうかを調べます。 アルファベットである場合は、小文字か大文字かを調べます。 こうしたチェックは <xref:System.Char.IsLetter%2A> と <xref:System.Char.IsLower%2A> で実行され、どちらも `bool` 型を返します。

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a>C# 言語仕様

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>関連項目

- [C# リファレンス](../../../csharp/language-reference/index.md)
- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)
- [C# のキーワード](../../../csharp/language-reference/keywords/index.md)
- [整数型の一覧表](../../../csharp/language-reference/keywords/integral-types-table.md)
- [組み込み型の一覧表](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [暗黙的な数値変換の一覧表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [明示的な数値変換の一覧表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

---
title: implicit (C# リファレンス)
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: 70379136fd4b14403eac919ac15590250b17b416
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44273260"
---
# <a name="implicit-c-reference"></a>implicit (C# リファレンス)

`implicit` キーワードを使用して、暗黙のユーザー定義型変換演算子を宣言します。 変換を実行してもデータ損失が発生しないことが保証されている場合に、ユーザー定義型とその他の型との間の暗黙の変換を有効にするために使用します。

## <a name="example"></a>例

[!code-csharp[csrefKeywordsConversion#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#5)]

暗黙の変換では不要なキャストを省略できるため、ソース コードが読みやすくなります。 ただし、暗黙の変換では、一方の型からもう一方の型に明示的にキャストする必要がないため、予期しない結果が生じないように注意する必要があります。 プログラマーが意識しなくても安全に使用できるように、通常、暗黙の変換演算子は、例外をスローしたり情報を失ったりしてはなりません。 このような条件を満たすことができない変換演算子は、`explicit` でマークする必要があります。 詳細については、「[変換演算子の使用](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)」を参照してください。

## <a name="c-language-specification"></a>C# 言語仕様

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)  
- [C# プログラミング ガイド](../../programming-guide/index.md)  
- [C# のキーワード](index.md)  
- [explicit](explicit.md)  
- [演算子 (C# リファレンス)](operator.md)  
- [方法: 構造体間にユーザー定義の変換を実装する](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

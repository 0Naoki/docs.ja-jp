---
title: 暗黙的に型指定される配列 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicitly-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: 36ca18adc392643107b43a947656846f3b94a2eb
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597349"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a>暗黙的に型指定される配列 (C# プログラミング ガイド)

配列インスタンスの型が、配列初期化子で指定された要素から推論される暗黙的に型指定された配列を作成できます。 暗黙的に型指定された変数の規則は、暗黙的に型指定された配列にも適用されます。 詳細については、「[暗黙的に型指定されるローカル変数](../classes-and-structs/implicitly-typed-local-variables.md)」を参照してください。

暗黙的に型指定された配列は通常、匿名型、オブジェクト、コレクション初期化子と共にクエリ式で使用されます。

次の例では、暗黙的に型指定された配列を作成する方法を示します。

[!code-csharp[csProgGuideLINQ#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#37)]

前の例で、暗黙的に型指定された配列では、初期化ステートメントの左側では角かっこが使用されていないことに注意してください。 また、ジャグ配列は、1 次元の配列と同じように `new []` を使用して初期化されます。

## <a name="implicitly-typed-arrays-in-object-initializers"></a>オブジェクト初期化子で暗黙的に型指定された配列

配列を含む匿名型を作成するときには、型のオブジェクトの初期化子で配列を暗黙的に型指定する必要があります。 次の例では、`contacts` は、匿名型の暗黙的に型指定された配列で、それぞれが `PhoneNumbers` という名前の配列を含んでいます。 `var` キーワードは、オブジェクト初期化子内で使用されないことに注意してください。

[!code-csharp[csProgGuideLINQ#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#38)]

## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../index.md)
- [暗黙的に型指定されるローカル変数](../classes-and-structs/implicitly-typed-local-variables.md)
- [配列](./index.md)
- [匿名型](../classes-and-structs/anonymous-types.md)
- [オブジェクト初期化子とコレクション初期化子](../classes-and-structs/object-and-collection-initializers.md)
- [var](../../language-reference/keywords/var.md)
- [LINQ クエリ式](../linq-query-expressions/index.md)

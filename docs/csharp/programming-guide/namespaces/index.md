---
title: 名前空間 (C# プログラミング ガイド)
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: c4011092a6c605137053b544d4b9f14cce2fdb4c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2018
ms.locfileid: "45624555"
---
# <a name="namespaces-c-programming-guide"></a>名前空間 (C# プログラミング ガイド)

C# プログラミングでは、名前空間が 2 つの方法でよく使用されます。 最初の方法では、次のように .NET Framework で名前空間を使用して、その多くのクラスを整理します。  
  
[!code-csharp[csProgGuide#22](../inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
`System` は名前空間で、`Console` はその名前空間内のクラスです。 以下の例のように、`using` キーワードを使用できるため、完全な名前は必要ありません。  
  
[!code-csharp[csProgGuide#1](../inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
[!code-csharp[csProgGuide#25](../inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
詳細については、「[using ディレクティブ](../../language-reference/keywords/using-directive.md)」をご覧ください。  
  
2 つ目の方法では、独自の名前空間を宣言します。これは、より大きなプログラミング プロジェクトでクラス名とメソッド名のスコープを制御するのに役立ちます。 名前空間を宣言するには、以下の例のように、[namespace](../../language-reference/keywords/namespace.md) キーワードを使用します。  
  
[!code-csharp[csProgGuideNamespaces#6](codesnippet/CSharp/index_4.cs)]

名前空間の名前を、有効な C# の[識別子名](../inside-a-program/identifier-names.md)にする必要があります。

## <a name="namespaces-overview"></a>名前空間の概要  

名前空間には次の特徴があります。  
  
- 大きなコード プロジェクトを整理します。  
- `.` 演算子を使用して、区切られます。  
- `using directive` を使用すると、クラスごとに名前空間の名前を指定する必要がなくなります。  
- `global` 名前空間は "ルート" 名前空間です。`global::System` は常に .NET Framework 名前空間の `System` を参照します。  

## <a name="c-language-specification"></a>C# 言語仕様

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>参照

- [名前空間の使用](using-namespaces.md)
- [方法: グローバル名前空間エイリアスを使用する](how-to-use-the-global-namespace-alias.md)
- [方法: My 名前空間を使用する](how-to-use-the-my-namespace.md)
- [C# プログラミング ガイド](../index.md)  
- [識別子名](../inside-a-program/identifier-names.md)
- [名前空間キーワード](../../language-reference/keywords/namespace-keywords.md)  
- [using ディレクティブ](../../language-reference/keywords/using-directive.md)  
- [:: 演算子](../../language-reference/operators/namespace-alias-qualifer.md)  
- [。演算子](../../language-reference/operators/member-access-operator.md)
>>>>>>> 識別子の名前指定の規則の追加

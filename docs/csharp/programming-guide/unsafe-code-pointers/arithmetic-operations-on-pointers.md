---
title: ポインターに対する算術演算 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: 94e5d3fbf250f8b99560f83e14c063142ac7ad29
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242101"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a>ポインターに対する算術演算 (C# プログラミング ガイド)
このトピックでは、算術演算子 `+` と `-` を使用したポインター操作について説明します。  
  
> [!NOTE]
>  void ポインターには、算術演算を実行できません。  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a>ポインターに対する数値の加算と減算  
 型が [int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md)、[ulong](../../../csharp/language-reference/keywords/ulong.md) のいずれかである値 `n` をポインターに加算できます。 `p` が型 `pointer-type*` のポインターである場合、結果の `p+n` は `p` のアドレスに `n * sizeof(pointer-type)` を加算した結果のポインターです。 同様に、`p-n` は `p` のアドレスから `n * sizeof(pointer-type)` を減算した結果を表すポインターです。  
  
## <a name="subtracting-pointers"></a>ポインターの減算  
 同じ型のポインターを減算することもできます。 結果は常に `long` 型になります。 たとえば場合、`p1` と `p2` が `pointer-type*` 型のポインターである場合、式 `p1-p2` の結果は次のようになります。  
  
 `((long)p1 - (long)p2)/sizeof(pointer-type)`  
  
 算術演算がポインターのドメインをオーバーフローしても、例外は生成されません。生じる結果は実装によって異なります。  
  
## <a name="example"></a>例  
 [!code-csharp[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## <a name="c-language-specification"></a>C# 言語仕様  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [アンセーフ コードとポインター](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [ポインター式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [C# 演算子](../../../csharp/language-reference/operators/index.md)  
- [ポインターの操作](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [ポインター型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [型](../../../csharp/language-reference/keywords/types.md)  
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
- [fixed ステートメント](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)

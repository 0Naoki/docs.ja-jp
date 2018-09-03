---
title: unsafe (C# リファレンス)
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: b4615021a4fc3391ac0ae703b6c97301b44aa60e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43389589"
---
# <a name="unsafe-c-reference"></a>unsafe (C# リファレンス)
`unsafe` キーワードは、ポインターに関連するすべての操作に必要な、unsafe コンテキストを示します。 詳しくは、「[アンセーフ コードとポインター](../../../csharp/programming-guide/unsafe-code-pointers/index.md)」をご覧ください。  
  
 `unsafe` 修飾子は、型またはメンバーの宣言で使用できます。 そのため、型やメンバーの全体的なテキスト範囲が unsafe コンテキストと見なされます。 たとえば、次に示すのは、`unsafe` 修飾子を使用して宣言されたメソッドです。  
  
```csharp  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 unsafe コンテキストのスコープはパラメーター リストからメソッドの末尾までなので、ポインターはパラメーター リストでも使用できます。  
  
```csharp  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 また、unsafe ブロックを使用して、そのブロック内で unsafe コードを使用できるようにすることもできます。 例:  
  
```csharp  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 unsafe コードをコンパイルするには、 [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) コンパイラ オプションを指定する必要があります。 unsafe コードは、共通言語ランタイムでは検証できません。  
  
## <a name="example"></a>例  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a>C# 言語仕様  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>参照

- [C# リファレンス](../../../csharp/language-reference/index.md)  
- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [C# のキーワード](../../../csharp/language-reference/keywords/index.md)  
- [fixed ステートメント](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [アンセーフ コードとポインター](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [固定サイズ バッファー](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)

---
title: ジェネリックと属性 (C# プログラミング ガイド)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 0fe2d61001584aa7c175500bfa754b2ae2244660
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2018
ms.locfileid: "45675536"
---
# <a name="generics-and-attributes-c-programming-guide"></a>ジェネリックと属性 (C# プログラミング ガイド)
属性は、非ジェネリック型の場合と同様に、ジェネリック型に適用できます。 属性の適用については、「[属性](../../../csharp/programming-guide/concepts/attributes/index.md)」を参照してください。  
  
 カスタム属性は、型引数が与えられないオープン ジェネリック型と、すべての型パラメーターに引数が与えられる、構築クローズ ジェネリック型のみ参照が許可されます。  
  
 次の例では、このカスタム属性が使用されています。  
  
 [!code-csharp[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]  
  
 属性は、オープン ジェネリック型を参照できます。  
  
 [!code-csharp[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]  
  
 適切な数のコンマを利用し、複数の型パラメーターを指定します。 この例では、`GenericClass2` には 2 つの型パラメーターがあります。  
  
 [!code-csharp[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]  
  
 属性は、構築クローズ ジェネリック型を参照できます。  
  
 [!code-csharp[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]  
  
 ジェネリック型パラメーターを参照する属性は、コンパイル時エラーを引き起こします。  
  
 [!code-csharp[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]  
  
 ジェネリック型は <xref:System.Attribute> から継承できません。  
  
 [!code-csharp[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]  
  
 実行時にジェネリック型または型パラメーターに関する情報を取得するには、<xref:System.Reflection> のメソッドを利用できます。 詳細については、「[ジェネリックとリフレクション](../../../csharp/programming-guide/generics/generics-and-reflection.md)」を参照してください。  
  
## <a name="see-also"></a>参照

- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [ジェネリック](../../../csharp/programming-guide/generics/index.md)  
- [属性](../../../../docs/standard/attributes/index.md)

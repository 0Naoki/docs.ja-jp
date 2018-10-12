---
title: ジェネリックの概要 (C# プログラミング ガイド)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
ms.openlocfilehash: 17f4c67792732be7a678ec858b6627fa712194c5
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861288"
---
# <a name="introduction-to-generics-c-programming-guide"></a>ジェネリックの概要 (C# プログラミング ガイド)
ジェネリックのクラスとメソッドは、非ジェネリックでは不可能な方法で、再利用性、タイプ セーフ、効率性を同時に実現しています。 ジェネリックは、コレクションとそれを操作するメソッドとともに使用されるのが通常です。 .NET Framework クラス ライブラリのバージョン 2.0 には、いくつかの新しいジェネリック ベースのコレクション クラスを含む新しい名前空間、<xref:System.Collections.Generic> が用意されています。 .NET Framework 2.0 以降を対象とするすべてのアプリケーションでは、<xref:System.Collections.ArrayList> などの以前の非ジェネリック コレクション クラスの代わりに、新しいジェネリック コレクション クラスを使用することをお勧めします。 詳細については、「[.NET のジェネリック](../../../standard/generics/index.md)」を参照してください。  
  
 もちろん、カスタムのジェネリック型やジェネリック メソッドを作成して、タイプ セーフで効率的な独自の汎用ソリューションや設計パターンを実現することもできます。 次のコード例では、デモンストレーション用の簡単なジェネリックのリンク リスト クラスを示します。 (通常は、独自のクラスを作成するのではなく、.NET Framework クラス ライブラリに用意されている <xref:System.Collections.Generic.List%601> クラスを使用してください。)この例では、通常、具体的な型を使用して、リストに格納する項目の型を示す場面で、型パラメーター `T` を使用しています。 このパラメーターは、次のように使用されています。  
  
-   `AddHead` メソッドのメソッド パラメーターの型として使用。  
  
-   入れ子になった `Node` クラスの `Data` プロパティの戻り値の型として使用。  
  
-   入れ子になったクラスのプライベート メンバー `data` の型として使用。  
  
 T は、入れ子になった `Node` クラスで使用できることに注意してください。 `GenericList<T>` が `GenericList<int>` のような具象型でインスタンス化されると、`T` の部分はそれぞれ `int` に置き換えられます。  
  
 [!code-csharp[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_1.cs)]  
  
 次のコード例では、クライアント コードでジェネリックの `GenericList<T>` クラスを使用して、整数のリストを作成する方法を示しています。 このコードの型引数を変更するだけで、文字列やその他の任意のカスタム型のリストを作成するように簡単に修正できます。  
  
 [!code-csharp[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_2.cs)]  
  
## <a name="see-also"></a>参照

- <xref:System.Collections.Generic>  
- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [ジェネリック](../../../csharp/programming-guide/generics/index.md)

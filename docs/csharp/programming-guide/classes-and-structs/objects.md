---
title: "オブジェクト (C# プログラミング ガイド) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- objects [C#], about objects
- variables [C#]
ms.assetid: af4a5230-fbf3-4eea-95e1-8b883c2f845c
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a5ed524a1b17f7be8903f998cbd732594faab831
ms.openlocfilehash: fe548eb5d520945e3f0d52750bbf89935947116e
ms.contentlocale: ja-jp
ms.lasthandoff: 05/15/2017

---
# <a name="objects-c-programming-guide"></a>オブジェクト (C# プログラミング ガイド)
クラスまたは構造体の定義は、型の動作を指定する設計図に似ています。 オブジェクトは基本的に、設計図に従って割り当てられて構成されたメモリのブロックです。 プログラムでは、同じクラスのオブジェクトを多数作成できます。 オブジェクトはインスタンスとも呼ばれ、名前付きの変数または配列やコレクションに格納できます。 クライアント コードとは、これらの変数を使ってメソッドを呼び出し、オブジェクトのパブリック プロパティにアクセスするコードです。 C# などのオブジェクト指向言語では、一般的なプログラムは動的に対話する複数のオブジェクトで構成されています。  
  
> [!NOTE]
>  静的な型の動作方法は、ここで説明する動作方法とは異なります。 詳細については、「[静的クラスと静的クラス メンバー](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)」を参照してください。  
  
## <a name="struct-instances-vs-class-instances"></a>構造体インスタンスとクラス インスタンス  
 クラスは参照型であるため、クラスのオブジェクトの変数は、マネージ ヒープ上のオブジェクトのアドレスへの参照を保持します。 同じ型の 2 番目のオブジェクトが最初のオブジェクトに割り当てられた場合、両方の変数がそのアドレスにあるオブジェクトを参照します。 この点については、後で詳しく説明します。  
  
 クラスのインスタンスは、[new 演算子](../../../csharp/language-reference/keywords/new-operator.md)を使って作成されます。 次の例では、`Person` が型で、`person1` と `person 2` がその型のインスタンスつまりオブジェクトです。  
  
 [!code-cs[csProgGuideStatements#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_1.cs)]  
  
 構造体は値型であるため、構造体オブジェクトの変数はオブジェクト全体のコピーを保持します。 構造体のインスタンスも `new` 演算子を使って作成できますが、次の例で示すように、これは必要ではありません。  
  
 [!code-cs[csProgGuideStatements#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_2.cs)]  
  
 `p1` と `p2` のメモリはどちらも、スレッドのスタックに割り当てられます。 そのメモリは、それが宣言されている型またはメソッドと共に解放されます。 これは、割り当て時に構造体がコピーされる理由の 1 です。 これに対し、クラスのインスタンスに割り当てられたメモリは、そのオブジェクトに対するすべての参照がスコープ外になると、共通言語ランタイムによって自動的に解放 (ガベージ コレクション) されます。 C++ のようにクラスのオブジェクトを確定的に破棄することはできません。 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] でのガベージ コレクションについて詳しくは、「[ガベージ コレクション](../../../standard/garbage-collection/index.md)」をご覧ください。  
  
> [!NOTE]
>  マネージ ヒープ上のメモリの割り当てと解放は、共通言語ランタイムにおいて高度に最適化されています。 ほとんどの場合、ヒープへのクラス インスタンスの割り当てと、スタックへの構造体インスタンスの割り当てに、パフォーマンス コストの点で大きな違いはありません。  
  
## <a name="object-identity-vs-value-equality"></a>オブジェクト ID と値の等価性  
 2 つのオブジェクトが等しいかどうかを比較するときは、最初に、2 つの変数がメモリ内の同じオブジェクトを表しているかどうかを知りたいのか、それともオブジェクトの 1 つ以上のフィールドの値が等しいかどうかを知りたいのかを、区別する必要があります。 値を比較する場合は、オブジェクトが値型 (構造体) のインスタンスか、または参照型 (クラス、デリゲート、配列) のインスタンスかを、検討する必要があります。  
  
-   クラスの 2 つのインスタンスがメモリ内の同じ場所を参照しているかどうか (つまり、同じ *ID* か) を調べるには、静的な <xref:System.Object.Equals%2A> メソッドを使います (<xref:System.Object?displayProperty=fullName> は、ユーザー定義の構造体やクラスを含む、すべての値型と参照型の暗黙の基底クラスです)。  
  
-   2 つの構造体インスタンスのインスタンス フィールドが同じ値を持つかどうかを調べるには、<xref:System.ValueType.Equals%2A?displayProperty=fullName> メソッドを使います。 すべての構造体は <xref:System.ValueType?displayProperty=fullName> を暗黙的に継承するので、次の例で示すように、オブジェクトで直接メソッドを呼び出します。  
  
 [!code-cs[csProgGuideStatements#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_3.cs)]  
  
 <xref:System.ValueType?displayProperty=fullName> での `Equals` の実装は、構造体に存在するフィールドを特定できる必要があるため、リフレクションを使います。 独自の構造体を作成するときは、`Equals` メソッドをオーバーライドして、独自の型に固有の効率的な等値アルゴリズムを提供します。  
  
-   クラスの 2 つのインスタンスのフィールドの値が等しいかどうかを調べるには、<xref:System.Object.Equals%2A> メソッドまたは [== 演算子](../../../csharp/language-reference/operators/equality-comparison-operator.md)を使用できる場合があります。 ただし、この方法を使用できるのは、その型のオブジェクトにおける "等値" の意味のカスタム定義が、クラスのオーバーライドまたはオーバーロードによって提供されている場合だけです。 クラスは、<xref:System.IEquatable%601> インターフェイスまたは <xref:System.Collections.Generic.IEqualityComparer%601> インターフェイスを実装することもできます。 どちらのインターフェイスも、値の等価性をテストするために使うことができるメソッドを提供します。 `Equals` をオーバーライドする独自のクラスを設計するときは、「[方法: 型の値の等価性を定義する](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md)」および「<xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>」に記載されているガイドラインに従ってください。  
  
## <a name="related-sections"></a>関連項目  
 詳細情報  
  
-   [クラス](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [構造体](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [コンストラクター](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [ファイナライザー](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
  
-   [イベント](../../../csharp/programming-guide/events/index.md)  
  
## <a name="see-also"></a>関連項目  
 [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)   
 [object](../../../csharp/language-reference/keywords/object.md)   
 [継承](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [class](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)   
 [New 演算子](../../../csharp/language-reference/keywords/new-operator.md)   
 [共通型システム](../../../standard/base-types/common-type-system.md)

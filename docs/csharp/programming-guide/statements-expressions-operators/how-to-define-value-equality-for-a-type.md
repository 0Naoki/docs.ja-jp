---
title: "方法: 型の値の等価性を定義する (C# プログラミング ガイド) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- overriding Equals method [C#]
- object equivalence [C#]
- Equals method [C#] , overriding
- value equality [C#]
- equivalence [C#]
ms.assetid: 4084581e-b931-498b-9534-cf7ef5b68690
caps.latest.revision: 15
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 33b2ab2252fac8442caa7b2f3e9b5b311cc0f9b6
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-define-value-equality-for-a-type-c-programming-guide"></a>方法: 型の値の等価性を定義する (C# プログラミング ガイド)
クラスまたは構造体を定義する場合は、型に値の等価性 (同値) のカスタム定義を作成することが有用かどうかを判断します。 通常、値の等価性を実装するのは、その型のオブジェクトがある種のコレクションに追加されることが想定されている場合、または、そのオブジェクトの主な目的が一連のフィールドまたはプロパティを格納することである場合です。 値の等価性は、型のすべてのフィールドおよびプロパティの比較に基づいて定義できます。また、サブセットに基づいて定義することもできます。 ただし、いずれの場合も、クラスおよび構造体の両方について、等価性を保証する 5 つの条件に従って実装する必要があります。  
  
1.  x.`Equals`(x) は `true.` を返します。これは再帰プロパティと呼ばれます。  
  
2.  x.`Equals`(y) は、y.`Equals`(x) と同じ値を返します。 これは対照プロパティと呼ばれます。  
  
3.  (x.`Equals`(y) && y.`Equals`(z)) が `true` を返す場合は、x.`Equals`(z) も `true` を返します。 これは推移的プロパティと呼ばれます。  
  
4.  x.`Equals`(y) が連続して呼び出された場合は、x および y によって参照されるオブジェクトが変更されていない限り、同じ値を返します。  
  
5.  x.`Equals`(null) は `false` を返します。 ただし、null.Equals(null) は例外をスローするため、上の 2 番目の規則には従っていません。  
  
 構造体を定義すると、<xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> メソッドの <xref:System.ValueType?displayProperty=fullName> オーバーライドから継承された値の等価性が既定で実装されます。 この実装では、リフレクションを使用して、型のフィールドとプロパティをすべて調べます。 この実装によって正しい結果が生成されますが、その型専用に記述したカスタム実装と比較すると、処理にかなり時間がかかります。  
  
 値の等価性に関する実装の詳細は、クラスと構造体で異なりますが、 等価性を実装するための基本的な手順については、両方とも同じです。  
  
1.  [仮想](../../../csharp/language-reference/keywords/virtual.md) <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> メソッドをオーバーライドします。 ほとんどの場合、`bool Equals( object obj )` の実装には、<xref:System.IEquatable%601?displayProperty=fullName> インターフェイスの実装である型固有の `Equals` メソッドを呼び出すだけで済みます  (手順 2 を参照)。  
  
2.  型固有の `Equals` メソッドを指定して、<xref:System.IEquatable%601?displayProperty=fullName> インターフェイスを実装します。 ここで実際の等価性の比較を実行します。 たとえば、型のフィールドを 1 ～ 2 個だけ比較することで等価性を定義できます。 `Equals` から例外をスローしないでください。 クラスの場合に限り、このメソッドはクラスで宣言されているフィールドのみを調べます。 基底クラスに含まれるフィールドを調べるには、`base.Equals` を呼び出す必要があります  (<xref:System.Object> から直接継承された型である場合は、この呼び出しを行わないでください。<xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> の <xref:System.Object> 実装では参照の等価性チェックが実行されるためです)。  
  
3.  推奨、ただし省略可能: [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) 演算子および [!=](../../../csharp/language-reference/operators/not-equal-operator.md) 演算子をオーバーロードします。  
  
4.  値の等価性を持つ 2 つのオブジェクトによって同じハッシュ コードが生成されるように、<xref:System.Object.GetHashCode%2A?displayProperty=fullName> をオーバーライドします。  
  
5.  省略可能: "大なり" または "少なり" の定義をサポートするには、型に対して <xref:System.IComparable%601> インターフェイスを実装したうえで、[<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) 演算子および [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) 演算子をオーバーロードします。  
  
 次に示す最初の例は、クラスの実装です。 2 番目の例は、構造体の実装を示しています。  
  
## <a name="example"></a>例  
 次の例は、クラス (参照型) で値の等価性を実装する方法を示しています。  
  
 [!code-cs[csProgGuideStatements#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equality-for-a-type_1.cs)]  
  
 クラス (参照型) の場合、両方の <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> メソッドの既定の実装で、参照の等価性の比較は実行されますが、値の等価性のチェックは実行されません。 実装が仮想メソッドをオーバーライドする場合、その目的は、仮想メソッドに値の等価性のセマンティクスを提供することです。  
  
 `==` 演算子と `!=` 演算子は、オーバーロードされなくてもクラスで使用できます。 ただし、既定の動作として参照の等価性のチェックが実行されます。 クラスで `Equals` メソッドをオーバーロードする場合は、`==` 演算子と `!=` 演算子をオーバーロードすることをお勧めしますが、必須ではありません。  
  
## <a name="example"></a>例  
 次の例は、構造体 (値型) で値の等価性を実装する方法を示しています。  
  
 [!code-cs[csProgGuideStatements#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equality-for-a-type_2.cs)]  
  
 構造体の場合、<xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> (<xref:System.ValueType?displayProperty=fullName> でオーバーライドされるバージョン) の既定の実装で、リフレクションを使用して値の等価性のチェックが実行され、型のすべてのフィールドの値が比較されます。 実装が構造体の仮想 `Equals` メソッドをオーバーライドする場合、その目的は、値の等価性のチェックをより効率的に実行することと、オプションで、構造体のフィールドまたはプロパティの一部のサブセットに基づいて比較を行うことです。  
  
 [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) 演算子および [!=](../../../csharp/language-reference/operators/not-equal-operator.md) 演算子は、構造体が明示的にその演算子をオーバーロードしない限り、その構造体を操作できません。  
  
## <a name="see-also"></a>関連項目  
 [等価比較](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)   
 [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)


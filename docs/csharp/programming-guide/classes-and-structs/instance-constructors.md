---
title: インスタンス コンストラクター - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: e3ba825fcbf40e08a2cb4488de2bbed9257c2508
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592836"
---
# <a name="instance-constructors-c-programming-guide"></a>インスタンス コンストラクター (C# プログラミング ガイド)
インスタンス コンストラクターは、[new](../../../csharp/language-reference/keywords/new.md) 式を使って[クラス](../../../csharp/language-reference/keywords/class.md)のオブジェクトを作成するときに、インスタンス メンバー変数を作成および初期化するために使われます。 [静的](../../../csharp/language-reference/keywords/static.md)クラスを初期化する場合、または非静的クラスの静的変数を初期化する場合は、静的コンストラクターを定義する必要があります。 詳細については、「[静的コンストラクター](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)」を参照してください。  
  
 次に示すのは、インスタンス コンストラクターの例です。  
  
 [!code-csharp[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]  
  
> [!NOTE]
>  わかりやすくするため、このクラスにはパブリック フィールドが含まれています。 パブリック フィールドを使うと、プログラム内の任意の場所にある任意のメソッドが、制限も検証もなしにオブジェクトの内部動作にアクセスできるため、パブリック フィールドは推奨されるプログラミング手法ではありません。 データ メンバーは、一般にプライベートにする必要があり、クラスのメソッドとプロパティを介してのみアクセスする必要があります。  
  
 このインスタンス コンストラクターは、`Coords` クラスに基づくオブジェクトが作成されるたびに呼び出されます。 引数を受け取らないこのようなコンストラクターは、*既定のコンストラクター*と呼ばれます。 ただし、コンストラクターを追加すると便利な場合がよくあります。 たとえば、データ メンバーの初期値を指定できるコンストラクターを `Coords` クラスに追加できます。  
  
 [!code-csharp[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]  
  
 これにより、次のように、既定値または特定の初期値で `CoOrd` オブジェクトを作成できます。  
  
 [!code-csharp[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]  
  
 クラスにコンストラクターがない場合は、既定のコンストラクターが自動的に生成され、既定値を使ってオブジェクトのフィールドが初期化されます。 たとえば、[int](../../../csharp/language-reference/keywords/int.md) は 0 に初期化されます。 既定値について詳しくは、「[既定値の一覧表](../../../csharp/language-reference/keywords/default-values-table.md)」をご覧ください。 したがって、`Coords` クラスの既定のコンストラクターは、すべてのデータ メンバーをゼロに初期化するため、クラスの動作を変更することなくまとめて削除することができます。 複数のコンストラクターを使う完全な例は後の例 1 で、自動的に生成されたコンストラクターの例は例 2 で示します。  
  
 インスタンス コンストラクターを使って、基底クラスのインスタンス コンストラクターを呼び出すこともできます。 次のように、クラスのコンストラクターは、初期化子を使って基底クラスのコンストラクターを呼び出すことができます。  
  
 [!code-csharp[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]  
  
 この例では、`Circle` クラスは、半径と高さを表す値を、`Circle` の派生元である `Shape` によって提供されるコンストラクターに渡しています。 `Shape` と `Circle` を使う完全な例は、例 3 をご覧ください。  
  
## <a name="example-1"></a>例 1  
 次の例で示すクラスには、引数を持たないクラス コンストラクターと、2 つの引数を持つクラス コンストラクターがあります。  
  
 [!code-csharp[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]  
  
## <a name="example-2"></a>例 2  
 この例の `Person` クラスにはコンストラクターがありません。このような場合は、既定のコンストラクターが自動的に提供され、フィールドは既定値に初期化されます。  
  
 [!code-csharp[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]  
  
 `age` の既定値は `0`、`name` の既定値は `null` であることに注意してください。 既定値について詳しくは、「[既定値の一覧表](../../../csharp/language-reference/keywords/default-values-table.md)」をご覧ください。  
  
## <a name="example-3"></a>例 3  
 次の例では、基底クラスの初期化子の使い方を示します。 `Circle` クラスは汎用クラス `Shape` から派生し、`Cylinder` クラスは `Circle` クラスから派生しています。 各派生クラスのコンストラクターでは、その基底クラスの初期化子が使われています。  
  
 [!code-csharp[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]  
  
 基底クラスのコンストラクターの呼び出しに関する他の例については、「[virtual](../../../csharp/language-reference/keywords/virtual.md)」、「[override](../../../csharp/language-reference/keywords/override.md)」、「[base](../../../csharp/language-reference/keywords/base.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)
- [クラスと構造体](../../../csharp/programming-guide/classes-and-structs/index.md)
- [コンストラクター](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [ファイナライザー](../../../csharp/programming-guide/classes-and-structs/destructors.md)
- [static](../../../csharp/language-reference/keywords/static.md)

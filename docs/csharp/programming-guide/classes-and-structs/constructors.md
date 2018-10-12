---
title: コンストラクター (C# プログラミング ガイド)
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 3d07fe5f6164885a994838376887edccc260e291
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2018
ms.locfileid: "45593960"
---
# <a name="constructors-c-programming-guide"></a>コンストラクター (C# プログラミング ガイド)
[クラス](../../../csharp/language-reference/keywords/class.md)または[構造体](../../../csharp/language-reference/keywords/struct.md)を作成するたびに、コンストラクターが呼び出されます。 クラスまたは構造体には、異なる引数を取るコンストラクターが複数含まれていることがあります。 プログラマーはコンストラクターを利用することで、既定値を設定したり、インスタンス化を制限したり、柔軟で読みやすいコードを記述したりできます。 詳細と例については、「[コンストラクターの使用](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)」と「[インスタンス コンストラクター](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)」を参照してください。  

## <a name="default-constructors"></a>既定のコンストラクター
  
クラスにコンストラクターを指定しない場合、C# では既定でコンストラクターが 1 つ作成されます。そのコンストラクターによりオブジェクトがインスタンス化され、「[既定値の一覧表](../../../csharp/language-reference/keywords/default-values-table.md)」の一覧にある既定値にメンバー変数が設定されます。 構造体にコンストラクターを指定しない場合、C# では、*暗黙的既定コンストラクター*を利用し、「[既定値の一覧表](../../../csharp/language-reference/keywords/default-values-table.md)」の一覧にある既定値に値の型の各フィールドが自動的に初期化されます。 詳細と例については、「[インスタンス コンストラクター](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)」を参照してください。  

## <a name="constructor-syntax"></a>コンストラクターの構文

コンストラクターは、名前がその型の名前と同じメソッドです。 メソッド シグネチャには、メソッド名とそのパラメーター リストだけが含まれます。戻り値の型は含まれません。 次の例は、`Person` という名前のクラスのコンストラクターを示しています。

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

コンストラクターを 1 つのステートメントとして実装できる場合、[式の本体の定義](../statements-expressions-operators/expression-bodied-members.md)を利用できます。 次の例では、コンストラクターに *name* という名前の文字列パラメーターが 1 つある `Location` クラスが定義されています。 式の本体の定義により `locationName` フィールドに引数が割り当てられます。

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a>静的コンストラクター

前の例には、表示されるすべてのインスタンス コンストラクターがあり、それが新しいオブジェクトを作成します。 クラスまたは構造体には静的コンストラクターを与えることもできます。静的コンストラクターは型の静的メンバーを初期化します。  静的コンストラクターにはパラメーターがありません。 静的コンストラクターを指定して静的フィールドを初期化しない場合、C# コンパイラは、「[既定値の一覧表](../../../csharp/language-reference/keywords/default-values-table.md)」の一覧にある既定値に静的フィールドを初期化する既定の静的コンストラクターを与えます。 

次の例では、静的コンストラクターを使用して静的フィールドを初期化しています。

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

式の本体の定義で静的コンストラクターを定義することもできます。次の例をご覧ください。 

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

詳細と例については、「[静的コンストラクター](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)」を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [コンストラクターの使用](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [インスタンス コンストラクター](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [プライベート コンストラクター](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [静的コンストラクター](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [方法: コピー コンストラクターを記述する](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a>参照

- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [クラスと構造体](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [ファイナライザー](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
- [static](../../../csharp/language-reference/keywords/static.md)  
- [初期化子がコンストラクターとは反対の順序で実行される理由その 1](https://blogs.msdn.microsoft.com/ericlippert/2008/02/15/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)

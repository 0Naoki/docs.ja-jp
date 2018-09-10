---
title: 名前付きメソッドを使用したデリゲートと匿名メソッド (C# プログラミング ガイド)
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 6d7dcb3c7c6fa8f1d55237504c23cf468aa0e79d
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44274210"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a>名前付きメソッドを使用したデリゲートと匿名メソッド (C# プログラミング ガイド)
[デリゲート](../../../csharp/language-reference/keywords/delegate.md)は、名前付きメソッドに関連付けることができます。 名前付きメソッドを使用してデリゲートをインスタンス化するときは、次のように、そのメソッドをパラメーターとして渡します。  
  
 [!code-csharp[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]  
  
 これを名前付きメソッドの使用といいます。 名前付きメソッドで作成されたデリゲートは、[静的](../../../csharp/language-reference/keywords/static.md)メソッドまたはインスタンス メソッドのいずれかでカプセル化できます。 旧バージョンの C# では、デリゲートをインスタンス化するには、名前付きメソッドを使用するしかありませんが、 新しいメソッドを作成するのが、オーバーヘッドの点で望ましくない場合は、C# でデリゲートをインスタンス化し、そのデリゲートが呼び出されたときに処理するコード ブロックを直接指定できます。 ブロックには、ラムダ式または匿名メソッドのいずれかを含めることができます。 詳細については、[匿名関数](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)に関するページをご覧ください。  
  
## <a name="remarks"></a>コメント  
 デリゲート パラメーターとして渡すメソッドには、デリゲート宣言と同じシグネチャが必要です。  
  
 デリゲート インスタンスがカプセル化できるのは、静的メソッドまたはインスタンス メソッドのいずれかです。  
  
 デリゲートは [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) パラメーターを使用できますが、マルチキャスト イベント デリゲートでこのパラメーターを使用することはお勧めしません。どのデリゲートが呼び出されるかわからないためです。  
  
## <a name="example-1"></a>例 1  
 次のシンプルな例では、デリゲートを宣言して使用します。 デリゲート `Del` とそれに関連付けられているメソッド `MultiplyNumbers` の両方に同じシグネチャが含まれることに注意してください。  
  
 [!code-csharp[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]  
  
## <a name="example-2"></a>例 2  
 次の例では、1 つのデリゲートを静的メソッドとインスタンス メソッドの両方に割り当て、各メソッドから特定の情報を戻します。  
  
 [!code-csharp[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]  
  
## <a name="see-also"></a>参照

- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [デリゲート](../../../csharp/programming-guide/delegates/index.md)  
- [匿名メソッド](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
- [方法: デリゲートを結合する (マルチキャスト デリゲート)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
- [イベント](../../../csharp/programming-guide/events/index.md)

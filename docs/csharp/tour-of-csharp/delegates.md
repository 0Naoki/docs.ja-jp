---
title: "C# のデリゲート | C# 言語のツアー"
description: "C# のデリゲートと遅延バインディングについて"
keywords: ".NET、C#、デリゲート、ラムダ、遅延バインディング"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.translationtype: Human Translation
ms.sourcegitcommit: 19006cc5f24ffc66b92e53e8174c6bd33c249679
ms.openlocfilehash: 9cfefa5f781944b41828ebb61004f960e6cf3d59
ms.contentlocale: ja-jp
ms.lasthandoff: 04/14/2017

---

# <a name="delegates"></a>デリゲート

***デリゲート型***は、特定のパラメーター リストおよび戻り値を使用してメソッドへの参照を表します。 デリゲートを使用すれば、変数に割り当ててパラメーターとして渡すことのできるエンティティとして、メソッドを処理できます。 デリゲートはまた、他のいくつかの言語にみられる関数ポインターの概念に似ていますが、関数ポインターとは異なり、デリゲートはオブジェクト指向でタイプ セーフです。

次の例では、`Function` という名前のデリゲート型を宣言して使用します。

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

`Function` デリゲート型のインスタンスは、`double` 引数を取得して `double` 値を返す任意のメソッドを参照できます。 `Apply` メソッドは、指定された関数を `double[]` の要素に適用し、`double[]` を結果とともに返します。 `Main` メソッドでは、`Apply` は `double[]` に 3 つの異なる関数を適用するために使用されます。

デリゲートは、静的メソッド (前述の例の `Square` や `Math.Sin` など) またはインスタンス メソッド (前述の例の `m.Multiply` など) のいずれかを参照できます。 インスタンス メソッドを参照するデリゲートはまた、特定のオブジェクトを参照し、インスタンス メソッドがデリゲートから呼び出されると、そのオブジェクトは呼び出しで `this` になります。

その場で作成される「インライン メソッド」である匿名関数を使用してデリゲートを作成することもできます。 匿名関数では、周囲のメソッドのローカル変数を確認できます。 したがって、上記の乗数の例は、乗数クラスを使用せずもっと簡単に記述できます。

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

デリゲートの興味深く有用な点は、参照するメソッドのクラスを把握せず必要ともしないことです。重要なのは、参照されるメソッドは同じパラメーターを持ち、デリゲートとして型を返すということです。

>[!div class="step-by-step"]
[前へ](enums.md)
[次へ](attributes.md)


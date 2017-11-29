---
title: Overloads (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a23a6b91681cbd814ac96464e1c340be99a0ecf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="overloads-visual-basic"></a>Overloads (Visual Basic)
プロパティまたはプロシージャが、同じ名前の 1 つ以上の既存のプロパティまたはプロシージャを再度宣言することを示します。  
  
## <a name="remarks"></a>コメント  
 *オーバー ロード*同じスコープ内で指定されたプロパティまたはプロシージャ名の 1 つ以上の定義を指定することです。 プロパティまたは異なるシグネチャを持つプロシージャを再宣言とも呼ばれる*シグネチャによる隠ぺい*です。  
  
## <a name="rules"></a>ルール  
  
-   **宣言コンテキスト。** `Overloads` は、プロパティまたはプロシージャの宣言ステートメントでのみ使用できます。  
  
-   **結合された修飾子。** 指定することはできません`Overloads`と共に[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)同じプロシージャ宣言内で。  
  
-   **相違点が必要です。** *署名*この宣言内で異なる必要があるすべてのプロパティまたはプロシージャをオーバー ロードのシグネチャ。 シグネチャは、プロパティまたはプロシージャの名前と以下の項目で構成されます。  
  
    -   パラメーターの数  
  
    -   パラメーターの順序  
  
    -   パラメーターのデータ型  
  
    -   型パラメーターの数 (ジェネリック プロシージャの場合)  
  
    -   戻り値の型 (変換演算子プロシージャの場合のみ)  
  
     すべてのオーバーロードを同じ名前にする必要はありますが、各オーバーロードは、前の項目の 1 つ以上において他のすべてのオーバーロードと異なっている必要があります。 これにより、コンパイラは、コードでプロパティまたはプロシージャが呼び出すときに使用するバージョンを区別できます。  
  
-   **相違点は許可されません。** 以下の項目はシグネチャに含まれないため、これらの項目の 1 つ以上を変更しても、プロパティまたはプロシージャのオーバーロードには有効ではありません。  
  
    -   値を返すかどうか (プロシージャの場合)  
  
    -   戻り値のデータ型 (変換演算子を除く)  
  
    -   パラメーターまたは型パラメーターの名前  
  
    -   型パラメーターに対する制約 (ジェネリック プロシージャの場合)  
  
    -   パラメーター修飾子キーワード (`ByRef` や `Optional` など)  
  
    -   プロパティまたはプロシージャ修飾子キーワード (`Public` や `Shared` など)  
  
-   **省略可能な修飾子です。** 同じクラス内でオーバーロードされるプロパティまたはプロシージャを複数定義する場合、`Overloads` 修飾子を使用する必要はありません。 ただし、宣言の 1 つで `Overloads` を使用した場合は、すべての宣言で Overloads を使用する必要があります。  
  
-   **シャドウとオーバー ロードします。** `Overloads`シャドウを既存のメンバーまたは基底クラスのオーバー ロードされたメンバーのセットにも使用できます。 この方法で `Overloads` を使用する場合は、基底クラスのメンバーと同じ名前とパラメーター リストを使用してプロパティまたはメソッドを宣言し、`Shadows` キーワードは指定しません。  
  
 `Overrides` を使用する場合は、ライブラリ API と C# が連携しやすくなるように、コンパイラが暗黙的に `Overloads` を追加します。  
  
 `Overloads` 修飾子は、次のコンテキストで使用できます。  
  
 [Function ステートメント](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator ステートメント](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property ステートメント](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub ステートメント](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>関連項目  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [プロシージャのオーバーロード](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [Visual Basic におけるジェネリック型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [演算子プロシージャ](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [方法 : 変換演算子を定義する](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)

---
title: ^= 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: 382e0b27c2dbf27e5acccf29f1b8d2b002cb6664
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592234"
---
# <a name="-operator-visual-basic"></a>^= 演算子 (Visual Basic)
変数またはプロパティの値を式のべき乗にし、結果を変数またはプロパティに代入します。  
  
## <a name="syntax"></a>構文  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>指定項目  
 `variableorproperty`  
 必須。 任意の数値変数またはプロパティ。  
  
 `expression`  
 必須。 任意の数式。  
  
## <a name="remarks"></a>コメント  
 @No__t-0 演算子の左側の要素は、単純なスカラー変数、プロパティ、または配列の要素にすることができます。 変数またはプロパティを[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)にすることはできません。  
  
 @No__t-0 演算子は、まず、変数またはプロパティ (演算子の左辺) の値を、式の値 (演算子の右側) の値に基づいて発生させています。 次に、演算子は、その操作の結果を変数またはプロパティに戻します。  
  
 Visual Basic は、常に[Double データ型](../../../visual-basic/language-reference/data-types/double-data-type.md)の指数演算を実行します。 異なる型のオペランドは `Double` に変換され、結果は常に-1 @no__t ます。  
  
 @No__t-0 の値には、小数、負、またはその両方を指定できます。  
  
## <a name="overloading"></a>オーバーロード  
 [^ 演算子](../../../visual-basic/language-reference/operators/exponentiation-operator.md)は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できることを意味します。 @No__t-0 演算子のオーバーロードは、`^=` 演算子の動作に影響します。 コードで `^` をオーバーロードするクラスまたは構造体に @no__t 0 を使用している場合は、再定義された動作を理解していることを確認してください。 詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、`^=` 演算子を使用して、1つの @no__t 変数の値を2番目の変数のべき乗に上げ、その結果を最初の変数に代入します。  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>関連項目

- [^ 演算子](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [代入演算子](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [算術演算子](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Visual Basic における演算子の優先順位](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [機能別の演算子一覧](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [ステートメント](../../../visual-basic/programming-guide/language-features/statements.md)

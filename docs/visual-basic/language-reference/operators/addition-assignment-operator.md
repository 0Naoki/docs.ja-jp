---
title: += 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: 249a19abfb08677c01ac4cc484d049a7ed1a983c
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591645"
---
# <a name="-operator-visual-basic"></a>+= 演算子 (Visual Basic)
数値式の値を数値変数またはプロパティの値に加算し、その結果を変数またはプロパティに代入します。 また、を使用して、@no__t 0 の式を @no__t の変数またはプロパティに連結し、その結果を変数またはプロパティに代入することもできます。  
  
## <a name="syntax"></a>構文  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a>指定項目  
 `variableorproperty`  
 必須。 任意の数値または @no__t 0 の変数またはプロパティ。  
  
 `expression`  
 必須。 任意の数値または @no__t 0 の式。  
  
## <a name="remarks"></a>コメント  
 @No__t-0 演算子の左側の要素は、単純なスカラー変数、プロパティ、または配列の要素にすることができます。 変数またはプロパティを[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)にすることはできません。  
  
 @No__t-0 演算子は、右辺の値を左側の変数またはプロパティに追加し、その結果を左側の変数またはプロパティに代入します。 @No__t-0 演算子を使用すると、右側の `String` 式を左側の `String` 変数またはプロパティに連結し、その結果を左側の変数またはプロパティに代入することもできます。  
  
> [!NOTE]
> @No__t-0 演算子を使用すると、加算または文字列の連結が行われるかどうかを判断できない場合があります。 @No__t-0 演算子を連結に使用して、あいまいさをなくし、自己記述型のコードを提供します。  
  
 コンパイル環境で厳密なセマンティクスが適用されている場合、この代入演算子は、暗黙的に拡張を実行しますが、縮小変換は実行しません。 これらの変換の詳細については、[拡大変換と縮小変換 (Visual Basic)](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)に関するページを参照してください。 厳密なセマンティクスと寛容なセマンティクスの詳細については、「 [Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)」を参照してください。  
  
 寛容なセマンティクスが許可されている場合、@no__t 0 演算子は、`+` 演算子によって実行されるものと同じように、さまざまな文字列と数値変換を暗黙的に実行します。 これらの変換の詳細については、「 [+ 演算子](../../../visual-basic/language-reference/operators/addition-operator.md)」を参照してください。  
  
## <a name="overloading"></a>オーバーロード  
 @No__t-0 演算子は*オーバーロード*できます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。 @No__t-0 演算子のオーバーロードは、`+=` 演算子の動作に影響します。 コードで `+` をオーバーロードするクラスまたは構造体に @no__t 0 を使用している場合は、再定義された動作を理解していることを確認してください。 詳細については、[演算子プロシージャ (Visual Basic)](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)に関するページを参照してください。  
  
## <a name="example"></a>例  
 次の例では、`+=` 演算子を使用して、ある変数の値を別の変数と結合します。 最初の部分では `+=` を数値変数と共に使用して、ある値を別の値に追加します。 2番目の部分では、1つの値を別の値に連結するために、`+=` と `String` の変数を使用します。 どちらの場合も、結果は最初の変数に割り当てられます。  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 @No__t-0 の値は13になり、`str1` の値は "103" になりました。  
  
## <a name="see-also"></a>関連項目

- [+ 演算子](../../../visual-basic/language-reference/operators/addition-operator.md)
- [代入演算子](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [算術演算子](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [連結演算子](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Visual Basic における演算子の優先順位](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [機能別の演算子一覧](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [ステートメント](../../../visual-basic/programming-guide/language-features/statements.md)

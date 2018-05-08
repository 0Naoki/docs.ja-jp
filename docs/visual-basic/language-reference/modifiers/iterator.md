---
title: 反復子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 565508046b3fa2dc52acf8c5204153beffc15d9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="iterator-visual-basic"></a>反復子 (Visual Basic)
指定する関数または`Get`アクセサーが反復子。  
  
## <a name="remarks"></a>コメント  
 *反復子*コレクションに対するカスタム イテレーションを実行します。 反復子を使用して、 [Yield](../../../visual-basic/language-reference/statements/yield-statement.md)を一度に 1 つ、コレクション内の各要素を返すステートメントです。 ときに、`Yield`ステートメントに達すると、コードの現在の位置が保持されます。 次回、Iterator 関数が呼び出されると、この位置から実行が再開されます。  
  
 関数、またはとして、反復子を実装することができます、`Get`プロパティ定義のアクセサー。 `Iterator`反復子関数の宣言に修飾子が表示されますか`Get`アクセサー。  
  
 使用して、クライアント コードから反復子を呼び出す、[ごとにしています.次のステートメントの](../../../visual-basic/language-reference/statements/for-each-next-statement.md)します。  
  
 反復子関数の戻り値の型または`Get`アクセサーを指定することができます<xref:System.Collections.IEnumerable>、 <xref:System.Collections.Generic.IEnumerable%601>、 <xref:System.Collections.IEnumerator>、または<xref:System.Collections.Generic.IEnumerator%601>です。  
  
 反復子には指定できません`ByRef`パラメーター。  
  
 反復子を、イベント、インスタンス コンストラクター、静的コンストラクター、静的デストラクターで指定することはできません。  
  
 反復子は、匿名の関数を指定できます。 詳細については、「 [反復子](../../programming-guide/concepts/iterators.md)」を参照してください。  
  
## <a name="usage"></a>使用法  
 `Iterator` 修飾子は、次のコンテキストで使用できます。  
  
-   [Function ステートメント](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property ステートメント](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>例  
 次の例では、iterator 関数を示します。 Iterator 関数が、`Yield`内にあるステートメント、[をしています.[次へ]](../../../visual-basic/language-reference/statements/for-next-statement.md)ループします。 各反復処理、[各](../../../visual-basic/language-reference/statements/for-each-next-statement.md)ステートメント本体で`Main`への呼び出しを作成、 `Power` iterator 関数。 Iterator 関数を呼び出すごとに、`Yield` ステートメントの次の実行に進みます。これは、`For…Next` ループの次の反復処理で行われます。  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## <a name="example"></a>例  
 次の例は、反復子である `Get` アクセサーを示しています。 `Iterator`プロパティ宣言では、修飾子です。  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 その他の例では、次を参照してください。[反復子](../../programming-guide/concepts/iterators.md)です。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>  
 [反復子](../../programming-guide/concepts/iterators.md)  
 [Yield ステートメント](../../../visual-basic/language-reference/statements/yield-statement.md)

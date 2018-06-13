---
title: Visual Basic の連結演算子
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: ab268e513e6f019ed651c94deb5e423cfcca7587
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650619"
---
# <a name="concatenation-operators-in-visual-basic"></a>Visual Basic の連結演算子
連結演算子は、複数の文字列を結合して 1 つの文字列にします。 連結演算子には、`+` と `&` の 2 つがあります。 どちらの演算子も、次の例に示すように基本的な連結演算を行います。  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 これらの演算子は、次のように `String` 型の変数を連結することもできます。  
  
 [!code-vb[VbVbalrOperators#76](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]  
  
## <a name="differences-between-the-two-concatenation-operators"></a>2 つの連結演算子の相違点  
 [+ 演算子](../../../../visual-basic/language-reference/operators/addition-operator.md)が 2 つの数値を追加することの主な目的です。 ただし、数値オペランドを文字列オペランドに連結することもできます。 `+` 演算子は、一連の複雑な規則に従って、加算、連結、コンパイル エラーのシグナルの送信、ランタイム <xref:System.InvalidCastException> 例外のスローのどれを行うかを決定します。  
  
 [& 演算子](../../../../visual-basic/language-reference/operators/concatenation-operator.md)に対してのみ定義`String`オペランド、および、常に拡大変換するには、そのオペランド`String`の設定に関係なく、`Option Strict`です。 文字列の連結には `&` 演算子を使用することをお勧めします。この演算子は文字列専用として定義されているため、意図しない変換が発生する可能性を減らすことができます。  
  
## <a name="performance-string-and-stringbuilder"></a>パフォーマンス: 文字列と StringBuilder  
 連結、削除、置換などの文字列操作を何度も行う場合は、<xref:System.Text.StringBuilder> 名前空間の <xref:System.Text> クラスを使用するとパフォーマンスが向上します。 <xref:System.Text.StringBuilder> オブジェクトを作成して初期化するには追加の命令が必要であり、最終的な値を `String` に変換するにはまた別の命令が必要になりますが、<xref:System.Text.StringBuilder> は高速に実行できるため、この時間を埋め合わせることができます。  
  
## <a name="see-also"></a>関連項目  
 [Option Strict ステートメント](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Visual Basic における文字列操作メソッドの型](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)  
 [Visual Basic における算術演算子](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Visual Basic における比較演算子](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Visual Basic における論理/ビット処理演算子](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

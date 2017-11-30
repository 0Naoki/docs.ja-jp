---
title: "方法 : Visual Basic でプロシージャを別のプロシージャに渡す"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e8e205f5238aab39aa92574bc5c680e68cc8a81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>方法 : Visual Basic でプロシージャを別のプロシージャに渡す
この例では、デリゲートを使用してプロシージャを別のプロシージャに渡す方法を示します。  
  
 デリゲートはで他の任意の型と同様に使用できる型[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]です。 `AddressOf`演算子プロシージャ名に適用される場合は、デリゲート オブジェクトを返します。  
  
 この例で取得した、別のプロシージャへの参照を実行できるデリゲート パラメーターを持つプロシージャ、`AddressOf`演算子。  
  
### <a name="create-the-delegate-and-matching-procedures"></a>デリゲートと一致するプロシージャを作成します。  
  
1.  という名前のデリゲートを作成する`MathOperator`です。  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  という名前のプロシージャを作成する`AddNumbers`パラメーターと戻り値の型と一致する`MathOperator`署名が一致するようにします。  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  という名前のプロシージャを作成する`SubtractNumbers`と一致するシグネチャを持つ`MathOperator`します。  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  という名前のプロシージャを作成する`DelegateTest`をパラメーターとしてデリゲートを取得します。  
  
     この手順への参照を受け入れることができる`AddNumbers`または`SubtractNumbers`、署名が一致するので、`MathOperator`署名します。  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  という名前のプロシージャを作成する`Test`を呼び出す`DelegateTest`のデリゲートが 1 回`AddNumbers`をパラメーターとして再度のデリゲートを使用して`SubtractNumbers`をパラメーターとして。  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     ときに`Test`が呼び出されると、その最初の結果を表示`AddNumbers`で動作している`5`と`3`は 8 です。 結果、`SubtractNumbers`に作用する`9`と`3`が表示されたらは 6 です。  
  
## <a name="see-also"></a>関連項目  
 [デリゲート](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [AddressOf 演算子](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Delegate ステートメント](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [方法: デリゲート メソッドを呼び出す](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)

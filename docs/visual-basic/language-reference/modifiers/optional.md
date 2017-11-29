---
title: Optional (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3aa01c2c1ae731c8fe00fdee24521760db69e624
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)
プロシージャが呼び出されたときにプロシージャの引数を省略できますを指定します。  
  
## <a name="remarks"></a>コメント  
 省略可能なパラメーターごとに、そのパラメーターの既定値として定数式を指定する必要があります。 式が評価された場合[Nothing](../../../visual-basic/language-reference/nothing.md)値のデータ型の既定値は、パラメーターの既定値として使用します。  
  
 パラメーター リストには、省略可能なパラメーターが含まれています、それに続くすべてのパラメーターは省略可能な必要があります。  
  
 `Optional` 修飾子は、次のコンテキストで使用できます。  
  
-   [Declare ステートメント](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Function ステートメント](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property ステートメント](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Sub ステートメント](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  省略可能なパラメーターの有無のプロシージャを呼び出すときに、位置または名前で引数を渡すことができます。 詳細については、次を参照してください。[位置と名前による引数を渡す](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)です。  
  
> [!NOTE]
>  オーバー ロードを使用して、省略可能なパラメーターを持つプロシージャを定義することもできます。 1 つの省略可能なパラメーターがある場合は、プロシージャ パラメーターを受け取る、しない 2 つのオーバー ロードされたバージョンを定義できます。 詳細については、次を参照してください。[プロシージャのオーバー ロード](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)です。  
  
## <a name="example"></a>例  
 次の例では、省略可能なパラメーターを持つプロシージャを定義します。  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a>例  
 次の例では、位置によって渡される引数を指定して、名前によって渡される引数を使用してプロシージャを呼び出す方法を示します。 プロシージャは、2 つの省略可能なパラメーターを持ちます。  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a>関連項目  
 [パラメーター リスト](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [省略可能なパラメーター](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [キーワード](../../../visual-basic/language-reference/keywords/index.md)

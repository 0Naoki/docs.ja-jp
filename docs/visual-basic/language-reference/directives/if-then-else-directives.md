---
title: '#もし。。。Then... #Else ディレクティブ (Visual Basic)'
ms.date: 04/11/2018
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05aac9109e49897d1c4dbbad60d807eb3e47798d
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43798636"
---
# <a name="ifthenelse-directives"></a>#If...Then...#Else ディレクティブ
選択した Visual Basic のコード ブロックを条件付きでコンパイルします。  
  
## <a name="syntax"></a>構文  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a>指定項目  
 `expression`  
 必要な`#If`と`#ElseIf`ステートメントの省略可能な他の場所。 1 つまたは複数の条件付きコンパイラ定数、リテラル、および演算子に評価されるのみで構成される、任意の式`True`または`False`します。  
  
 `statements`  
 必要な`#If`ステートメント ブロック、省略可能な他の場所。 Visual Basic プログラムの行またはコンパイラ ディレクティブに関連付けられている式が評価された場合にコンパイルされる`True`します。  
  
 `#End If`  
 終了、`#If`ステートメント ブロックです。  
  
## <a name="remarks"></a>Remarks  
 画面の動作で、`#If...Then...#Else`ディレクティブが同じのように見える、`If...Then...Else`ステートメント。 ただし、`#If...Then...#Else`ディレクティブ、コンパイラによってどのようなコンパイルは一方の評価、`If...Then...Else`ステートメントが実行時に条件を評価します。  
  
 条件付きコンパイルは通常、さまざまなプラットフォーム向けの同じプログラムのコンパイルに使用されます。 使用を防ぐために実行可能ファイルに表示されないコードをデバッグします。 条件付きコンパイル時に除外するコードは、サイズやパフォーマンスに影響を与えませんために完全に、最終的な実行可能ファイルから省略されます。  
  
 使用して、任意の評価の結果に関係なくすべての式が評価されます`Option Compare Binary`します。 `Option Compare`ステートメントでは式には影響しません`#If`と`#ElseIf`ステートメント。  
  
> [!NOTE]
>  単一行の形式、 `#If`、 `#Else`、 `#ElseIf`、および`#End If`ディレクティブが存在しません。 その他のコードは、ディレクティブのいずれかと同じ行に表示できません。 

条件付きコンパイル ブロック内のステートメントは、完全な論理ステートメントである必要があります。 たとえば、関数の属性のみを条件付きでコンパイルすることはできませんが、条件付きでその属性と共に関数を宣言することができます。

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a>例
 この例では、`#If...Then...#Else`コンストラクトを特定のステートメントをコンパイルするかどうかを判断します。  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a>関連項目  
[#Const ディレクティブ](../../../visual-basic/language-reference/directives/const-directive.md)  
[If...Then...Else ステートメント](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
[条件付きコンパイル](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
<xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>   



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
ms.openlocfilehash: aaf5e7dd82cebf734da59e9feb89174705468a4b
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580085"
---
# <a name="ifthenelse-directives"></a>#If...Then...#Else ディレクティブ

選択された Visual Basic コードのブロックを条件付きでコンパイルします。

## <a name="syntax"></a>構文

```vb
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
@No__t_0 および `#ElseIf` のステートメント、他の場所では省略可能です。 @No__t_0 または `False` に評価される1つ以上の条件付きコンパイラ定数、リテラル、および演算子で構成される任意の式。

`statements`  
@No__t_0 ステートメントブロックに必要です。他の場所では省略可能です。 関連付けられた式が `True` に評価される場合にコンパイルされるプログラムラインまたはコンパイラディレクティブを Visual Basic します。

`#End If`  
@No__t_0 ステートメントブロックを終了します。

## <a name="remarks"></a>Remarks

サーフェイスでは、`#If...Then...#Else` ディレクティブの動作は、`If...Then...Else` ステートメントと同じになります。 ただし、`#If...Then...#Else` ディレクティブは、コンパイラによってコンパイルされた内容を評価します。一方、`If...Then...Else` ステートメントは、実行時に条件を評価します。

通常、条件付きコンパイルは、異なるプラットフォームに対して同じプログラムをコンパイルするために使用されます。 また、デバッグコードが実行可能ファイルに表示されないようにするためにも使用されます。 条件付きコンパイル中に除外されたコードは、最終的な実行可能ファイルから完全に省略されるため、サイズやパフォーマンスには影響しません。

評価の結果に関係なく、すべての式は `Option Compare Binary` を使用して評価されます。 @No__t_0 ステートメントは、`#If` および `#ElseIf` ステートメントの式には影響しません。

> [!NOTE]
> @No__t_0、`#Else`、`#ElseIf`、および `#End If` ディレクティブの単一行形式は存在しません。 ディレクティブと同じ行に他のコードを記述することはできません。

条件付きコンパイルブロック内のステートメントは、完全な論理ステートメントである必要があります。 たとえば、条件付きで関数の属性のみをコンパイルすることはできませんが、その属性と共に関数を条件付きで宣言することはできます。

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

この例では、`#If...Then...#Else` コンストラクトを使用して、特定のステートメントをコンパイルするかどうかを判断します。

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a>関連項目

- [#Const ディレクティブ](../../../visual-basic/language-reference/directives/const-directive.md)
- [If...Then...Else ステートメント](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [条件付きコンパイル](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>

---
title: For...Next ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: a60293fc837b6d12810a211892c391f24a46d4e6
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582957"
---
# <a name="fornext-statement-visual-basic"></a>For...Next ステートメント (Visual Basic)

ステートメントのグループを指定された回数だけ繰り返します。

## <a name="syntax"></a>構文

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a>指定項目

|パーツ|説明|
|----------|-----------------|
|`counter`|@No__t_0 ステートメントで必要です。 数値変数。 ループのコントロール変数。 詳細については、このトピックで後述する「 [Counter 引数](#BKMK_Counter)」を参照してください。|
|`datatype`|省略可能です。 @No__t_0 のデータ型。 詳細については、このトピックで後述する「 [Counter 引数](#BKMK_Counter)」を参照してください。|
|`start`|必須です。 数値式。 `counter` の初期値になります。|
|`end`|必須です。 数値式。 @No__t_0 の最終的な値。|
|`step`|省略可能です。 数値式。 ループを通じて毎回 `counter` をインクリメントする量。|
|`statements`|省略可能です。 指定した回数だけ実行される、`For` と `Next` 間の1つ以上のステートメント。|
|`Continue For`|省略可能です。 次のループの反復処理に制御を転送します。|
|`Exit For`|省略可能です。 @No__t_0 ループから制御を転送します。|
|`Next`|必須です。 @No__t_0 ループの定義を終了します。|

> [!NOTE]
> このステートメントで `To` キーワードを使用して、カウンターの範囲を指定します。 このキーワードは、 [Select...Case ステートメント](../../../visual-basic/language-reference/statements/select-case-statement.md)と配列宣言。 配列の宣言の詳細については、「 [Dim ステートメント](../../../visual-basic/language-reference/statements/dim-statement.md)」を参照してください。

## <a name="simple-examples"></a>簡単な例

@No__t_0 を使用しています...一連のステートメントを設定された回数繰り返し実行する場合は `Next` 構造体。

次の例では、`index` 変数は値1で始まり、ループの反復ごとにインクリメントされ、`index` の値が5に達した後に終了します。

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

次の例では、`number` 変数は2から始まり、ループの反復ごとに0.25 によって減少し、`number` の値が0に達した後に終了します。 @No__t_1 の `Step` 引数は、ループの各反復処理で値を0.25 ずつ減らします。

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> しばらくお待ちください... [End While ステートメント](../../../visual-basic/language-reference/statements/while-end-while-statement.md)または[Do...Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)は、ループ内でステートメントを実行する回数が事前にわからない場合に適しています。 ただし、ループを特定の回数繰り返し実行することが予想される場合は、`For`...`Next` ループの方が適しています。 ループに最初に入るときのイテレーションの数を決定します。

## <a name="nesting-loops"></a>ループの入れ子

ループを入れ子にするには、別のループ内にループを挿入し `For` ます。 入れ子になった `For` の例を次に示します。異なるステップ値を持つ構造体を `Next` します。 外側のループは、ループの反復ごとに文字列を作成します。 内側のループは、ループの反復ごとにループカウンター変数をデクリメントします。

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

ループを入れ子にする場合、各ループには一意の `counter` 変数が必要です。

また、さまざまな種類のコントロール構造を入れ子にすることもできます。 詳細については、[入れ子になった制御構造](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) を参照してください。

## <a name="exit-for-and-continue-for"></a>を終了し、を続行します。

@No__t_0 ステートメントは、すぐに `For`... `Next` を終了します。 ループし、`Next` ステートメントの後のステートメントに制御を転送します。

@No__t_0 ステートメントは、ループの次の反復処理に制御を直ちに転送します。 詳細については、「 [Continue ステートメント](../../../visual-basic/language-reference/statements/continue-statement.md)」を参照してください。

次の例は、`Continue For` と `Exit For` ステートメントの使用方法を示しています。

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

@No__t_1 には、任意の数の `Exit For` ステートメントを含めることができ `Next` ループ. 入れ子になった `For`... `Next` 内で使用する場合 ループ、`Exit For` 最も内側のループを終了し、次に高い入れ子レベルに制御を転送します。

`Exit For` は、何らかの条件 (たとえば、`If`... `Then`... `Else` 構造) を評価した後によく使用されます。 次の条件に `Exit For` を使用することもできます。

- 反復処理を続行することは不要または不可能です。 この条件は、エラー値または終了要求によって作成できます。

- @No__t_0...`Catch`...`Finally` ステートメントは例外をキャッチします。 @No__t_1 ブロックの末尾に `Exit For` を使用することもできます。

- 無限ループがあります。これは、大規模または無限の回数実行されるループです。 このような条件を検出した場合は、`Exit For` を使用してループをエスケープできます。 詳細については、「 [Do...Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)。

## <a name="technical-implementation"></a>技術的な実装

@No__t_0 の場合`Next` ループが開始され、Visual Basic は `start`、`end`、および `step` を評価します。 Visual Basic は、現時点ではこれらの値のみを評価し、`start` を `counter` に割り当てます。 ステートメントブロックが実行される前に、Visual Basic は `counter` と `end` を比較します。 @No__t_0 が `end` の値よりも大きい場合 (または `step` が負の場合) は、`For` ループが終了し、制御が `Next` ステートメントの後のステートメントに渡されます。 それ以外の場合は、ステートメントブロックが実行されます。

Visual Basic が `Next` ステートメントを検出するたびに、`step` によって `counter` がインクリメントされ、`For` ステートメントに戻ります。 ここでも、`counter` を `end` と比較し、その結果に応じてブロックを実行するか、ループを終了します。 このプロセスは `counter` が `end` になるか、`Exit For` ステートメントが検出されるまで続行されます。

@No__t_0 が `end` になるまで、ループは停止しません。 @No__t_0 が `end` に等しい場合、ループは続行されます。 ブロックを実行するかどうかを決定する比較は、`step` が正の場合は `end`  <=  `counter`、`counter` が負の場合は  >=  `end` `step` になります。

ループ内で `counter` の値を変更すると、コードの読み取りやデバッグが困難になることがあります。 @No__t_0、`end`、または `step` の値を変更しても、ループが最初に入力されたときに決定された反復値には影響しません。

ループを入れ子にした場合、内部レベルの `Next` ステートメントの前に外側の入れ子レベルの `Next` ステートメントが検出されると、コンパイラはエラーを通知します。 ただし、コンパイラは、すべての `Next` ステートメントで `counter` を指定した場合にのみ、この重複エラーを検出できます。

### <a name="step-argument"></a>ステップ引数

@No__t_0 の値には、正または負のどちらかを指定できます。 このパラメーターは、次の表に従ってループ処理を決定します。

|**ステップ値**|**ループが実行される場合**|
|--------------------|--------------------------|
|正または0|`counter` <= `end`|
|負|`counter` >= `end`|

@No__t_0 の既定値は1です。

### <a name="BKMK_Counter"></a>Counter 引数

次の表は、`counter` が `For…Next` ループ全体を対象とする新しいローカル変数を定義するかどうかを示しています。 この決定は `datatype` が存在するかどうか、`counter` が既に定義されているかどうかによって異なります。

|@No__t_0 存在しますか?|@No__t_0 既に定義されていますか?|結果 (`counter` で、`For...Next` ループ全体にスコープが設定された新しいローカル変数が定義されているかどうか)|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|Ｘ|[はい]|いいえ。 `counter` は既に定義されています。 @No__t_0 のスコープがプロシージャに対してローカルでない場合は、コンパイル時の警告が発生します。|
|Ｘ|Ｘ|はい。 データ型は、`start`、`end`、および `step` 式から推論されます。 型の推定の詳細については、「[オプション推論ステートメント](../../../visual-basic/language-reference/statements/option-infer-statement.md)と[ローカル型の推論](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」を参照してください。|
|[はい]|[はい]|はい。ただし、既存の `counter` 変数がプロシージャの外部で定義されている場合に限ります。 この変数は個別に保持されます。 既存の `counter` 変数のスコープがプロシージャに対してローカルである場合は、コンパイル時エラーが発生します。|
|[はい]|Ｘ|はい。|

@No__t_0 のデータ型によって、イテレーションの種類が決定されます。この型は、次のいずれかの型である必要があります。

- @No__t_0、`SByte`、`UShort`、`Short`、`UInteger`、`Integer`、`ULong`、`Long`、`Decimal`、`Single`、0。

- [Enum ステートメント](../../../visual-basic/language-reference/statements/enum-statement.md)を使用して宣言する列挙体。

- `Object`。

- 次の演算子を持つ `T` 型。 `B` は `Boolean` 式で使用できる型です。

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

必要に応じて、`Next` ステートメントで `counter` 変数を指定することもできます。 この構文を使用すると、特に `For` ループが入れ子になっている場合に、プログラムの読みやすさが向上します。 対応する `For` ステートメントに表示される変数を指定する必要があります。

@No__t_0、`end`、および `step` 式は、`counter` の型に拡大変換される任意のデータ型に評価されます。 @No__t_0 にユーザー定義型を使用する場合は、`start`、`end`、または `step` の型を `counter` の型に変換するために、`CType` 変換演算子を定義することが必要になる場合があります。

## <a name="example"></a>例

次の例では、ジェネリックリストからすべての要素を削除します。 [For Each...次のステートメント](../../../visual-basic/language-reference/statements/for-each-next-statement.md)の例では、`For` を示しています...`Next` ステートメントを降順で反復処理します。 この例では、`removeAt` メソッドによって、削除された要素の後にある要素のインデックス値が小さくなるため、この手法を使用します。

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a>例

次の例では、列挙[ステートメント](../../../visual-basic/language-reference/statements/enum-statement.md)を使用して宣言された列挙型を反復処理します。

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a>例

次の例では、ステートメントのパラメーターは、`+`、`-`、`>=`、および `<=` の各演算子に対して演算子のオーバーロードを持つクラスを使用しています。

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a>関連項目

- <xref:System.Collections.Generic.List%601>
- [ループ構造](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While ステートメント](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [入れ子になった制御構造](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit ステートメント](../../../visual-basic/language-reference/statements/exit-statement.md)
- [コレクション](../../programming-guide/concepts/collections.md)

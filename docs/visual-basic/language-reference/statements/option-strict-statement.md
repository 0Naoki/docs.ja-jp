---
title: Option Strict ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Strict
- vb.OptionStrict
helpviewer_keywords:
- Strict keyword [Visual Basic]
- Option Strict statement [Visual Basic]
- conversions [Visual Basic], implicit
- late binding [Visual Basic]
- implicit conversions [Visual Basic]
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
ms.openlocfilehash: ed95d0a0c6fc9ba41bba2c4e16d4ed3b721ae4e3
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44077068"
---
# <a name="option-strict-statement"></a>Option Strict Statement
暗黙的なデータ型変換を拡大変換のみに制限、遅延バインディングが禁止および禁止になる暗黙的な型指定、`Object`型。  
  
## <a name="syntax"></a>構文  
  
```  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>指定項目  
  
|用語|定義|  
|---|---|  
|`On`|任意。 により、`Option Strict`をチェックします。|  
|`Off`|任意。 無効にします`Option Strict`をチェックします。|  
  
## <a name="remarks"></a>Remarks  
 ときに`Option Strict On`または`Option Strict`ファイルでは、コンパイル時エラーが発生する、次の条件が表示されます。  
  
-   暗黙的な縮小変換  
  
-   遅延バインディング  
  
-   結果が `Object` 型となる暗黙の型指定  
  
> [!NOTE]
>  設定できる警告の構成で、 [[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)コンパイル時エラーが発生する 3 つの条件に対応する 3 つの設定があります。 これらの設定を使用する方法については、次を参照してください。 [IDE で警告の構成を設定する](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions)このトピックで後述します。  
  
 `Option Strict Off`ステートメントは、これらのエラーまたは警告を有効にする、関連する IDE 設定を指定する場合でもエラーと警告は、次の 3 つのすべての条件のチェックをオフにします。 `Option Strict On`場合でも、これらのエラーまたは警告をオフに関連付けられている IDE 設定の指定、ステートメントがエラーと警告は、次の 3 つのすべての条件のチェックをオンにします。  
  
 使用する場合、`Option Strict`ステートメントは、ファイル内の他のコード ステートメントの前に出現する必要があります。  
  
 設定すると`Option Strict`に`On`、Visual Basic プログラミングのすべての要素のデータ型を指定することを確認します。 データ型を明示的に指定またはローカル型推論を使用して指定できます。 すべてのプログラミング要素のデータ型を指定することはお勧めしますが、次の理由。  
  
-   変数とパラメーターの IntelliSense のサポートが有効にするとします。 これにより、コードを入力すると、プロパティやその他のメンバーを参照してください。  
  
-   これにより、コンパイラが型チェックを実行できます。 型チェックでは、型変換エラーのため実行時に失敗するステートメントを検索できます。 また、これらのメソッドをサポートしていないオブジェクトに対するメソッドの呼び出しを識別します。  
  
-   これは、コードの実行が速くなります。 この理由の 1 つは、プログラミング要素のデータ型を指定しない場合、Visual Basic コンパイラが割り当てる、`Object`型。 コンパイル済みのコードは、間を気軽に変換する必要があります`Object`とその他のデータ型は、パフォーマンスが低下します。  
  
## <a name="implicit-narrowing-conversion-errors"></a>暗黙的な縮小変換エラー  
 縮小変換する暗黙的なデータ型変換がある場合は、暗黙的な縮小変換エラーが発生します。  
  
 Visual Basic は、多くのデータ型を他のデータ型に変換できます。 1 つのデータ型の値は精度が低いまたは容量の小さいデータ型に変換するときに、データ損失が発生することができます。 このような縮小変換が失敗した場合、実行時エラーが発生します。 `Option Strict` これらの縮小変換のコンパイル時に通知をにより、それらを回避するようにします。 詳細については、次を参照してください。[暗黙的および明示的な変換](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)と[Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)します。  
  
 エラーが発生する変換には、式で発生する暗黙的な変換が含まれます。 詳細については、次のトピックを参照してください。  
  
-   [+ 演算子](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [+= 演算子](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\ 演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [/= 演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Char データ型](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 使用して文字列を連結するときに、 [& 演算子](../../../visual-basic/language-reference/operators/concatenation-operator.md)、すべての文字列への変換は拡大変換と見なされます。 場合でも、暗黙的な縮小変換エラーは、これらの変換が生成されないように`Option Strict`にします。  
  
 場合に縮小変換がコンパイル時エラーになりますを対応するパラメーターと異なるデータ型を持つ引数を持つメソッドを呼び出すときに`Option Strict`にします。 拡大変換または明示的な変換を使用して、コンパイル時エラーを回避できます。  
  
 内の要素からの変換のコンパイル時に暗黙的な縮小変換エラーが抑制されます、`For Each…Next`ループ コントロール変数のコレクション。 これが発生した場合でも`Option Strict`にします。 詳細については、"Narrowing Conversions"セクションを参照してください[ごとにしています...次のステートメントの](../../../visual-basic/language-reference/statements/for-each-next-statement.md)します。  
  
## <a name="late-binding-errors"></a>遅延バインド エラー  
 `Object` 型として宣言された変数のプロパティまたはメソッドにオブジェクトを代入する場合は、そのオブジェクトは遅延バインディングされます。 詳細については、次を参照してください。[事前バインディングと遅延バインディング](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)します。  
  
## <a name="implicit-object-type-errors"></a>オブジェクトの暗黙的な型のエラー  
 適切な型が宣言された変数を推論できない場合は暗黙的なオブジェクトの型エラーが発生するため、`Object` の型が推論されます。 これは主に、`As` 句を使用せず、`Option Infer` をオフにして、`Dim` ステートメントを使用して変数を宣言した場合に発生します。 詳細については、次を参照してください。 [Option Infer ステートメント](../../../visual-basic/language-reference/statements/option-infer-statement.md)と[Visual Basic 言語仕様](../../../visual-basic/reference/language-specification/index.md)します。  
  
 メソッドのパラメーターに、`As`句は省略可能な場合は`Option Strict`はオフです。 ただし、任意の 1 つのパラメーターを使用している場合、`As`句では、これらはすべて使用する必要あります。 場合`Option Strict`では、`As`句がすべてのパラメーター定義が必要です。  
  
 使用せずに変数を宣言する場合、`As`句に設定し、 `Nothing`、変数の型を持つ`Object`します。 コンパイル時エラーが発生しないケースでこのときに`Option Strict`上と`Option Infer`にします。 この例は`Dim something = Nothing`します。  
  
### <a name="default-data-types-and-values"></a>既定のデータ型と値  
 次の表に、データ型と初期化子で指定するさまざまな組み合わせの結果、 [Dim ステートメント](../../../visual-basic/language-reference/statements/dim-statement.md)します。  
  
|データ型が指定されているか|初期化子が指定されているか|例|結果|  
|---|---|---|---|  
|Ｘ|Ｘ|`Dim qty`|`Option Strict` がオフ (既定値) の場合、変数は `Nothing` に設定されます。<br /><br /> `Option Strict` がオンの場合、コンパイル時エラーが発生します。|  
|Ｘ|○|`Dim qty = 5`|`Option Infer` がオン (既定値) の場合、変数は初期化子のデータ型になります。 参照してください[ローカル型推論](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)します。<br /><br /> `Option Infer` がオフで、`Option Strict` がオフの場合、変数は `Object` のデータ型になります。<br /><br /> `Option Infer` がオフで、`Option Strict` がオンの場合、コンパイル時エラーが発生します。|  
|○|Ｘ|`Dim qty As Integer`|変数は、データ型の既定値に初期化されます。 詳細については、次を参照してください。 [Dim ステートメント](../../../visual-basic/language-reference/statements/dim-statement.md)します。|  
|はい|○|`Dim qty  As Integer = 5`|初期化子のデータ型を指定したデータ型に変換できない場合は、コンパイル時エラーが発生します。|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>ときに Option Strict のステートメントが存在しません。  
 ソース コードが含まれていない場合、`Option Strict`ステートメントでは、 **Option strict**の設定、 [[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)使用されます。 **コンパイル ページ**エラーを生成する条件をさらに細かく制御する設定があります。  
  
 使用することができます、コマンド ライン コンパイラを使用している場合、 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)コンパイラ オプションの設定を指定する`Option Strict`します。  
  
### <a name="to-set-option-strict-in-the-ide"></a>IDE で Option Strict を設定するには  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1.  **ソリューション エクスプローラー**でプロジェクトを選択します。 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。  
  
2.  **コンパイル** タブの値を設定、 **Option Strict**ボックス。  
  
###  <a name="conditions"></a> IDE で警告の構成を設定するには  
 使用すると、 [[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)の代わりに、`Option Strict`ステートメントでは、エラーを生成する条件をさらに制御があります。 **警告の構成**のセクション、**コンパイル ページ**がコンパイル時エラーが発生する 3 つの条件に対応する設定と`Option Strict`にします。 これらの設定を次に示します。  
  
-   **暗黙的な変換**  
  
-   **遅延バインディング、呼び出しが実行時に失敗する可能性があります**  
  
-   **暗黙的な型、オブジェクトと見なされます**  
  
 **[Option Strict]** を **[オン]** に設定すると、これら 3 つの警告の構成設定のすべてが **[エラー]** に設定されます。 **[Option Strict]** を **[オフ]** に設定すると、3 つの設定すべてが **[なし]** に設定されます。  
  
 各警告の構成設定を個別に **[なし]**、**[警告]**、または **[エラー]** に変更することができます。 3 つの警告の構成設定がすべて **[エラー]** に設定されている場合、`Option strict` ボックスに `On` が表示されます。 3 つすべてが **[なし]** に設定されている場合、このボックスには `Off` が表示されます。 これらの設定のその他の組み合わせに対しては、**(カスタム)** が表示されます。  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>新しいプロジェクトの Option Strict の既定の設定を設定するには  
 プロジェクトを作成するときに、 **Option Strict**の設定、**コンパイル**タブに設定されている、 **Option Strict**での設定、**オプション**ダイアログ ボックス。  
  
 設定する`Option Strict`でこのダイアログ ボックスで、**ツール** メニューのをクリックして**オプション**します。 **[オプション]** ダイアログ ボックスの **[プロジェクトおよびソリューション]** を展開し、**[VISUAL BASIC の既定値]** をクリックします。 初期の既定の設定で**VB の既定値**は`Off`します。  
  
### <a name="to-set-option-strict-on-the-command-line"></a>コマンドラインで Option Strict を設定するには  
 含める、 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)コンパイラ オプションで、 **vbc**コマンド。  
  
## <a name="example"></a>例  
 次の例では、縮小、変換は暗黙的な型変換によって発生したコンパイル時エラーを示します。 このようなエラーに対応する、**暗黙的な変換**条件、**コンパイル ページ**します。  
  
 [!code-vb[VbVbalrStatements#161](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## <a name="example"></a>例  
 次の例では、遅延バインディングによるコンパイル時エラーを示します。 このカテゴリのエラーに対応する、**遅延バインディング; 呼び出しは実行時に失敗でした**条件、**コンパイル ページ**します。  
  
 [!code-vb[VbVbalrStatements#162](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## <a name="example"></a>例  
 次の例では、暗黙の型で宣言された変数によって発生したエラー`Object`します。 このようなエラーに対応する、**暗黙的な型; object と見なされます**条件、**コンパイル ページ**します。  
  
 [!code-vb[VbVbalrStatements#163](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#164](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]  
  
## <a name="see-also"></a>関連項目

- [拡大変換と縮小変換](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
- [暗黙の型変換と明示的な型変換](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
- [[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
- [Option Explicit ステートメント](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
- [データ型変換関数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
- [方法: オブジェクトのメンバーにアクセスする](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)  
- [XML での埋め込み式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
- [厳密でないデリゲート変換](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
- [Office ソリューションの遅延バインディング](/visualstudio/vsto/late-binding-in-office-solutions)  
- [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
- [[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

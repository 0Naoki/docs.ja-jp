---
title: オブジェクト初期化子:名前付きの型と匿名型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
ms.openlocfilehash: e1f461cc98fb104f78a6c83a207cff7f4eda9227
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046463"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>オブジェクト初期化子:名前付きの型と匿名型 (Visual Basic)
オブジェクト初期化子を使用すると、単一の式を使用して複雑なオブジェクトのプロパティを指定できます。 これらの型を使用して、名前付きの型と匿名型のインスタンスを作成できます。  
  
## <a name="declarations"></a>宣言  
 名前付きの型と匿名型のインスタンスの宣言はほぼ同じに見えますが、その効果は同じではありません。 各カテゴリには、独自の機能と制限があります。 次の例は、オブジェクト初期化子リストを使用して`Customer`、名前付きクラスのインスタンスを宣言および初期化する便利な方法を示しています。 クラスの名前がキーワード`New`の後に指定されていることに注意してください。  
  
 [!code-vb[VbVbalrObjectInit#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#1)]  
  
 匿名型には使用可能な名前がありません。 したがって、匿名型のインスタンス化にクラス名を含めることはできません。  
  
 [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
 2つの宣言の要件と結果は同じではありません。 では、プロパティを`Name`持つクラスが既に存在している必要があり、宣言によってそのクラスのインスタンスが作成されます。`Customer` `namedCust` では`Name`、コンパイラは、1つのプロパティ、という文字列を持つ新しいクラスを定義し、そのクラスの新しいインスタンスを作成します。 `anonymousCust`  
  
## <a name="named-types"></a>名前付きの型  
 オブジェクト初期化子は、型のコンストラクターを呼び出す簡単な方法を提供し、1つのステートメントで一部またはすべてのプロパティの値を設定します。 コンパイラは、ステートメントの適切なコンストラクターを呼び出します。引数が指定されていない場合はパラメーターなしのコンストラクター、または1つ以上の引数が送信される場合はパラメーター化されたコンストラクターです。 その後、指定されたプロパティは初期化子リストに表示される順序で初期化されます。  
  
 初期化子リスト内の各初期化は、クラスのメンバーへの初期値の割り当てで構成されます。 メンバーの名前とデータ型は、クラスが定義されるときに決定されます。 次の例`Customer`では、クラスが存在し、文字列値を受け入れること`City`ができるとという名前`Name`のメンバーを持っている必要があります。  
  
 [!code-vb[VbVbalrObjectInit#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#3)]  
  
 または、次のコードを使用して同じ結果を得ることもできます。  
  
 [!code-vb[VbVbalrObjectInit#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#4)]  
  
 これらの宣言は、パラメーターなしのコンストラクターを使用してオブジェクト`Customer`を作成し、を使用`With`してプロパティ`Name`と`City`プロパティの初期値を指定する次の例と同じです。諸表.  
  
 [!code-vb[VbVbalrObjectInit#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#5)]  
  
 クラスに`Customer`パラメーター化されたコンストラクターが含まれていて、たとえば`Name`、の値をに送信できる場合は、次`Customer`の方法でオブジェクトを宣言して初期化することもできます。  
  
 [!code-vb[VbVbalrObjectInit#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#6)]  
  
 次のコードに示すように、すべてのプロパティを初期化する必要はありません。  
  
 [!code-vb[VbVbalrObjectInit#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#7)]  
  
 ただし、初期化リストを空にすることはできません。 初期化されていないプロパティは、既定値を保持します。  
  
### <a name="type-inference-with-named-types"></a>名前付きの型の推論  
 オブジェクト初期化子とローカル型推論を組み合わせる`cust1`ことによって、の宣言のコードを短縮できます。 これにより、変数宣言`As`で句を省略できます。 変数のデータ型は、割り当てによって作成されたオブジェクトの型から推論されます。 次の例では、の`cust6`型は`Customer`です。  
  
 [!code-vb[VbVbalrObjectInit#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#8)]  
  
### <a name="remarks-about-named-types"></a>名前付きの型に関する解説  
  
- オブジェクト初期化子リストでクラスメンバーを複数回初期化することはできません。 の`cust7`宣言によりエラーが発生します。  
  
     [!code-vb[VbVbalrObjectInit#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#9)]  
  
- メンバーは、自身または別のフィールドを初期化するために使用できます。 が初期化される前にメンバーにアクセスする場合、の次の`cust8`宣言のように、既定値が使用されます。 オブジェクト初期化子を使用する宣言が処理された場合、最初に発生するのは、適切なコンストラクターが呼び出されることです。 その後、初期化子リスト内の個々のフィールドが初期化されます。 次の例で`Name`は、の既定値がに`cust8`割り当てられており、初期化さ`cust9`れた値がで割り当てられています。  
  
     [!code-vb[VbVbalrObjectInit#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#10)]  
  
     次の例では、およびの`cust3` `cust4`パラメーター化された`cust10`コンストラクター `cust11`を使用して、およびを宣言および初期化します。  
  
     [!code-vb[VbVbalrObjectInit#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#11)]  
  
- オブジェクト初期化子は入れ子にすることができます。 `AddressClass`次の例では、は`City`と`State`と`Customer`いう2つのプロパティを持つクラスです。この`Address`クラスには、の`AddressClass`インスタンスであるプロパティがあります。  
  
     [!code-vb[VbVbalrObjectInit#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#12)]  
  
- 初期化リストを空にすることはできません。  
  
- 初期化するインスタンスを型オブジェクトにすることはできません。  
  
- 初期化されるクラスメンバーは、共有メンバー、読み取り専用のメンバー、定数、またはメソッドの呼び出しにはできません。  
  
- 初期化されるクラスメンバーにインデックスを作成したり、修飾したりすることはできません。 次の例では、コンパイラエラーが発生します。  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>匿名型  
 匿名型では、オブジェクト初期化子を使用して、明示的に定義して名前を指定しない新しい型のインスタンスを作成します。 代わりに、コンパイラは、オブジェクト初期化子リストで指定したプロパティに従って型を生成します。 型の名前は指定されていないため、*匿名型*と呼ばれます。 たとえば、次の宣言をの`cust6`前の宣言と比較します。  
  
 [!code-vb[VbVbalrObjectInit#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#13)]  
  
 構文が異なるのは、データ型の後`New`に名前が指定されていないことだけです。 しかし、何が起こるかはかなり異なります。 コンパイラは、 `Name`とと`City`いう2つのプロパティを持つ新しい匿名型を定義し、指定された値を使用してそのインスタンスを作成します。 型の推定によって`Name` 、 `City`例のとの型が文字列になります。  
  
> [!CAUTION]
> 匿名型の名前はコンパイラによって生成され、コンパイルごとに異なる場合があります。 コードでは、匿名型の名前を使用したり、使用したりしないでください。  
  
 型の名前は使用できないため、 `As`句を使用してを宣言`cust13`することはできません。 その型を推論する必要があります。 遅延バインディングを使用しない場合、匿名型の使用はローカル変数に限定されます。  
  
 匿名型は、クエリの[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]重要なサポートを提供します。 クエリでの匿名型の使用の詳細については、「[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」と「 [VISUAL BASIC での LINQ の概要](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)」を参照してください。  
  
### <a name="remarks-about-anonymous-types"></a>匿名型の解説  
  
- 通常、匿名型の宣言に含まれるすべてまたはほとんどのプロパティは、キープロパティになります。これは`Key` 、プロパティ名の前にキーワードを入力することによって示されます。  
  
     [!code-vb[VbVbalrObjectInit#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#14)]  
  
     キープロパティの詳細については、「[キー](../../../../visual-basic/language-reference/modifiers/key.md)」を参照してください。  
  
- 名前付きの型の場合と同様に、匿名型の定義の初期化子リストは、少なくとも1つのプロパティを宣言する必要があります。  
  
     [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
- 匿名型のインスタンスが宣言されている場合、コンパイラは、一致する匿名型定義を生成します。 プロパティの名前とデータ型は、インスタンス宣言から取得され、コンパイラによって定義に含まれます。 名前付きの型の場合と同じように、プロパティには名前が付けられず、事前に定義されます。 これらの型は推論されます。 `As`句を使用してプロパティのデータ型を指定することはできません。  
  
- 匿名型では、他のいくつかの方法でプロパティの名前と値を設定することもできます。 たとえば、匿名型のプロパティは、変数の名前と値の両方、または別のオブジェクトのプロパティの名前と値の両方を受け取ることができます。  
  
     [!code-vb[VbVbalrObjectInit#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#15)]  
  
     匿名型のプロパティを定義するためのオプションの詳細につい[ては、「方法:匿名型の宣言](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)のプロパティ名と型を推論します。  
  
## <a name="see-also"></a>関連項目

- [ローカル型の推論](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Visual Basic における LINQ の概要](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [方法: 匿名型の宣言でプロパティの名前と型を推論する](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
- [方法: オブジェクト初期化子を使用してオブジェクトを宣言する](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)

---
title: Visual Basic における変数のトラブルシューティング
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting [Visual Basic], variables
- variables [Visual Basic], troubleshooting
ms.assetid: 928a2dc8-e565-4ae4-8ba3-80cc0cb50090
ms.openlocfilehash: 31aca95bb292ecd0bb04fda6ded83d4af8be0e2f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598612"
---
# <a name="troubleshooting-variables-in-visual-basic"></a>Visual Basic における変数のトラブルシューティング
このページには、Visual Basic における変数を使用する場合に発生する可能性がある一般的な問題が一覧表示されます。  
  
## <a name="unable-to-access-members-of-an-object"></a>オブジェクトのメンバーにアクセスできない  
 コードからオブジェクトのプロパティまたはメソッドにアクセスしようとしたときに、発生する可能性があるエラーは 2 つあります。  
  
- オブジェクト変数を特定の型として宣言した後、その型で定義されていないメンバーを参照すると、コンパイラによってエラー メッセージが生成されることがあります。  
  
- オブジェクト変数に代入されたオブジェクトが、コードからアクセスしようとしたメンバーを公開していないと、ランタイム <xref:System.MemberAccessException> が発生します。 変数の場合[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)、メンバーでない場合に、この例外を取得することもできます`Public`します。 この原因は、遅延バインディングで許可されているのは、 `Public` メンバーへのアクセスのみのためです。  
  
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) で型チェックが `On`に設定されている場合、オブジェクト変数がアクセスできるのは、その変数の宣言時に指定したクラスのメソッドとプロパティだけです。 次に例を示します。  

 [!code-vb[VbVbalrVariables#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#2)]  
  
 この例の場合、 `p` で使用できるのは <xref:System.Object> クラス自体のメンバーのみです。 `Left` プロパティは含まれません。 一方、 `q` は、 <xref:System.Windows.Forms.Label>型として宣言されているため、 <xref:System.Windows.Forms.Label> 名前空間の <xref:System.Windows.Forms> クラスのすべてのメソッドとプロパティを使用できます。  
  
### <a name="correct-approach"></a>修正方法  
 特定のクラスのオブジェクトにあるすべてのメンバーにアクセスできるようにするには、オブジェクト変数をできる限りそのクラスの型で宣言します。 オブジェクト型がコンパイル時にわからないなどの理由で、それができない場合は、 `Option Strict` を `Off` に設定し、変数を [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)で変数を使用するときに発生する可能性のある、いくつかの一般的な問題について説明します。 これにより任意の型のオブジェクトを変数に代入できます。また、現在変数に代入されているオブジェクトが受け入れ可能な型であることを確認する必要があります。 使用することができます、 [TypeOf 演算子](../../../../visual-basic/language-reference/operators/typeof-operator.md)この判断を行います。  
  
## <a name="other-components-cannot-access-your-variable"></a>他のコンポーネントが変数にアクセスできない  
 Visual Basic の名前は*大文字*します。 2 つの名前の違いが英字の大文字と小文字の違いだけの場合、コンパイラでは 2 つを同じ名前と解釈します。 たとえば、 `ABC` と `abc` は、宣言された同じ要素を参照していると見なされます。  
  
 しかし、共通言語ランタイム (CLR) のバインディングでは *大文字と小文字が区別されます* 。 このため、アセンブリまたは DLL を作成し、他のアセンブリで使用できるようにすると、名前の大文字と小文字が区別されるようになります。 たとえば、 `ABC`という名前の要素を持つクラスを定義し、他のアセンブリから共通言語ランタイムを通じてこのクラスを使用する場合は、この要素を `ABC`として参照する必要があります。 後でクラスを再コンパイルして要素の名前を `abc`に変更すると、このクラスを使用していた他のアセンブリがこの要素にアクセスできなくなります。 したがって、アセンブリを更新してリリースするときは、パブリックな要素の名前の大文字と小文字を変更しないでください。  
  
 詳細については、[共通言語ランタイム](../../../../standard/clr.md)に関するページを参照してください。  
  
### <a name="correct-approach"></a>修正方法  
 他のコンポーネントから変数にアクセスできるようにするには、その変数の名前を、大文字と小文字が区別されるものとして扱います。 作成したクラスまたはモジュールをテストするときには、他のアセンブリが適切な変数にバインドされることを確認します。 コンポーネントの公開後は、大文字と小文字の変更を含め、既存の変数名は変更しないようにします。  
  
## <a name="wrong-variable-being-used"></a>誤った変数が使用される  
 同じ名前の 1 つ以上の変数がある場合は、Visual Basic コンパイラはその名前への参照を解決しようとします。 変数のスコープが異なる場合、コンパイラは、参照を最も狭いスコープの宣言に解決します。 変数のスコープが同じ場合、解決は失敗し、コンパイラはエラーを発行します。 詳細については、「 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)」を参照してください。  
  
### <a name="correct-approach"></a>修正方法  
 同じ名前でスコープが異なる変数を使わないようにします。 他のアセンブリまたはプロジェクトを使用している場合は、その外部コンポーネントで定義された名前を使うことはできるだけ避けてください。 同じ名前の変数が複数ある場合は、変数への参照ごとに修飾子を付けるようにしてください。 詳細については、「 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- [変数](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [変数宣言](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [オブジェクト変数](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [オブジェクト変数の宣言](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [方法: オブジェクトのメンバーへのアクセス](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [オブジェクト変数の値](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [方法: オブジェクト変数が指す型を確認します。](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)
- [宣言された要素の参照](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)

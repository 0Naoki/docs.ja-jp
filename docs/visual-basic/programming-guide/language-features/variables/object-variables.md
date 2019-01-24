---
title: Visual Basic におけるオブジェクト変数
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 046119664fc0277a6a5305d0cf086b4438b13f9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685465"
---
# <a name="object-variables-in-visual-basic"></a>Visual Basic におけるオブジェクト変数
値を直接格納するだけでなく、変数は、オブジェクトを参照できます。 同じ理由から、変数に任意の値を代入するには、変数にオブジェクトを割り当てます。  
  
-   変数名は、多くの場合、短くしてメソッドと、オブジェクト自体へのアクセスに必要なプロパティの完全なパスよりも覚えやすくします。  
  
-   オブジェクトを参照する変数を使用するは、必要なメソッドやプロパティを使って繰り返しオブジェクト自体へのアクセスよりも効率的です。  
  
-   コードの実行中に他のオブジェクトを参照する変数を変更することができます。  
  
## <a name="making-code-shorter"></a>コードを短く  
 オブジェクト変数を使用すると、入力するのに必要がコードを短きます。 次の例では、メソッドとプロパティの完全なパスを使用して、アクセスする、<xref:System.Windows.Forms.Control>オブジェクト。  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 このコードを短くし、コントロールのオブジェクト変数を使用する場合は、実行を高速化できます。 割り当てる特定のクラスでオブジェクト変数を宣言する必要があります (`Control`この場合)。 オブジェクトを変数に代入すると参照するオブジェクトを扱うときとまったく同じように扱うことができます。 設定またはオブジェクトのプロパティを取得またはそのメソッドのいずれかを使用できます。 次の例では、オブジェクト変数を使用して、前の例のコードを簡略化します。  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a>関連項目
- [変数宣言](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [方法: 長い修飾パスを持つオブジェクトへのアクセスを高速化します。](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [オブジェクト変数の宣言](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [オブジェクト変数の代入](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [オブジェクト変数の値](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)

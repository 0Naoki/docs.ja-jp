---
title: "方法 : Windows フォーム TextBox コントロールでテキストを選択する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08ad19f3daca43fb33e845b632ac7d92b00f544c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a>方法 : Windows フォーム TextBox コントロールでテキストを選択する
Windows フォームでテキストをプログラムで選択できる<xref:System.Windows.Forms.TextBox>コントロール。 たとえば、特定の文字列のテキストを検索する関数を作成する場合は、検索した文字列の位置のリーダーを視覚的にアラートを生成するテキストを選択できます。  
  
### <a name="to-select-text-programmatically"></a>プログラムによってテキストを選択するには  
  
1.  設定、<xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>プロパティを選択するテキストの先頭にします。  
  
     <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>プロパティは、数値をテキスト文字列内に挿入ポイントを示す、0、左端の位置。 場合、<xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>プロパティの値に文字数以上になると、テキスト ボックスに、カーソルが最後の文字の後に配置します。  
  
2.  設定、<xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>プロパティを選択するテキストの長さをします。  
  
     <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>プロパティは、カーソルの幅を設定する数値。 設定、 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 0 では、この数の文字を選択するとが現在のカーソル位置からの起動に大きい数値にします。  
  
3.  (省略可能)アクセスを選択したテキスト、<xref:System.Windows.Forms.TextBoxBase.SelectedText%2A>プロパティです。  
  
     選択以下のコードをテキストの内容ボックスときに、コントロールの<xref:System.Windows.Forms.Control.Enter>イベントが発生します。 この例では、テキスト ボックスに値を持つかどうか、<xref:System.Windows.Forms.TextBox.Text%2A>プロパティが`null`または空の文字列。 テキスト ボックスにフォーカスが移動すると、テキスト ボックスの現在のテキストが選択されます。 `TextBox1_Enter`イベント ハンドラーが; 詳細については、コントロールにバインドする必要がありますを参照してください[する方法: Windows フォームの時間の実行時のイベント ハンドラーの作成](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)です。  
  
     この例をテストするには、テキスト ボックスにフォーカスがあるまで Tab キーを押します。 テキスト ボックスをクリックし場合、テキストは選択できません。  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.TextBox>  
 [TextBox コントロールの概要](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [方法: 読み取り専用テキスト ボックスを作成する](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [方法: 文字列に引用符を挿入する](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [方法: Windows フォーム TextBox コントロールで複数行を表示する](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox コントロール](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)

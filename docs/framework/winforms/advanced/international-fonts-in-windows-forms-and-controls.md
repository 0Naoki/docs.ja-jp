---
title: Windows フォームおよびコントロールの国際対応フォント
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 38a6928dfb548c6b514b598dbebe5bbc62d2e3f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Windows フォームおよびコントロールの国際対応フォント
国際対応のアプリケーションでは、可能な限り、フォント フォールバックを使用するフォントを選択する勧めします。 システムがどのようなスクリプトの文字を決定するフォント代替手段に属しています。  
  
## <a name="using-font-fallback"></a>フォント フォールバックの使用  
 この機能を利用するを設定しないでください、<xref:System.Drawing.Font>フォームまたはその他の要素のプロパティです。 アプリケーションでは、オペレーティング システムの 1 つのローカライズされた言語によって異なるため既定のシステム フォントが自動的に使用します。 アプリケーションを実行すると、システムは自動的に提供されているオペレーティング システムで選択したカルチャに適切なフォントを使用します。  
  
 例外が発生しました、規則に、フォント、フォント スタイルを変更するために設定されていないのです。 これは、ユーザーが太字で表示されるテキスト ボックス内のテキストを作成する場合、ボタンをクリックしたアプリケーションの重要なことがあります。 実行するには関数を作成する、太字で表示するテキスト ボックスのフォント スタイルを変更する、フォームのフォントにします。 2 つの場所でこの関数の呼び出しすることが重要: ボタンの<xref:System.Windows.Forms.Control.Click>イベント ハンドラーと、<xref:System.Windows.Forms.Control.FontChanged>イベント ハンドラー。 のみ、関数が呼び出される場合、<xref:System.Windows.Forms.Control.Click>イベント ハンドラーとコードの他のいくつかの部分は、フォーム全体のフォント ファミリを変更、フォームの残りの部分では、テキスト ボックスは変更されません。  
  
```  
' Visual Basic  
Private Sub MakeBold()  
   ' Change the TextBox to a bold version of the form font  
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
   ' Clicking this button makes the TextBox bold  
   MakeBold()  
End Sub  
  
Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged  
   ' If the TextBox is already bold and the form's font changes,  
   ' change the TextBox to a bold version of the new form font  
   If (TextBox1.Font.Style = FontStyle.Bold) Then  
      MakeBold()  
   End If  
End Sub  
  
// C#  
private void button1_Click(object sender, System.EventArgs e)  
{  
   // Clicking this button makes the TextBox bold  
   MakeBold();  
}  
  
private void MakeBold()   
{  
   // Change the TextBox to a bold version of the form's font  
   textBox1.Font = new Font(this.Font, FontStyle.Bold);  
}  
  
private void Form1_FontChanged(object sender, System.EventArgs e)  
{  
   // If the TextBox is already bold and the form's font changes,  
   // change the TextBox to a bold version of the new form font  
   if (textBox1.Font.Style == FontStyle.Bold)   
   {  
      MakeBold();  
   }  
}  
```  
  
 ただし、アプリケーションをローカライズするときに太字のフォント可能性があります表示が不十分な特定の言語。 これに問題がある場合ローカライズで通常のテキストに太字のフォントを切り替えるオプションをします。 ローカリゼーションいない開発者は、通常とソース コードへのアクセスはありません、リソース ファイルにのみこのオプション処理リソース ファイルで設定します。 これを行うには、設定すると、<xref:System.Drawing.Font.Bold%2A>プロパティを`true`です。 これは、結果、ローカライザーが編集できる、リソース ファイルに書き出され、フォントを設定します。 後にコードを作成し、`InitializeComponent`フォントを再設定する方法、フォームのフォントに基づいていますが、リソース ファイルで指定されたフォント スタイルを使用します。  
  
```  
' Visual Basic  
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)  
  
// C#  
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);  
```  
  
## <a name="see-also"></a>関連項目  
 [Windows フォームのグローバル化](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)  
 [フォントとテキストの使用](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)

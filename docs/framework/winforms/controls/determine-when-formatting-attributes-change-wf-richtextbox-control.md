---
title: '方法: Windows フォームの RichTextBox コントロールにおける書式属性の変更を確認する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
ms.openlocfilehash: a90affde9de36f1c83d5b7c21b40580cdf53402e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308459"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="32c22-102">方法: Windows フォームの RichTextBox コントロールにおける書式属性の変更を確認する</span><span class="sxs-lookup"><span data-stu-id="32c22-102">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="32c22-103">Windows フォームの一般的な用途<xref:System.Windows.Forms.RichTextBox>コントロールがフォントのオプションや段落スタイルなどの属性を持つテキストを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="32c22-103">A common use of the Windows Forms <xref:System.Windows.Forms.RichTextBox> control is formatting text with attributes such as font options or paragraph styles.</span></span> <span data-ttu-id="32c22-104">アプリケーションは、多くのワード プロセッシング アプリケーションと同様に、ツールバーを表示できるように書式設定文字列のすべての変更を追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32c22-104">Your application may need to keep track of any changes in text formatting for the purpose of displaying a toolbar, as in many word-processing applications.</span></span>  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a><span data-ttu-id="32c22-105">属性の書式設定の変更に応答するには</span><span class="sxs-lookup"><span data-stu-id="32c22-105">To respond to changes in formatting attributes</span></span>  
  
1. <span data-ttu-id="32c22-106">コードを記述、<xref:System.Windows.Forms.RichTextBox.SelectionChanged>属性の値に応じて適切なアクションを実行するイベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="32c22-106">Write code in the <xref:System.Windows.Forms.RichTextBox.SelectionChanged> event handler to perform an appropriate action depending on the value of the attribute.</span></span> <span data-ttu-id="32c22-107">次の例の値に応じて、ツール バー ボタンの外観を変更する、<xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="32c22-107">The following example changes the appearance of a toolbar button depending on the value of the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="32c22-108">ツール バー ボタンは、コントロールのカーソルが移動したときにのみ更新されます。</span><span class="sxs-lookup"><span data-stu-id="32c22-108">The toolbar button will only be updated when the insertion point is moved in the control.</span></span>  
  
     <span data-ttu-id="32c22-109">次の例でフォームを前提としています、<xref:System.Windows.Forms.RichTextBox>コントロールと<xref:System.Windows.Forms.ToolBar>ツール バー ボタンを格納しているコントロール。</span><span class="sxs-lookup"><span data-stu-id="32c22-109">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control and a <xref:System.Windows.Forms.ToolBar> control that contains a toolbar button.</span></span> <span data-ttu-id="32c22-110">ツールバーとツールバー ボタンの詳細については、次を参照してください。[方法。ツール バー コントロールにボタンを追加](how-to-add-buttons-to-a-toolbar-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="32c22-110">For more information about toolbars and toolbar buttons, see [How to: Add Buttons to a ToolBar Control](how-to-add-buttons-to-a-toolbar-control.md).</span></span>  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)   
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else   
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="32c22-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="32c22-111">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="32c22-112">RichTextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="32c22-112">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="32c22-113">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="32c22-113">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)

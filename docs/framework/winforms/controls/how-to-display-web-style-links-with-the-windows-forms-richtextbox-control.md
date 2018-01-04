---
title: "方法 : Windows フォームの RichTextBox コントロールを使用して Web スタイルのリンクを表示する"
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
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80f794be15eae33ca4e28dc0cfe04872f63230b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>方法 : Windows フォームの RichTextBox コントロールを使用して Web スタイルのリンクを表示する
Windows フォーム<xref:System.Windows.Forms.RichTextBox>コントロールは、カラーや下線が引かれたとしての Web リンクを表示できます。 ウィンドウを開いてブラウザー表示のリンクがクリックされたときに、このリンク テキストで指定された Web サイト コードを記述することができます。  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>RichTextBox コントロールでの Web ページにリンクするには  
  
1.  設定、<xref:System.Windows.Forms.RichTextBox.Text%2A>プロパティを有効な URL (たとえば、"http://www.microsoft.com/") を含む文字列にします。  
  
2.  確認、<xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>プロパティに設定されている`true`(既定)。  
  
3.  新しいグローバル インスタンスを作成、<xref:System.Diagnostics.Process>オブジェクト。  
  
4.  イベント ハンドラーを記述、<xref:System.Windows.Forms.RichTextBox.LinkClicked>ブラウザーに必要なテキストを送信するイベントです。  
  
     次の例で、<xref:System.Windows.Forms.RichTextBox.LinkClicked>イベントで指定された URL を Internet Explorer のインスタンスを開き、<xref:System.Windows.Forms.RichTextBox.Text%2A>のプロパティ、<xref:System.Windows.Forms.RichTextBox>コントロール。 この例では、フォーム、<xref:System.Windows.Forms.RichTextBox>コントロール。  
  
    > [!IMPORTANT]
    >  呼び出し元に、<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>メソッドを使用する、<xref:System.Security.SecurityException>な特権がないため、部分的に信頼されたコンテキストでコードを実行している場合に例外です。 詳しくは、「[コード アクセス セキュリティの基礎](../../../../docs/framework/misc/code-access-security-basics.md)」をご覧ください。  
  
    ```vb  
    Public p As New System.Diagnostics.Process  
    Private Sub RichTextBox1_LinkClicked _  
       (ByVal sender As Object, ByVal e As _  
       System.Windows.Forms.LinkClickedEventArgs) _  
       Handles RichTextBox1.LinkClicked  
          ' Call Process.Start method to open a browser  
          ' with link text as URL.  
          p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText)  
    End Sub  
    ```  
  
    ```csharp  
    public System.Diagnostics.Process p = new System.Diagnostics.Process();  
  
    private void richTextBox1_LinkClicked(object sender,   
    System.Windows.Forms.LinkClickedEventArgs e)  
    {  
       // Call Process.Start method to open a browser  
       // with link text as URL.  
       p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText);  
    }  
    ```  
  
    ```cpp  
    public:  
       System::Diagnostics::Process ^ p;  
  
    private:  
       void richTextBox1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkClickedEventArgs ^  e)  
       {  
          // Call Process.Start method to open a browser  
          // with link text as URL.  
          p = System::Diagnostics::Process::Start("IExplore.exe",  
             e->LinkText);  
       }  
    ```  
  
     ([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) プロセスを初期化する必要があります`p`をフォームのコンス トラクターで、次のステートメントを含めることによって行うことができます。  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]、 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) フォームのコンストラクターに次のコードを挿入してイベント ハンドラーを登録します。  
  
    ```csharp  
    this.richTextBox1.LinkClicked += new   
       System.Windows.Forms.LinkClickedEventHandler  
       (this.richTextBox1_LinkClicked);  
    ```  
  
    ```cpp  
    this->richTextBox1->LinkClicked += gcnew  
       System::Windows::Forms::LinkClickedEventHandler  
       (this, &Form1::richTextBox1_LinkClicked);  
    ```  
  
     作業が完了したらを作成したプロセスをすぐに停止するのには重要です。 上に示したコードを参照する、コード プロセスを停止するようになります。  
  
    ```vb  
    Public Sub StopWebProcess()  
       p.Kill()  
    End Sub  
    ```  
  
    ```csharp  
    public void StopWebProcess()  
    {  
       p.Kill();  
    }  
    ```  
  
    ```cpp  
    public: void StopWebProcess()  
    {  
       p->Kill();  
    }  
    ```  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>  
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox コントロール](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Windows フォームで使用するコントロール](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)

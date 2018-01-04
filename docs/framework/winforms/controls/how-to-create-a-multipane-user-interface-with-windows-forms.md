---
title: "方法 : Windows フォームでマルチペイン ユーザー インターフェイスを作成する"
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
helpviewer_keywords:
- SplitContainer control [Windows Forms], examples
- ListView control [Windows Forms], examples
- RichTextBox control [Windows Forms], examples
- Panel control [Windows Forms], examples
- TreeView control [Windows Forms], examples
- Splitter control [Windows Forms], examples
ms.assetid: e79f6bcc-3740-4d1e-b46a-c5594d9b7327
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f29fb5fc4f873431471cd1c037446a5157d5f07c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms"></a>方法 : Windows フォームでマルチペイン ユーザー インターフェイスを作成する
Microsoft Outlook で使用される次のようなマルチペイン ユーザー インターフェイスを作成する次の手順で、**フォルダー**  ボックスの一覧、**メッセージ** ウィンドウで、および**プレビュー**ウィンドウです。 この方法は、主にコントロールをフォームにドッキングすることにより実現されます。  
  
 コントロールをドッキングするときは、親コンテナーの端にコントロールを固定するを決定します。 このため、設定した場合、<xref:System.Windows.Forms.SplitContainer.Dock%2A>プロパティを<xref:System.Windows.Forms.DockStyle.Right>コントロールの右エッジは、親コントロールの右端にドッキングされます。 さらに、ドッキングされたコントロールの端は、コンテナー コントロールの一致するようにサイズ変更されます。 方法の詳細については<xref:System.Windows.Forms.SplitContainer.Dock%2A>プロパティを参照してください[する方法: Windows フォームでのドッキング コントロール](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)です。  
  
 この手順では、配置で、<xref:System.Windows.Forms.SplitContainer>および他のコントロール、フォームではなく、アプリケーションの Microsoft Outlook を模倣する機能を追加します。  
  
 内のすべてのコントロールを配置するこのユーザー インターフェイスを作成する、<xref:System.Windows.Forms.SplitContainer>を含むコントロール、<xref:System.Windows.Forms.TreeView>左側のパネルのコントロールです。 右側のパネル、<xref:System.Windows.Forms.SplitContainer>コントロールには、2 つ目が含まれている<xref:System.Windows.Forms.SplitContainer>コントロールを<xref:System.Windows.Forms.ListView>上のコントロール、<xref:System.Windows.Forms.RichTextBox>コントロール。 これら<xref:System.Windows.Forms.SplitContainer>コントロールがフォーム上の他のコントロールの独立したサイズ変更を有効にします。 独自のカスタム ユーザー インターフェイスを作成するには、この手順の手法を適用することができます。  
  
### <a name="to-create-an-outlook-style-user-interface-programmatically"></a>Outlook スタイルのユーザー インターフェイスをプログラムで作成するには  
  
1.  フォーム内で、ユーザー インターフェイスを構成する各コントロールを宣言します。 この例では、使用、 <xref:System.Windows.Forms.TreeView>、 <xref:System.Windows.Forms.ListView>、 <xref:System.Windows.Forms.SplitContainer>、および<xref:System.Windows.Forms.RichTextBox>Microsoft Outlook のユーザー インターフェイスを模倣するためにコントロールできます。  
  
    ```vb  
    Private WithEvents treeView1 As System.Windows.Forms.TreeView  
    Private WithEvents listView1 As System.Windows.Forms.ListView  
    Private WithEvents richTextBox1 As System.Windows.Forms.RichTextBox  
    Private WithEvents splitContainer1 As _  
        System.Windows.Forms.SplitContainer  
    Private WithEvents splitContainer2 As _  
        System.Windows.Forms.SplitContainer  
    ```  
  
    ```csharp  
    private System.Windows.Forms.TreeView treeView1;  
    private System.Windows.Forms.ListView listView1;  
    private System.Windows.Forms.RichTextBox richTextBox1;  
    private System.Windows.Forms. SplitContainer splitContainer2;  
    private System.Windows.Forms. SplitContainer splitContainer1;  
    ```  
  
2.  ユーザー インターフェイスを定義するプロシージャを作成します。 次のコードは、Microsoft Outlook のユーザー インターフェイスは、フォームのようにするように、プロパティを設定します。 ただし、それらを異なる方法でドッキングやその他のコントロールを使用して、同じように柔軟性を他のユーザー インターフェイスを作成するだけくらい簡単です。  
  
    ```vb  
    Public Sub CreateOutlookUI()  
        ' Create an instance of each control being used.  
        Me.components = New System.ComponentModel.Container()  
        Me.treeView1 = New System.Windows.Forms.TreeView()  
        Me.listView1 = New System.Windows.Forms.ListView()  
        Me.richTextBox1 = New System.Windows.Forms.RichTextBox()  
        Me.splitContainer1 = New System.Windows.Forms.SplitContainer()  
        Me.splitContainer2= New System.Windows.Forms. SplitContainer()  
  
        ' Should you develop this into a working application,  
        ' use the AddHandler method to hook up event procedures here.  
  
        ' Set properties of TreeView control.  
        ' Use the With statement to avoid repetitive code.  
        With Me.treeView1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 0  
            .Nodes.Add("treeView")  
        End With  
  
    ' Set properties of ListView control.  
       With Me.listView1  
          .Dock = System.Windows.Forms.DockStyle.Top  
          .TabIndex = 2  
          .Items.Add("listView")  
       End With  
  
    ' Set properties of RichTextBox control.  
       With Me.richTextBox1  
          .Dock = System.Windows.Forms.DockStyle.Fill  
          .TabIndex = 3  
          .Text = "richTextBox1"  
       End With  
  
        ' Set properties of the first SplitContainer control.  
        With Me.splitContainer1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 1  
            .SplitterWidth = 4  
            .SplitterDistance = 150  
            .Orientation = Orientation.Horizontal  
            .Panel1.Controls.Add(Me.listView1)  
            .Panel2.Controls.Add(Me.richTextBox1)  
    End With  
  
        ' Set properties of the second SplitContainer control.  
        With Me.splitContainer2  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 4  
            .SplitterWidth = 4  
            .SplitterDistance = 100  
            .Panel1.Controls.Add(Me.treeView1)  
            .Panel2.Controls.Add(Me.SplitContainer1)  
    End With  
  
    ' Add the main SplitContainer control to the form.  
        Me.Controls.Add(Me.splitContainer2)  
        Me.Text = "Intricate UI Example"  
    End Sub  
    ```  
  
    ```csharp  
    public void createOutlookUI()  
    {  
        // Create an instance of each control being used.  
        treeView1 = new System.Windows.Forms.TreeView();  
        listView1 = new System.Windows.Forms.ListView();  
        richTextBox1 = new System.Windows.Forms.RichTextBox();  
        splitContainer2 = new System.Windows.Forms.SplitContainer();  
        splitContainer1 = new System.Windows.Forms.SplitContainer();  
  
        // Insert code here to hook up event methods.  
  
        // Set properties of TreeView control.  
        treeView1.Dock = System.Windows.Forms.DockStyle.Fill;  
        treeView1.TabIndex = 0;  
        treeView1.Nodes.Add("treeView");  
  
        // Set properties of ListView control.  
        listView1.Dock = System.Windows.Forms.DockStyle.Top;  
        listView1.TabIndex = 2;  
        listView1.Items.Add("listView");  
  
        // Set properties of RichTextBox control.  
        richTextBox1.Dock = System.Windows.Forms.DockStyle.Fill;  
        richTextBox1.TabIndex = 3;  
        richTextBox1.Text = "richTextBox1";  
  
        // Set properties of first SplitContainer control.  
        splitContainer1.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 1;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 150;  
        splitContainer2.Orientation = Orientation.Horizontal;  
        splitContainer2.Panel1.Controls.Add(this.listView1);  
        splitContainer2.Panel1.Controls.Add(this.richTextBox1);  
  
        // Set properties of second SplitContainer control.  
        splitContainer2.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 4;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 100;  
        splitContainer2.Panel1.Controls.Add(this.treeView1);  
        splitContainer2.Panel1.Controls.Add(this.splitContainer1);  
  
        // Add the main SplitContainer control to the form.  
        this.Controls.Add(this.splitContainer2);  
        this.Text = "Intricate UI Example";  
    }  
    ```  
  
3.  [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]で作成したプロシージャの呼び出しを追加、`New()`プロシージャです。 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]、フォーム クラスのコンス トラクターに次のコード行を追加します。  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
    ```  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.Forms.SplitContainer>  
 [SplitContainer コントロール](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)  
 [方法: デザイナーを使用して Windows フォームでマルチペイン ユーザー インターフェイスを作成する](../../../../docs/framework/winforms/controls/create-a-multipane-user-interface-with-wf-using-the-designer.md)

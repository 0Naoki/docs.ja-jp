---
title: "方法 : Windows フォーム LinkLabel コントロールの表示形式を変更する"
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
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7dc3963ab1b242ce8dce53d9bba996f52347679b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>方法 : Windows フォーム LinkLabel コントロールの表示形式を変更する
によって表示されるテキストを変更することができます、<xref:System.Windows.Forms.LinkLabel>さまざまな目的に合わせてコントロール。 たとえば、下線付きで特定の色で表示するテキストを設定してテキストをクリックすることができます、ユーザーに示すためによくあることを勧めします。 ユーザーは、テキストをクリックすると、異なる色に色を変更します。 この動作を制御するには、5 つの異なるプロパティを設定することができます。 <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>、 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>、 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>、 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>、および<xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>プロパティです。  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>LinkLabel コントロールの外観を変更するには  
  
1.  設定、<xref:System.Windows.Forms.LinkLabel.LinkColor%2A>と<xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>色のプロパティです。  
  
     これにいずれかのプログラムから、またはデザイン時に、**プロパティ**ウィンドウです。  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2.  設定、<xref:System.Windows.Forms.LinkLabel.Text%2A>プロパティに適切なキャプション。  
  
     これにいずれかのプログラムから、またはデザイン時に、**プロパティ**ウィンドウです。  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  設定、<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>プロパティのキャプションのどの部分がリンクとして示されます。  
  
     <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>値を表示、 <xref:System.Windows.Forms.LinkArea> 2 つの数値、文字の開始位置と文字数を含むです。 これにいずれかのプログラムから、またはデザイン時に、**プロパティ**ウィンドウです。  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  設定、<xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>プロパティを<xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>、 <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>、または<xref:System.Windows.Forms.LinkBehavior.NeverUnderline>です。  
  
     設定されている場合<xref:System.Windows.Forms.LinkBehavior.HoverUnderline>、によって決まりますキャプションの一部<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>にポインターを置いたときに下線のみです。  
  
5.  <xref:System.Windows.Forms.LinkLabel.LinkClicked> 、イベント ハンドラーを設定、<xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>プロパティを`true`です。  
  
     リンクにアクセスすると、色で通常の何らかの方法でその外観を変更することを共通であります。 指定された色に変更は、<xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>プロパティです。  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>  
 [LinkLabel コントロールの概要](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)  
 [方法: Windows フォーム LinkLabel コントロールでオブジェクトまたは Web ページにリンクする](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [LinkLabel コントロール](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)

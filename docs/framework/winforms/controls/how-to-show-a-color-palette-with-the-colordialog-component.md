---
title: '方法 : ColorDialog コンポーネントを使用してカラー パレットを表示する'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- palettes [Windows Forms], showing color
- color dialog box [Windows Forms], showing color palettes
- colors [Windows Forms], allowing users to select
- color palettes [Windows Forms], dialog box
- ColorDialog component [Windows Forms], showing color palettes
- color palettes [Windows Forms], showing in ColorDialog component
- colors [Windows Forms], showing palettes
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f3f75c6ec29b82c70d4160ccc40ddb9ced0ea711
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>方法 : ColorDialog コンポーネントを使用してカラー パレットを表示する
[ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)コンポーネント色のパレットを表示し、ユーザーが選択した色を含むプロパティを返します。  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>ColorDialog コンポーネントを使用する色を選択するには  
  
1.  ダイアログ ボックスを使用して、表示、<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>メソッドです。  
  
2.  使用して、<xref:System.Windows.Forms.DialogResult>プロパティ ダイアログ ボックスの終了方法を確認します。  
  
3.  使用して、<xref:System.Windows.Forms.ColorDialog.Color%2A>のプロパティ、<xref:System.Windows.Forms.ColorDialog>選択した色を設定するコンポーネントです。  
  
     次の例で、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Click>イベント ハンドラーが表示されます、<xref:System.Windows.Forms.ColorDialog>コンポーネントです。 ときに、色を選択し、ユーザーが**OK**、<xref:System.Windows.Forms.Button>コントロールの背景色が、選択した色に設定されています。 この例では、フォームには、<xref:System.Windows.Forms.Button>コントロールと<xref:System.Windows.Forms.ColorDialog>コンポーネントです。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     (Visual C# の場合、 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])、イベント ハンドラーを登録するフォームのコンス トラクターに次のコードを追加します。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.ColorDialog>  
 [ColorDialog コンポーネント](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)

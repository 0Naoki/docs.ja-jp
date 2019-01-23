---
title: '方法: MDI 子フォームを配置します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms [Windows Forms], arranging
- MDI [Windows Forms], arranging child forms
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
ms.openlocfilehash: 6e1e4f22aa70d8ee4d4122f9e77427c101b6713f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540742"
---
# <a name="how-to-arrange-mdi-child-forms"></a>方法: MDI 子フォームを配置します。
多くの場合、アプリケーションには、並べて表示、重ねて表示、整列など、開いている MDI 子フォームのレイアウトを制御するメニュー コマンドがあります。 <xref:System.Windows.Forms.Form.LayoutMdi%2A> メソッドと <xref:System.Windows.Forms.MdiLayout> 列挙値のいずれかを使用して、MDI 親フォーム内の子フォームを再配置することができます。  
  
 <xref:System.Windows.Forms.MdiLayout> 列挙値は、子フォームを重ねて表示したり、水平方向または垂直方向に並べて表示したり、または MDI フォームの下部に沿って整列された子フォーム アイコンとして表示します。 これらの値が、Windows のコマンドと同じ効果がある**重ねて**、 **windows を並べて表示**、**表示**、および**デスクトップを表示します。**、それぞれします。  
  
 多くの場合、これらのメソッドは、メニュー項目の <xref:System.Windows.Forms.Control.Click> イベントで呼び出されるイベント ハンドラーとして使用されます。 このようにして、テキスト "重ねて表示" を指定したメニュー項目に、MDI 子ウィンドウに対する目的の効果を持たせることができます。  
  
### <a name="to-arrange-child-forms"></a>子フォームを整列させるには  
  
1.  メソッドで、<xref:System.Windows.Forms.Form.LayoutMdi%2A> メソッドを使用して MDI 親フォームの <xref:System.Windows.Forms.MdiLayout> 列挙体を設定します。 次に、MDI 親フォーム (<xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType>) の子ウィンドウに `Form1` 列挙値を使用する例を示します。 コードでのイベント ハンドラーの中に、列挙が使用される、<xref:System.Windows.Forms.Control.Click>のイベント、 **Cascade Windows**メニュー項目。  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    >  使用する <xref:System.Windows.Forms.MdiLayout> 列挙値を変更することで、ウィンドウを並べて表示したり、ウィンドウをアイコンとして並べたりすることもできます。  
  
2.  Visual C# を使用している場合は、フォームのコンストラクターに次のコードを追加して、イベント ハンドラーを登録します。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## <a name="see-also"></a>関連項目
- [マルチ ドキュメント インターフェイス (MDI) アプリケーション](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)
- [方法: MDI 親フォームを作成します。](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)
- [方法: MDI 子フォームを作成します。](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)
- [方法: アクティブな MDI 子を決定します。](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)
- [方法: アクティブな MDI 子ウィンドウにデータを送信します。](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)

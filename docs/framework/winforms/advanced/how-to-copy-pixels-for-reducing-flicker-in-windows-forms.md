---
title: "方法 :ピクセルをコピーして Windows フォームのちらつきを低減する"
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
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17253e21739911d4aa0541fde9ae205b0be1c5a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>方法 :ピクセルをコピーして Windows フォームのちらつきを低減する
単純なグラフィックをアニメーション化するときにユーザーことができる場合もありますが発生ちらつき、またはその他の望ましくない視覚効果。 この問題を制限する 1 つの方法は、プロセスを使用して、"bitblt"画像の上です。 Bitblt は、「ビット ブロック転送」色データの元の四角形にはピクセルからピクセルの四角形に。  
  
 Windows フォームで bitblt が使用される、<xref:System.Drawing.Graphics.CopyFromScreen%2A>のメソッド、<xref:System.Drawing.Graphics>クラスです。 メソッドのパラメーターでは、ソースと宛先 (ポイント) として、コピーするのには、領域のサイズおよび新しい図形の描画に使用するグラフィックス オブジェクトを指定します。  
  
 次の例では、図形が描画されるフォームでその<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー。 次に、<xref:System.Drawing.Graphics.CopyFromScreen%2A>メソッドは、図形の複製に使用します。  
  
> [!NOTE]
>  設定、フォームの<xref:System.Windows.Forms.Control.DoubleBuffered%2A>プロパティを`true`でグラフィックス ベースのコードになります、<xref:System.Windows.Forms.Control.Paint>イベントとなるダブル バッファリングします。 ない、明確なパフォーマンスの向上と、次のコードを使用して、複雑なグラフィックス操作のコードを使用する場合に留意するものがあります。  
  
## <a name="example"></a>例  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 上記のコードをフォームの実行は<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー、フォームが再描画されると、グラフィックスが永続化できるようにします。 そのためグラフィックスに関連するメソッドを呼び出す必要はありません、 <xref:System.Windows.Forms.Form.Load> 、イベント ハンドラー描画済みのコンテンツが再描画されませんフォームがサイズ変更されるか、別の形式によって隠されるためです。  
  
## <a name="see-also"></a>参照  
 <xref:System.Drawing.CopyPixelOperation>  
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>  
 [Windows フォームにおけるグラフィックスと描画](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [ペンを使用した直線と図形の描画](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)

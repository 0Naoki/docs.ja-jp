---
title: '方法: 指定した位置のテキストの描画'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: e5a1791e21981f60e008b97a51d10f88b827de8d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660373"
---
# <a name="how-to-draw-text-at-a-specified-location"></a>方法: 指定した位置のテキストの描画
カスタム描画を実行するときに、指定された位置から始まる 1 つの水平方向にテキストを描画できます。 使用して、この方法でテキストを描画することができます、<xref:System.Drawing.Graphics.DrawString%2A>のメソッドをオーバー ロード、<xref:System.Drawing.Graphics>を受け取るクラス、<xref:System.Drawing.Point>または<xref:System.Drawing.PointF>パラメーター。 <xref:System.Drawing.Graphics.DrawString%2A>メソッドも必要になります、<xref:System.Drawing.Brush>と <xref:System.Drawing.Font>  
  
 使用することも、<xref:System.Windows.Forms.TextRenderer.DrawText%2A>のメソッドをオーバー ロード、<xref:System.Windows.Forms.TextRenderer>を受け取る、<xref:System.Drawing.Point>します。 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 必要です、<xref:System.Drawing.Color>と<xref:System.Drawing.Font>します。  
  
 次の図は、使用すると、特定の時点で描画されるテキストの出力、<xref:System.Drawing.Graphics.DrawString%2A>オーバー ロードされたメソッド。  
  
 ![フォント テキスト](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>GDI + でのテキストの線を描画するには  
  
1.  使用して、 <xref:System.Drawing.Graphics.DrawString%2A> 、テキストを渡すメソッド<xref:System.Drawing.Point>または<xref:System.Drawing.PointF>、 <xref:System.Drawing.Font>、および<xref:System.Drawing.Brush>します。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>GDI を使用してテキストの線を描画するには  
  
1.  使用して、 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 、テキストを渡すメソッド<xref:System.Drawing.Point>、 <xref:System.Drawing.Font>、および<xref:System.Drawing.Color>します。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例が必要です。  
  
-   <xref:System.Windows.Forms.PaintEventArgs>  `e`でのパラメーターである<xref:System.Windows.Forms.PaintEventHandler>します。  
  
## <a name="see-also"></a>関連項目
- [方法: GDI を使用してテキストを描画します。](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
- [フォントとテキストの使用](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [方法: フォント ファミリとフォントを作成します。](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
- [方法: 四角形内にテキストを折り返して描画](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)

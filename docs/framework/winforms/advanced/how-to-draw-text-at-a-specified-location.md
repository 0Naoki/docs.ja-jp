---
title: "方法 : テキストを指定の位置に描画する"
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
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text a a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aab9570b98caec5b3975a5b3ff6f1e62d4ad303b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-text-at-a-specified-location"></a>方法 : テキストを指定の位置に描画する
カスタム描画を実行するときに、指定した点から始まる 1 つの水平方向にテキストを描画できます。 使用して、この方法でテキストを描画することができます、<xref:System.Drawing.Graphics.DrawString%2A>オーバー ロードされたメソッドの<xref:System.Drawing.Graphics>を受け取るクラス、<xref:System.Drawing.Point>または<xref:System.Drawing.PointF>パラメーター。 <xref:System.Drawing.Graphics.DrawString%2A>メソッドも必要です、<xref:System.Drawing.Brush>と<xref:System.Drawing.Font>  
  
 使用することも、<xref:System.Windows.Forms.TextRenderer.DrawText%2A>オーバー ロードされたメソッドの<xref:System.Windows.Forms.TextRenderer>を受け取る、<xref:System.Drawing.Point>です。 <xref:System.Windows.Forms.TextRenderer.DrawText%2A>必要です、<xref:System.Drawing.Color>と<xref:System.Drawing.Font>です。  
  
 次の図に、使用すると、特定の時点で描画されるテキストの出力、<xref:System.Drawing.Graphics.DrawString%2A>オーバー ロードされたメソッドです。  
  
 ![フォント テキスト](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>GDI + でのテキストの線を描画するには  
  
1.  使用して、<xref:System.Drawing.Graphics.DrawString%2A>するは、テキストを渡すメソッド<xref:System.Drawing.Point>または<xref:System.Drawing.PointF>、 <xref:System.Drawing.Font>、および<xref:System.Drawing.Brush>です。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>GDI でテキストの線を描画するには  
  
1.  使用して、<xref:System.Windows.Forms.TextRenderer.DrawText%2A>メソッドをテキストを渡す<xref:System.Drawing.Point>、 <xref:System.Drawing.Font>、および<xref:System.Drawing.Color>です。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例が必要です。  
  
-   <xref:System.Windows.Forms.PaintEventArgs>  `e`、パラメーターのある<xref:System.Windows.Forms.PaintEventHandler>です。  
  
## <a name="see-also"></a>関連項目  
 [方法: GDI を使用してテキストを描画する](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [フォントとテキストの使用](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [方法: フォント ファミリとフォントを作成する](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [方法: 四角形内にテキストを折り返して描画する](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)

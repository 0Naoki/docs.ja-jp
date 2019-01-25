---
title: '方法: ライン キャップを持つ行を描画します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: a0d4d92d7201c4ac09eadd11d8f2e38a3c80c287
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713138"
---
# <a name="how-to-draw-a-line-with-line-caps"></a>方法: ライン キャップを持つ行を描画します。
ライン キャップと呼ばれるいくつかの図形のいずれかでは、先頭または末尾の行を描画できます。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] round、正方形、ひし形、および矢印などのいくつかのライン キャップをサポートしています。  
  
## <a name="example"></a>例  
 ライン キャップ (start cap) の行、行 (end cap) の末尾または破線 (ダッシュ cap) のダッシュの開始を指定することができます。  
  
 次の例では、線を一端にある矢印、もう一方の end ラウンド線端を描画します。 図は、その結果、行を示しています。  
  
 ![ペン](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
  
-   Windows フォームを作成し、フォームの処理<xref:System.Windows.Forms.Control.Paint>イベント。 例のコードを<xref:System.Windows.Forms.Control.Paint>イベント ハンドラーを渡す`e`として<xref:System.Windows.Forms.PaintEventArgs>します。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [Windows フォームにおけるグラフィックスと描画](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [ペンを使用した直線と図形の描画](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)

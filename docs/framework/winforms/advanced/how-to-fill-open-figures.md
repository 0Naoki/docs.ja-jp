---
title: '方法: 開いている図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: b4dd37decd86d625a9cdf8a6b4027dfaec0c0ff1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730751"
---
# <a name="how-to-fill-open-figures"></a>方法: 開いている図形を塗りつぶす
渡すことによって、パスを入力することができます、<xref:System.Drawing.Drawing2D.GraphicsPath>オブジェクトを<xref:System.Drawing.Graphics.FillPath%2A>メソッド。 <xref:System.Drawing.Graphics.FillPath%2A>メソッドは、塗りつぶしモード (代替またはワインディング) に応じて、パスに設定されているパスを入力します。 任意の開いている図形をパスには場合、は、これらの図形が閉じている場合、パスが入力されます。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] その終点からその開始点を直線を描画することで、図を閉じます。  
  
## <a name="example"></a>例  
 次の例では、1 つ開いている図 (円弧) と 1 つの閉じた図形 (楕円) を持つパスを作成します。 <xref:System.Drawing.Graphics.FillPath%2A>メソッドは既定の塗りつぶしモードに応じてパスを入力する<xref:System.Drawing.Drawing2D.FillMode.Alternate>します。  
  
 次の図は、コード例の出力を示します。 パスが格納されていることに注意してください (に従って<xref:System.Drawing.Drawing2D.FillMode.Alternate>) 場合と、その開始点を直線の終了点から、開いている図が閉じられました。  
  
 ![ファイルを開くパス](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [GDI+ でのグラフィックス パス](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)

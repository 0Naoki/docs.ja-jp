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
# <a name="how-to-fill-open-figures"></a><span data-ttu-id="b3ed9-102">方法: 開いている図形を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="b3ed9-102">How to: Fill Open Figures</span></span>
<span data-ttu-id="b3ed9-103">渡すことによって、パスを入力することができます、<xref:System.Drawing.Drawing2D.GraphicsPath>オブジェクトを<xref:System.Drawing.Graphics.FillPath%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="b3ed9-103">You can fill a path by passing a <xref:System.Drawing.Drawing2D.GraphicsPath> object to the <xref:System.Drawing.Graphics.FillPath%2A> method.</span></span> <span data-ttu-id="b3ed9-104"><xref:System.Drawing.Graphics.FillPath%2A>メソッドは、塗りつぶしモード (代替またはワインディング) に応じて、パスに設定されているパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b3ed9-104">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the fill mode (alternate or winding) currently set for the path.</span></span> <span data-ttu-id="b3ed9-105">任意の開いている図形をパスには場合、は、これらの図形が閉じている場合、パスが入力されます。</span><span class="sxs-lookup"><span data-stu-id="b3ed9-105">If the path has any open figures, the path is filled as if those figures were closed.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="b3ed9-106">その終点からその開始点を直線を描画することで、図を閉じます。</span><span class="sxs-lookup"><span data-stu-id="b3ed9-106">closes a figure by drawing a straight line from its ending point to its starting point.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3ed9-107">例</span><span class="sxs-lookup"><span data-stu-id="b3ed9-107">Example</span></span>  
 <span data-ttu-id="b3ed9-108">次の例では、1 つ開いている図 (円弧) と 1 つの閉じた図形 (楕円) を持つパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3ed9-108">The following example creates a path that has one open figure (an arc) and one closed figure (an ellipse).</span></span> <span data-ttu-id="b3ed9-109"><xref:System.Drawing.Graphics.FillPath%2A>メソッドは既定の塗りつぶしモードに応じてパスを入力する<xref:System.Drawing.Drawing2D.FillMode.Alternate>します。</span><span class="sxs-lookup"><span data-stu-id="b3ed9-109">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the default fill mode, which is <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span></span>  
  
 <span data-ttu-id="b3ed9-110">次の図は、コード例の出力を示します。</span><span class="sxs-lookup"><span data-stu-id="b3ed9-110">The following illustration shows the output of the example code.</span></span> <span data-ttu-id="b3ed9-111">パスが格納されていることに注意してください (に従って<xref:System.Drawing.Drawing2D.FillMode.Alternate>) 場合と、その開始点を直線の終了点から、開いている図が閉じられました。</span><span class="sxs-lookup"><span data-stu-id="b3ed9-111">Note that the path is filled (according to <xref:System.Drawing.Drawing2D.FillMode.Alternate>) as if the open figure were closed by a straight line from its ending point to its starting point.</span></span>  
  
 <span data-ttu-id="b3ed9-112">![ファイルを開くパス](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")</span><span class="sxs-lookup"><span data-stu-id="b3ed9-112">![Fill Open Path](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b3ed9-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b3ed9-113">Compiling the Code</span></span>  
 <span data-ttu-id="b3ed9-114">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="b3ed9-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ed9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3ed9-115">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="b3ed9-116">GDI+ でのグラフィックス パス</span><span class="sxs-lookup"><span data-stu-id="b3ed9-116">Graphics Paths in GDI+</span></span>](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)

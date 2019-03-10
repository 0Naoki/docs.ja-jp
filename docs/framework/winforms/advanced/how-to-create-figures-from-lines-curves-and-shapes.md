---
title: '方法: 直線、曲線、および形状から図形を作成します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: 1977f1c9efe2c379ef6039870aade300efca2bdd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709498"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a><span data-ttu-id="94db6-102">方法: 直線、曲線、および形状から図形を作成します。</span><span class="sxs-lookup"><span data-stu-id="94db6-102">How to: Create Figures from Lines, Curves, and Shapes</span></span>
<span data-ttu-id="94db6-103">図を作成するには、構築、<xref:System.Drawing.Drawing2D.GraphicsPath>などのメソッドを呼び出すと<xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>と<xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>にプリミティブを追加するパス。</span><span class="sxs-lookup"><span data-stu-id="94db6-103">To create a figure, construct a <xref:System.Drawing.Drawing2D.GraphicsPath>, and then call methods, such as <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, to add primitives to the path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94db6-104">例</span><span class="sxs-lookup"><span data-stu-id="94db6-104">Example</span></span>  
 <span data-ttu-id="94db6-105">次のコード例では、図形のパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94db6-105">The following code examples create paths that have figures:</span></span>  
  
-   <span data-ttu-id="94db6-106">最初の例では、1 つの図に、パスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94db6-106">The first example creates a path that has a single figure.</span></span> <span data-ttu-id="94db6-107">1 つの円弧の図で構成されます。これは既定の座標系に反時計回りに-180 度の掃引角度を円弧には。</span><span class="sxs-lookup"><span data-stu-id="94db6-107">The figure consists of a single arc. The arc has a sweep angle of –180 degrees, which is counterclockwise in the default coordinate system.</span></span>  
  
-   <span data-ttu-id="94db6-108">2 番目の例では、2 つの図に、パスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94db6-108">The second example creates a path that has two figures.</span></span> <span data-ttu-id="94db6-109">最初の図では、円弧が続く行です。</span><span class="sxs-lookup"><span data-stu-id="94db6-109">The first figure is an arc followed by a line.</span></span> <span data-ttu-id="94db6-110">2 番目の図は、後に続く行曲線行です。</span><span class="sxs-lookup"><span data-stu-id="94db6-110">The second figure is a line followed by a curve followed by a line.</span></span> <span data-ttu-id="94db6-111">最初の図は開いたままされ、2 番目の図が閉じられます。</span><span class="sxs-lookup"><span data-stu-id="94db6-111">The first figure is left open, and the second figure is closed.</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94db6-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="94db6-112">Compiling the Code</span></span>  
 <span data-ttu-id="94db6-113">前の例は、Windows フォームで使用するために設計されていて、必要な<xref:System.Windows.Forms.PaintEventArgs>`e`はのパラメーター、<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="94db6-113">The previous examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94db6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="94db6-114">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="94db6-115">パスの作成および描画</span><span class="sxs-lookup"><span data-stu-id="94db6-115">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
- [<span data-ttu-id="94db6-116">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="94db6-116">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)

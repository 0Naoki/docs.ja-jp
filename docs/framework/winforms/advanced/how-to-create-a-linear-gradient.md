---
title: '方法: 線形グラデーションを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: 540b6d422be5d5c0898f019592a755258145d14d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125022"
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="f9d47-102">方法: 線形グラデーションを作成する</span><span class="sxs-lookup"><span data-stu-id="f9d47-102">How to: Create a Linear Gradient</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="f9d47-103">水平方向、垂直方向、および対角線方向の線形グラデーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="f9d47-103">provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="f9d47-104">既定では、線形グラデーションの色を均一に変更します。</span><span class="sxs-lookup"><span data-stu-id="f9d47-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="f9d47-105">ただし、色が一様でない方法で変更されるように、線形グラデーションをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f9d47-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  
  
 <span data-ttu-id="f9d47-106">次の例では、線、楕円、および水平方向の線状グラデーション ブラシを四角形を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="f9d47-106">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
 <span data-ttu-id="f9d47-107"><xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A>コンス トラクターが 4 つの引数を受け取ります。 2 つのポイントと 2 つの色。</span><span class="sxs-lookup"><span data-stu-id="f9d47-107">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="f9d47-108">(0, 10) は、最初のポイントは最初の色 (赤) に関連付けられていると、2 番目の点 (200, 10) が 2 番目の色 (青) に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="f9d47-108">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="f9d47-109">想像どおりから描画される直線 (0, 10) に (200, 10) が赤から青に徐々 に変化します。</span><span class="sxs-lookup"><span data-stu-id="f9d47-109">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="f9d47-110">点 (50, 10) と (200, 10) で 10 件が重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="f9d47-110">The 10s in the points (50, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="f9d47-111">2 つのポイントが同じ 2 つ目の座標にあることが重要なは、それらを結ぶ線が水平方向。</span><span class="sxs-lookup"><span data-stu-id="f9d47-111">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="f9d47-112">楕円と四角形変更も徐々 に赤から青の水平方向の座標が 0 から 200 にようにできます。</span><span class="sxs-lookup"><span data-stu-id="f9d47-112">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="f9d47-113">次の図は、線、楕円、四角形を示します。</span><span class="sxs-lookup"><span data-stu-id="f9d47-113">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="f9d47-114">色のグラデーション繰り返される自体の水平方向座標が 200 を超えるとに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f9d47-114">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="f9d47-115">![線形グラデーション](./media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="f9d47-115">![Linear Gradient](./media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="f9d47-116">水平方向の線形グラデーションを使用するには</span><span class="sxs-lookup"><span data-stu-id="f9d47-116">To use horizontal linear gradients</span></span>  
  
-   <span data-ttu-id="f9d47-117">3 番目と 4 番目の引数として、それぞれ不透明な赤と不透明青を渡します。</span><span class="sxs-lookup"><span data-stu-id="f9d47-117">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="f9d47-118">色要素は前の例では 0 の水平座標から 200 の水平座標に移動すると直線的に変更します。</span><span class="sxs-lookup"><span data-stu-id="f9d47-118">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="f9d47-119">たとえば、最初の座標が 0 と 200 の中間点は、0 から 255 までの中間に位置が青要素があります。</span><span class="sxs-lookup"><span data-stu-id="f9d47-119">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="f9d47-120">他のグラデーションの 1 つのエッジから色が異なる方法を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="f9d47-120">allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="f9d47-121">黒から次の表に従って赤に変更されるグラデーション ブラシを作成するとします。</span><span class="sxs-lookup"><span data-stu-id="f9d47-121">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="f9d47-122">水平方向の座標</span><span class="sxs-lookup"><span data-stu-id="f9d47-122">Horizontal coordinate</span></span>|<span data-ttu-id="f9d47-123">RGB コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f9d47-123">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="f9d47-124">0</span><span class="sxs-lookup"><span data-stu-id="f9d47-124">0</span></span>|<span data-ttu-id="f9d47-125">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="f9d47-125">(0, 0, 0)</span></span>|  
|<span data-ttu-id="f9d47-126">40</span><span class="sxs-lookup"><span data-stu-id="f9d47-126">40</span></span>|<span data-ttu-id="f9d47-127">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="f9d47-127">(128, 0, 0)</span></span>|  
|<span data-ttu-id="f9d47-128">200</span><span class="sxs-lookup"><span data-stu-id="f9d47-128">200</span></span>|<span data-ttu-id="f9d47-129">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="f9d47-129">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="f9d47-130">水平座標が 0 から 200 の方法の 20% のみである場合に、赤のコンポーネントが半分の強さではことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f9d47-130">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="f9d47-131">次の例のセット、<xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A>のプロパティを<xref:System.Drawing.Drawing2D.LinearGradientBrush>に 3 つの相対強度を 3 つの相対位置に関連付けるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f9d47-131">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> property of a <xref:System.Drawing.Drawing2D.LinearGradientBrush> object to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="f9d47-132">上の表のように 0.5 の相対強度は 0.2 の相対位置に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="f9d47-132">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="f9d47-133">コードでは、楕円と四角形をグラデーション ブラシを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9d47-133">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="f9d47-134">次の図は、結果として得られる楕円と四角形を示します。</span><span class="sxs-lookup"><span data-stu-id="f9d47-134">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="f9d47-135">![線形グラデーション](./media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="f9d47-135">![Linear Gradient](./media/cslineargradient2.png "cslineargradient2")</span></span>  
  
### <a name="to-customize-linear-gradients"></a><span data-ttu-id="f9d47-136">線形グラデーションをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="f9d47-136">To customize linear gradients</span></span>  
  
-   <span data-ttu-id="f9d47-137">3 番目と 4 番目の引数として、それぞれ不透明な黒と不透明な赤を渡します。</span><span class="sxs-lookup"><span data-stu-id="f9d47-137">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="f9d47-138">上記の例のグラデーションを水平にされています。つまり、色は、水平線のいずれかに移動すると、段階的に変更します。</span><span class="sxs-lookup"><span data-stu-id="f9d47-138">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="f9d47-139">垂直方向のグラデーションと対角線方向のグラデーションを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f9d47-139">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="f9d47-140">次の例に、点 (0, 0) と (200, 100) を渡す、<xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A>コンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="f9d47-140">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="f9d47-141">青色の色が関連付けられている (0, 0) と、緑色の色が関連付けられます (200, 100)。</span><span class="sxs-lookup"><span data-stu-id="f9d47-141">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="f9d47-142">(ペンの幅が 10)、行と楕円は、線状グラデーション ブラシで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="f9d47-142">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="f9d47-143">次の図は、線、楕円を示します。</span><span class="sxs-lookup"><span data-stu-id="f9d47-143">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="f9d47-144">楕円内色徐々 にに沿って移動すると行のメモが並列に渡される行には (0, 0) と (200, 100)。</span><span class="sxs-lookup"><span data-stu-id="f9d47-144">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="f9d47-145">![線形グラデーション](./media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="f9d47-145">![Linear Gradient](./media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="f9d47-146">対角線方向の線形グラデーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="f9d47-146">To create diagonal linear gradients</span></span>  
  
-   <span data-ttu-id="f9d47-147">3 番目と 4 番目の引数として、それぞれ不透明青と不透明な緑を渡します。</span><span class="sxs-lookup"><span data-stu-id="f9d47-147">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="f9d47-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9d47-148">See also</span></span>

- [<span data-ttu-id="f9d47-149">グラデーション ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="f9d47-149">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
- [<span data-ttu-id="f9d47-150">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="f9d47-150">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)

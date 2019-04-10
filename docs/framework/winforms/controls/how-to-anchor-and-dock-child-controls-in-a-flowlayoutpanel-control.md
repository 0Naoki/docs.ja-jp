---
title: '方法: FlowLayoutPanel コントロールで子コントロールを固定およびドッキングする'
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms], child controls
- FlowLayoutPanel control [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
ms.openlocfilehash: 255ac50ae79d6931c9b82b50677c450c0834fdea
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329038"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="73ef4-102">方法: FlowLayoutPanel コントロールで子コントロールを固定およびドッキングする</span><span class="sxs-lookup"><span data-stu-id="73ef4-102">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>
<span data-ttu-id="73ef4-103"><xref:System.Windows.Forms.FlowLayoutPanel> コントロールは、子コントロールの <xref:System.Windows.Forms.Control.Anchor%2A> プロパティと <xref:System.Windows.Forms.Control.Dock%2A> プロパティをサポートします。</span><span class="sxs-lookup"><span data-stu-id="73ef4-103">The <xref:System.Windows.Forms.FlowLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>  
  
### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="73ef4-104">FlowLayoutPanel コントロールで子コントロールを固定およびドッキングするには</span><span class="sxs-lookup"><span data-stu-id="73ef4-104">To anchor and dock child controls in a FlowLayoutPanel control</span></span>  
  
1. <span data-ttu-id="73ef4-105">フォームで <xref:System.Windows.Forms.FlowLayoutPanel> コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="73ef4-105">Create a <xref:System.Windows.Forms.FlowLayoutPanel> control on your form.</span></span>  
  
2. <span data-ttu-id="73ef4-106">設定、<xref:System.Windows.Forms.Control.Width%2A>の<xref:System.Windows.Forms.FlowLayoutPanel>に制御を**300**、設定とその<xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>に<xref:System.Windows.Forms.FlowDirection.TopDown>します。</span><span class="sxs-lookup"><span data-stu-id="73ef4-106">Set the <xref:System.Windows.Forms.Control.Width%2A> of the <xref:System.Windows.Forms.FlowLayoutPanel> control to **300**, and set its <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> to <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>  
  
3. <span data-ttu-id="73ef4-107">2 つの <xref:System.Windows.Forms.Button> コントロールを作成し、<xref:System.Windows.Forms.FlowLayoutPanel> コントロールに配置します。</span><span class="sxs-lookup"><span data-stu-id="73ef4-107">Create two <xref:System.Windows.Forms.Button> controls, and place them in the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
4. <span data-ttu-id="73ef4-108">設定、<xref:System.Windows.Forms.Control.Width%2A>に最初のボタンの**200**します。</span><span class="sxs-lookup"><span data-stu-id="73ef4-108">Set the <xref:System.Windows.Forms.Control.Width%2A> of the first button to **200**.</span></span>  
  
5. <span data-ttu-id="73ef4-109">2 番目のボタンの <xref:System.Windows.Forms.Control.Dock%2A> プロパティを <xref:System.Windows.Forms.DockStyle.Fill> に設定します。</span><span class="sxs-lookup"><span data-stu-id="73ef4-109">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73ef4-110">2 番目のボタンは、最初のボタンと同じ幅を前提としています。</span><span class="sxs-lookup"><span data-stu-id="73ef4-110">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="73ef4-111"><xref:System.Windows.Forms.FlowLayoutPanel> コントロールの幅にまたがって伸縮しません。</span><span class="sxs-lookup"><span data-stu-id="73ef4-111">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
6. <span data-ttu-id="73ef4-112">2 番目のボタンの <xref:System.Windows.Forms.Control.Dock%2A> プロパティを `None` に設定します。</span><span class="sxs-lookup"><span data-stu-id="73ef4-112">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to `None`.</span></span> <span data-ttu-id="73ef4-113">これにより、元の幅のボタンを前提とします。</span><span class="sxs-lookup"><span data-stu-id="73ef4-113">This causes the button to assume its original width.</span></span>  
  
7. <span data-ttu-id="73ef4-114">2 番目のボタンの <xref:System.Windows.Forms.Control.Anchor%2A> プロパティを `Left, Right` に設定します。</span><span class="sxs-lookup"><span data-stu-id="73ef4-114">Set the <xref:System.Windows.Forms.Control.Anchor%2A> property of the second button to `Left, Right`.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="73ef4-115">2 番目のボタンは、最初のボタンと同じ幅を前提としています。</span><span class="sxs-lookup"><span data-stu-id="73ef4-115">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="73ef4-116"><xref:System.Windows.Forms.FlowLayoutPanel> コントロールの幅にまたがって伸縮しません。</span><span class="sxs-lookup"><span data-stu-id="73ef4-116">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="73ef4-117">これは、<xref:System.Windows.Forms.FlowLayoutPanel> コントロールの固定とドッキングの一般的な規則です。垂直方向のフローについては、<xref:System.Windows.Forms.FlowLayoutPanel> コントロールが、幅の最大の列の子コントロールから暗黙の列の幅を計算します。</span><span class="sxs-lookup"><span data-stu-id="73ef4-117">This is the general rule for anchoring and docking in the <xref:System.Windows.Forms.FlowLayoutPanel> control: for vertical flow directions, the <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the width of an implied column from the widest child control in the column.</span></span> <span data-ttu-id="73ef4-118"><xref:System.Windows.Forms.Control.Anchor%2A> プロパティまたは <xref:System.Windows.Forms.Control.Dock%2A> プロパティを持つこの列のその他のすべてのコントロールが、この暗黙の列に合わせて配置または拡大されます。</span><span class="sxs-lookup"><span data-stu-id="73ef4-118">All other controls in this column with <xref:System.Windows.Forms.Control.Anchor%2A> or <xref:System.Windows.Forms.Control.Dock%2A> properties are aligned or stretched to fit this implied column.</span></span> <span data-ttu-id="73ef4-119">この動作は、水平のフロー方向と同様の方法で機能します。</span><span class="sxs-lookup"><span data-stu-id="73ef4-119">The behavior works in a similar way for horizontal flow directions.</span></span> <span data-ttu-id="73ef4-120"><xref:System.Windows.Forms.FlowLayoutPanel> コントロールは、行で最も高い子コントロールから、暗黙の行の高さを計算して、この行のすべてのドッキングまたは固定の子コントロールは、暗黙の行に合わせて配置またはサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="73ef4-120">The <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the height of an implied row from the tallest child control in the row, and all docked or anchored child controls in this row are aligned or sized to fit the implied row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73ef4-121">例</span><span class="sxs-lookup"><span data-stu-id="73ef4-121">Example</span></span>  
 <span data-ttu-id="73ef4-122">次の図は、<xref:System.Windows.Forms.FlowLayoutPanel> 内の青のボタンを基準とする相対位置に固定されてドッキングされる 4 つのボタンを示しています。</span><span class="sxs-lookup"><span data-stu-id="73ef4-122">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="73ef4-123"><xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> が <xref:System.Windows.Forms.FlowDirection.LeftToRight> です。</span><span class="sxs-lookup"><span data-stu-id="73ef4-123">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.LeftToRight>.</span></span>  
  
 <span data-ttu-id="73ef4-124">![FlowLayoutPanel アンカー](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span><span class="sxs-lookup"><span data-stu-id="73ef4-124">![FlowLayoutPanel anchoring](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span></span>  
  
 <span data-ttu-id="73ef4-125">次の図は、<xref:System.Windows.Forms.FlowLayoutPanel> 内の青のボタンを基準とする相対位置に固定されてドッキングされる 4 つのボタンを示しています。</span><span class="sxs-lookup"><span data-stu-id="73ef4-125">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="73ef4-126"><xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> が <xref:System.Windows.Forms.FlowDirection.TopDown> です。</span><span class="sxs-lookup"><span data-stu-id="73ef4-126">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>  
  
 <span data-ttu-id="73ef4-127">![FlowLayoutPanel アンカー](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="73ef4-127">![FlowLayoutPanel anchoring](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span></span>  
  
 <span data-ttu-id="73ef4-128">次のコード例は、<xref:System.Windows.Forms.FlowLayoutPanel> コントロールの <xref:System.Windows.Forms.Button> コントロールにおける様々な <xref:System.Windows.Forms.Control.Anchor%2A> プロパティの値を示します。</span><span class="sxs-lookup"><span data-stu-id="73ef4-128">The following code example demonstrates various <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73ef4-129">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="73ef4-129">Compiling the Code</span></span>  
 <span data-ttu-id="73ef4-130">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="73ef4-130">This example requires:</span></span>  
  
-   <span data-ttu-id="73ef4-131">System、System.Data、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="73ef4-131">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="73ef4-132">コマンドラインからこの例を Visual Basic または Visual C# の構築方法の詳細については、[、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73ef4-132">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="73ef4-133">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="73ef4-133">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73ef4-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="73ef4-134">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="73ef4-135">FlowLayoutPanel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="73ef4-135">FlowLayoutPanel Control Overview</span></span>](flowlayoutpanel-control-overview.md)

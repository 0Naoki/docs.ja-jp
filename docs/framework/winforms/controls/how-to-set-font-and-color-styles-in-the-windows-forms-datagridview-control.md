---
title: '方法: Windows フォームの DataGridView コントロールのフォントと色のスタイルを設定します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell customization
- data grids [Windows Forms], customizing cells
- data grids [Windows Forms], font styles
- data grids [Windows Forms], color styles
ms.assetid: 588f2c57-d963-41b1-9c1d-d02d71818113
ms.openlocfilehash: 2476c7e972e5ba742c499c53ed689efca41cd148
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723908"
---
# <a name="how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="ec88b-102">方法: Windows フォームの DataGridView コントロールのフォントと色のスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="ec88b-102">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="ec88b-103"><xref:System.Windows.Forms.DataGridViewCellStyle> クラスのプロパティを設定して、<xref:System.Windows.Forms.DataGridView> コントロール内のセルの外観を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ec88b-103">You can specify the visual appearance of cells within a <xref:System.Windows.Forms.DataGridView> control by setting properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span> <span data-ttu-id="ec88b-104"><xref:System.Windows.Forms.DataGridView> クラスとコンパニオン クラスのさまざまなプロパティからこのクラスのインスタンスを取得することも、これらのプロパティの割り当てに <xref:System.Windows.Forms.DataGridViewCellStyle> オブジェクトをインスタンス化することもできます。</span><span class="sxs-lookup"><span data-stu-id="ec88b-104">You can retrieve instances of this class from various properties of the <xref:System.Windows.Forms.DataGridView> class and its companion classes, or you can instantiate <xref:System.Windows.Forms.DataGridViewCellStyle> objects for assignment to these properties.</span></span>  
  
 <span data-ttu-id="ec88b-105">次の手順は、<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> プロパティを使用したセルの外観の基本的なカスタマイズを示します。</span><span class="sxs-lookup"><span data-stu-id="ec88b-105">The following procedures demonstrate basic customization of cell appearance using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property.</span></span> <span data-ttu-id="ec88b-106">コントロール内のすべてのセルは、列、行、またはセル レベルでオーバーライドされるのでない限り、このプロパティで指定されたスタイルを継承します。</span><span class="sxs-lookup"><span data-stu-id="ec88b-106">Every cell in the control inherits the styles specified through this property unless they are overridden at the column, row, or cell level.</span></span> <span data-ttu-id="ec88b-107">スタイルの継承の例は、次を参照してください。[方法。Windows フォーム DataGridView コントロールの既定のセル スタイルを設定](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec88b-107">For an example of style inheritance, see [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="ec88b-108"><xref:System.Windows.Forms.DataGridViewCellStyle> クラスのその他の使用方法については、[参照] セクションの各トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec88b-108">For information about additional uses of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, see the topics listed in the See Also section.</span></span>  
  
 <span data-ttu-id="ec88b-109">Visual Studio では、このタスクに対する広範なサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ec88b-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="ec88b-110">参照してください[方法。既定のセル スタイルとデータ形式を Windows フォーム DataGridView コントロールのデザイナーを使用して設定](default-cell-styles-datagridview.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec88b-110">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](default-cell-styles-datagridview.md).</span></span>  
  
### <a name="to-specify-the-font-used-by-datagridview-cells"></a><span data-ttu-id="ec88b-111">DataGridView セルで使用されるフォントを指定するには</span><span class="sxs-lookup"><span data-stu-id="ec88b-111">To specify the font used by DataGridView cells</span></span>  
  
-   <span data-ttu-id="ec88b-112"><xref:System.Windows.Forms.DataGridViewCellStyle> の <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ec88b-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="ec88b-113">次のコード例では、コントロール全体のフォントを設定する <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="ec88b-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the font for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-datagridview-cells"></a><span data-ttu-id="ec88b-114">DataGridView セルの前景色と背景色を指定するには</span><span class="sxs-lookup"><span data-stu-id="ec88b-114">To specify the foreground and background colors of DataGridView cells</span></span>  
  
-   <span data-ttu-id="ec88b-115"><xref:System.Windows.Forms.DataGridViewCellStyle> の <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> プロパティと <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ec88b-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> and <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> properties of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="ec88b-116">次のコード例では、コントロール全体にこれらのスタイルを設定する <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="ec88b-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set these styles for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-selected-datagridview-cells"></a><span data-ttu-id="ec88b-117">選択された DataGridView セルの前景色と背景色を指定するには</span><span class="sxs-lookup"><span data-stu-id="ec88b-117">To specify the foreground and background colors of selected DataGridView cells</span></span>  
  
-   <span data-ttu-id="ec88b-118"><xref:System.Windows.Forms.DataGridViewCellStyle> の <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> プロパティと <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ec88b-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> and <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> properties of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="ec88b-119">次のコード例では、コントロール全体にこれらのスタイルを設定する <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="ec88b-119">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set these styles for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## <a name="example"></a><span data-ttu-id="ec88b-120">例</span><span class="sxs-lookup"><span data-stu-id="ec88b-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ec88b-121">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ec88b-121">Compiling the Code</span></span>  
 <span data-ttu-id="ec88b-122">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ec88b-122">This example requires:</span></span>  
  
-   <span data-ttu-id="ec88b-123">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="ec88b-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="ec88b-124"><xref:System?displayProperty=nameWithType>、<xref:System.Drawing?displayProperty=nameWithType>、および <xref:System.Windows.Forms?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="ec88b-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ec88b-125">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="ec88b-125">Robust Programming</span></span>  
 <span data-ttu-id="ec88b-126">最大限のスケーラビリティを実現するには、各要素のスタイルのプロパティを個別に設定するのではなく、同じスタイルを使用する複数の行、列、またはセルで <xref:System.Windows.Forms.DataGridViewCellStyle> オブジェクトを共有してください。</span><span class="sxs-lookup"><span data-stu-id="ec88b-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="ec88b-127">詳細については、[Windows フォーム DataGridView コントロールを拡張するためのベスト プラクティス](best-practices-for-scaling-the-windows-forms-datagridview-control.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec88b-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec88b-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec88b-128">See also</span></span>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="ec88b-129">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="ec88b-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="ec88b-130">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="ec88b-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)

---
title: '方法: Windows フォームの DataGridView コントロールの既定のセル スタイルを設定します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
ms.openlocfilehash: c7ece81e193f29960f29b749438280bbff0591f9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703128"
---
# <a name="how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="5dfbc-102">方法: Windows フォームの DataGridView コントロールの既定のセル スタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-102">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5dfbc-103">
  <xref:System.Windows.Forms.DataGridView> コントロールを使用して、コントロール全体、および特定の列と行の既定のセル スタイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-103">With the <xref:System.Windows.Forms.DataGridView> control, you can specify default cell styles for the entire control and for specific columns and rows.</span></span> <span data-ttu-id="5dfbc-104">これらは既定でフィルターを下に移動し、コントロール レベルから列レベルへ、次に行レベルへ、その次にセル レベルへ移動します。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-104">These defaults filter down from the control level to the column level, then to the row level, then to the cell level.</span></span> <span data-ttu-id="5dfbc-105">特定の <xref:System.Windows.Forms.DataGridViewCellStyle> プロパティがセル レベルで設定されていないと、行レベルで既定のプロパティの設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-105">If a particular <xref:System.Windows.Forms.DataGridViewCellStyle> property is not set at the cell level, the default property setting at the row level is used.</span></span> <span data-ttu-id="5dfbc-106">行レベルでもプロパティが設定されていない場合、既定の列の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-106">If the property is also not set at the row level, the default column setting is used.</span></span> <span data-ttu-id="5dfbc-107">最後に、列レベルでもプロパティが設定されていない場合、既定の <xref:System.Windows.Forms.DataGridView> の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-107">Finally, if the property is also not set at the column level, the default <xref:System.Windows.Forms.DataGridView> setting is used.</span></span> <span data-ttu-id="5dfbc-108">この設定により、複数のレベルでプロパティの設定を複製する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-108">With this setting, you can avoid having to duplicate the property settings at multiple levels.</span></span> <span data-ttu-id="5dfbc-109">各レベルでは、上位のレベルとは異なるスタイルだけを指定します。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-109">At each level, simply specify the styles that differ from the levels above it.</span></span> <span data-ttu-id="5dfbc-110">詳細については、次を参照してください。 [Windows フォームの DataGridView コントロールのセル スタイル](cell-styles-in-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-110">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="5dfbc-111">Visual Studio では、このタスクに対する広範なサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-111">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="5dfbc-112">参照してください[方法。既定のセル スタイルとデータ形式を Windows フォーム DataGridView コントロールのデザイナーを使用して設定](default-cell-styles-datagridview.md)します。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-112">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](default-cell-styles-datagridview.md).</span></span>  
  
### <a name="to-set-the-default-cell-styles-programmatically"></a><span data-ttu-id="5dfbc-113">既定値のセル スタイルをプログラムで設定するには</span><span class="sxs-lookup"><span data-stu-id="5dfbc-113">To set the default cell styles programmatically</span></span>  
  
1.  <span data-ttu-id="5dfbc-114">
  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> プロパティによって取得された <xref:System.Windows.Forms.DataGridViewCellStyle> のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-114">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> retrieved through the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2.  <span data-ttu-id="5dfbc-115">複数の行と列によって使用される新しい <xref:System.Windows.Forms.DataGridViewCellStyle> オブジェクトを作成して初期化します。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-115">Create and initialize new <xref:System.Windows.Forms.DataGridViewCellStyle> objects for use by multiple rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3.  <span data-ttu-id="5dfbc-116">特定の行と列の `DefaultCellStyle` プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-116">Set the `DefaultCellStyle` property of specific rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## <a name="example"></a><span data-ttu-id="5dfbc-117">例</span><span class="sxs-lookup"><span data-stu-id="5dfbc-117">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5dfbc-118">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5dfbc-118">Compiling the Code</span></span>  
 <span data-ttu-id="5dfbc-119">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-119">This example requires:</span></span>  
  
-   <span data-ttu-id="5dfbc-120">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-120">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="5dfbc-121">
  <xref:System?displayProperty=nameWithType>、<xref:System.Drawing?displayProperty=nameWithType>、および <xref:System.Windows.Forms?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-121">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5dfbc-122">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="5dfbc-122">Robust Programming</span></span>  
 <span data-ttu-id="5dfbc-123">非常に大きなデータ セットを処理するときに最大限のスケーラビリティを実現するには、各要素のスタイルのプロパティを個別に設定するのではなく、同じスタイルを使用する複数の行、列、またはセルで <xref:System.Windows.Forms.DataGridViewCellStyle> オブジェクトを共有してください。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-123">To achieve maximum scalability when you work with very large data sets, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than set the style properties for individual elements separately.</span></span> <span data-ttu-id="5dfbc-124">さらに、<xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> プロパティを使用して、共有された行を作成してアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-124">Additionally, you should create shared rows and access them by using the <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="5dfbc-125">詳細については、次を参照してください。 [Windows フォーム DataGridView コントロールを拡張するためのベスト プラクティス](best-practices-for-scaling-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-125">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dfbc-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="5dfbc-126">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5dfbc-127">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="5dfbc-127">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5dfbc-128">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="5dfbc-128">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5dfbc-129">Windows フォーム DataGridView コントロールを拡張するための推奨される手順</span><span class="sxs-lookup"><span data-stu-id="5dfbc-129">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5dfbc-130">方法: Windows フォームの DataGridView コントロールの交互の行のスタイル設定します。</span><span class="sxs-lookup"><span data-stu-id="5dfbc-130">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)

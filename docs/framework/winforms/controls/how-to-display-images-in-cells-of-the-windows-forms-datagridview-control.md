---
title: '方法: Windows フォーム DataGridView コントロールのセルにイメージを表示'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: 637cb2f51e8ad1161b0208a3ebd8337859261a11
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523598"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="8b97e-102">方法: Windows フォーム DataGridView コントロールのセルにイメージを表示</span><span class="sxs-lookup"><span data-stu-id="8b97e-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8b97e-103">画像またはグラフィックは、データの行で表示できる値のいずれか。</span><span class="sxs-lookup"><span data-stu-id="8b97e-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="8b97e-104">多くの場合、これらのグラフィックな従業員の写真や会社のロゴの形式になります。</span><span class="sxs-lookup"><span data-stu-id="8b97e-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="8b97e-105">内のデータを表示するときに画像を組み込むことは簡単、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="8b97e-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="8b97e-106"><xref:System.Windows.Forms.DataGridView>コントロールがネイティブでサポートされている任意のイメージ形式を処理、 <xref:System.Drawing.Image> OLE と同様に、クラス図の一部のデータベースで使用される形式。</span><span class="sxs-lookup"><span data-stu-id="8b97e-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="8b97e-107">場合、<xref:System.Windows.Forms.DataGridView>コントロールのデータ ソースのイメージの列がある、によって自動的に表示されます、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="8b97e-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="8b97e-108">次のコード例では、埋め込みリソースからアイコンを抽出し、image 列のすべてのセルに表示するためのビットマップに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8b97e-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="8b97e-109">対応するイメージとテキストのセルの値を置換する別の例では、次を参照してください。[方法。Windows フォーム DataGridView コントロールでデータの書式設定をカスタマイズ](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="8b97e-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b97e-110">例</span><span class="sxs-lookup"><span data-stu-id="8b97e-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8b97e-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="8b97e-111">Compiling the Code</span></span>  
 <span data-ttu-id="8b97e-112">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8b97e-112">This example requires:</span></span>  
  
-   <span data-ttu-id="8b97e-113">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="8b97e-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="8b97e-114">という名前の埋め込まれたアイコン リソース`tree.ico`します。</span><span class="sxs-lookup"><span data-stu-id="8b97e-114">An embedded icon resource named `tree.ico`.</span></span>  
  
-   <span data-ttu-id="8b97e-115"><xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、および <xref:System.Drawing?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="8b97e-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b97e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b97e-116">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="8b97e-117">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="8b97e-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="8b97e-118">方法: Windows フォーム DataGridView コントロールでデータの書式設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="8b97e-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)

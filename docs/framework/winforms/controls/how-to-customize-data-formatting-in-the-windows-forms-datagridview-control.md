---
title: '方法: Windows フォーム DataGridView コントロールでデータの書式設定をカスタマイズします。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], changing colors in DataGridView control [Windows Forms]
- colors [Windows Forms], changing in DataGridView control [Windows Forms]
- data [Windows Forms], formatting in DataGridView control
- DataGridView control [Windows Forms], cell customization
- DataGridView control [Windows Forms], changing cell colors
- Windows Forms, changing colors of DataGridView cells
- DataGridView control [Windows Forms], substituting cell values for display
- data grids [Windows Forms], formatting data
ms.assetid: a6e72c70-ce18-425f-828d-d57be6f96ab6
ms.openlocfilehash: 4a7e74afa985d36281994078bd0ea464f084cfa9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714906"
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fe2f3-102">方法: Windows フォーム DataGridView コントロールでデータの書式設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="fe2f3-102">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fe2f3-103">次のコード例は、列と値に応じてセルの表示方法を変更する<xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> イベントのハンドラーを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe2f3-103">The following code example demonstrates how to implement a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event that changes how cells are displayed depending on their columns and values.</span></span>  
  
 <span data-ttu-id="fe2f3-104">負の数値が含まれている `Balance` 列のセルは、赤の背景が指定されます。</span><span class="sxs-lookup"><span data-stu-id="fe2f3-104">Cells in the `Balance` column that contain negative numbers are given a red background.</span></span> <span data-ttu-id="fe2f3-105">これらのセルを通貨として書式設定し、負の値をかっこで囲んで表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe2f3-105">You can also format these cells as currency to display parentheses around negative values.</span></span> <span data-ttu-id="fe2f3-106">詳細については、「[方法 :書式設定データの Windows フォーム DataGridView コントロール](how-to-format-data-in-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="fe2f3-106">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="fe2f3-107">`Priority` 列のセルは、対応するテキスト セル値の代わりにイメージを表示します。</span><span class="sxs-lookup"><span data-stu-id="fe2f3-107">Cells in the `Priority` column display images in place of corresponding textual cell values.</span></span> <span data-ttu-id="fe2f3-108">
  <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> の<xref:System.Windows.Forms.ConvertEventArgs.Value%2A> プロパティはテキストのセル値を取得して、対応するイメージの表示値に設定する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe2f3-108">The <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property of the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> is used both to get the textual cell value and to set the corresponding image display value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe2f3-109">例</span><span class="sxs-lookup"><span data-stu-id="fe2f3-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fe2f3-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="fe2f3-110">Compiling the Code</span></span>  
 <span data-ttu-id="fe2f3-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fe2f3-111">This example requires:</span></span>  
  
-   <span data-ttu-id="fe2f3-112">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="fe2f3-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="fe2f3-113">`highPri.bmp`、`mediumPri.bmp`、および `lowPri.bmp` という名前の <xref:System.Drawing.Bitmap> イメージは、実行可能ファイルと同じディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="fe2f3-113"><xref:System.Drawing.Bitmap> images named `highPri.bmp`, `mediumPri.bmp`, and `lowPri.bmp` residing in the same directory as the executable file.</span></span>  
  
 <span data-ttu-id="fe2f3-114">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、[、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe2f3-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fe2f3-115">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe2f3-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe2f3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe2f3-116">See also</span></span>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Drawing.Bitmap>
- [<span data-ttu-id="fe2f3-117">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="fe2f3-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fe2f3-118">方法: 書式設定データの Windows フォーム DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="fe2f3-118">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fe2f3-119">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="fe2f3-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fe2f3-120">Windows フォーム DataGridView コントロールでのデータの書式設定</span><span class="sxs-lookup"><span data-stu-id="fe2f3-120">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)

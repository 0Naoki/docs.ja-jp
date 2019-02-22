---
title: '方法: Windows フォームの DataGridView コントロールで行の追加および削除を防ぐ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], disabling data entry
- data entry [Windows Forms], disabling in grids
- data grids [Windows Forms], disabling data entry
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
ms.openlocfilehash: 9f579720b4f3ff561ecd807e09db8d464abc9001
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664589"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b1430-102">方法: Windows フォームの DataGridView コントロールで行の追加および削除を防ぐ</span><span class="sxs-lookup"><span data-stu-id="b1430-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b1430-103">場合によっては、ユーザーが <xref:System.Windows.Forms.DataGridView> コントロールに新しいデータ行を入力したり、既存の行を削除したりできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1430-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b1430-104"><xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> プロパティは新しいレコードのための行がコントロールの一番下に存在しているかどうかを示し、<xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> プロパティは行を削除できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b1430-104">The <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property indicates whether the row for new records is present at the bottom of the control, while the <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> property indicates whether rows can be removed.</span></span> <span data-ttu-id="b1430-105">次のコード例は、これらのプロパティを使用し、さらに <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> プロパティも設定して、コントロール全体を読み取り専用にします。</span><span class="sxs-lookup"><span data-stu-id="b1430-105">The following code example uses these properties and also sets the <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> property to make the control entirely read-only.</span></span>  
  
 <span data-ttu-id="b1430-106">Visual Studio では、このタスクに対するサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b1430-106">There is support for this task in Visual Studio.</span></span> <span data-ttu-id="b1430-107">参照してください[方法。行の追加を回避し、削除を Windows フォーム DataGridView コントロールのデザイナーを使用して](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="b1430-107">Also see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1430-108">例</span><span class="sxs-lookup"><span data-stu-id="b1430-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b1430-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b1430-109">Compiling the Code</span></span>  
 <span data-ttu-id="b1430-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b1430-110">This example requires:</span></span>  
  
-   <span data-ttu-id="b1430-111">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="b1430-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="b1430-112">
  <xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="b1430-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1430-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1430-113">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b1430-114">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="b1430-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)

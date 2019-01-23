---
title: '方法: Windows フォームの DataGridView コントロール内の新しい行の既定値を指定します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
ms.openlocfilehash: dab9ba7ca16cf0c886601e3c8fea579e70b2f30d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596775"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="508a5-102">方法: Windows フォームの DataGridView コントロール内の新しい行の既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="508a5-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="508a5-103">行うことができますデータ エントリより便利なアプリケーションがいっぱいになる既定の新しく追加された行の値。</span><span class="sxs-lookup"><span data-stu-id="508a5-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="508a5-104"><xref:System.Windows.Forms.DataGridView>クラスを入力できる既定の値を<xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>イベント。</span><span class="sxs-lookup"><span data-stu-id="508a5-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="508a5-105">ユーザーが新しいレコードの行を入力すると、このイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="508a5-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="508a5-106">コードでは、このイベントを処理する場合は、任意のセルに独自の値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="508a5-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="508a5-107">次のコード例を使用して新しい行の既定値を指定する方法を示します、<xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>イベント。</span><span class="sxs-lookup"><span data-stu-id="508a5-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="508a5-108">例</span><span class="sxs-lookup"><span data-stu-id="508a5-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="508a5-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="508a5-109">Compiling the Code</span></span>  
 <span data-ttu-id="508a5-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="508a5-110">This example requires:</span></span>  
  
-   <span data-ttu-id="508a5-111">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="508a5-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="508a5-112">A`NewCustomerId`を一意に生成する関数`CustomerID`値。</span><span class="sxs-lookup"><span data-stu-id="508a5-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
-   <span data-ttu-id="508a5-113"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="508a5-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="508a5-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="508a5-114">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [<span data-ttu-id="508a5-115">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="508a5-115">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="508a5-116">Windows フォーム DataGridView コントロールにおける新規レコード行の使用</span><span class="sxs-lookup"><span data-stu-id="508a5-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)

---
title: DataGrid コントロール (Windows フォーム)
ms.date: 03/30/2017
helpviewer_keywords:
- datasets [Windows Forms], user interface
- DataGrid control [Windows Forms]
- datasets [Windows Forms], displaying in DataGrid control
- displaying data [Windows Forms], on forms
- data [Windows Forms], displaying on Windows Forms
ms.assetid: 1d9d5683-43d2-42dd-b6c3-e43f4cf0de99
ms.openlocfilehash: 5f8fcd21802c52d61d354c5ba85d665bd17237db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078916"
---
# <a name="datagrid-control-windows-forms"></a><span data-ttu-id="47a59-102">DataGrid コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="47a59-102">DataGrid Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="47a59-103"><xref:System.Windows.Forms.DataGridView> コントロールは、`DataGrid` コントロールに代わると共に追加の機能を提供します。ただし、`DataGrid` コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="47a59-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the `DataGrid` control; however, the `DataGrid` control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="47a59-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47a59-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="47a59-105">Windows フォームの `DataGrid` コントロールは、[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] データセットへのユーザー インターフェイスを提供し、データを表形式で表示して、データ ソースを更新できるようにします。</span><span class="sxs-lookup"><span data-stu-id="47a59-105">The Windows Forms `DataGrid` control provides a user interface to [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] datasets, displaying tabular data and enabling updates to the data source.</span></span>  
  
 <span data-ttu-id="47a59-106">`DataGrid` コントロールを有効なデータ ソースに対して設定すると、データの形式に基づいて列と行が作成されたコントロールが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="47a59-106">When the `DataGrid` control is set to a valid data source, the control is automatically populated, creating columns and rows based on the shape of the data.</span></span> <span data-ttu-id="47a59-107">`DataGrid` コントロールを使用すると、1 つのテーブルまたは、複数のテーブル間の階層的なリレーションシップを表示できます。</span><span class="sxs-lookup"><span data-stu-id="47a59-107">The `DataGrid` control can be used to display either a single table or the hierarchical relationships between a set of tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="47a59-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="47a59-108">In This Section</span></span>  
 [<span data-ttu-id="47a59-109">DataGrid コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="47a59-109">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)  
 <span data-ttu-id="47a59-110">`DataGrid` コントロールの基本機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="47a59-110">Describes the basic features of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="47a59-111">方法: デザイナーを使用して Windows フォーム DataGrid コントロールにテーブルと列を追加します。</span><span class="sxs-lookup"><span data-stu-id="47a59-111">How to: Add Tables and Columns to the Windows Forms DataGrid Control Using the Designer</span></span>](add-tables-and-columns-to-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="47a59-112">デザイナーを使用して `DataGrid` コントロールにテーブルと列を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47a59-112">Describes how to add tables and columns to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="47a59-113">方法: Windows フォームの DataGrid コントロールにテーブルと列を追加します。</span><span class="sxs-lookup"><span data-stu-id="47a59-113">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="47a59-114">プログラムによって `DataGrid` コントロールにテーブルと列を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47a59-114">Describes how to add tables and columns to the `DataGrid` control programmatically.</span></span>  
  
 [<span data-ttu-id="47a59-115">方法: デザイナーを使用してデータ ソースへの Windows フォームの DataGrid コントロールのバインドします。</span><span class="sxs-lookup"><span data-stu-id="47a59-115">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)  
 <span data-ttu-id="47a59-116">デザイナーを使用して [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] データセットを `DataGrid` コントロールにバインドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47a59-116">Describes how to bind an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] dataset to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="47a59-117">方法: Windows フォームの DataGrid コントロールをデータ ソースにバインドします。</span><span class="sxs-lookup"><span data-stu-id="47a59-117">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 <span data-ttu-id="47a59-118">[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] データセットを `DataGrid` コントロールにバインドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47a59-118">Describes how to bind an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] dataset to the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="47a59-119">方法: Windows フォーム DataGrid コントロールでの実行時に表示されるデータの変更</span><span class="sxs-lookup"><span data-stu-id="47a59-119">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)  
 <span data-ttu-id="47a59-120">`DataGrid` コントロール内でプログラムによってデータを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47a59-120">Describes how to change data programmatically in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="47a59-121">方法: デザイナーを使用して Windows フォーム DataGrid コントロールにマスター/詳細リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="47a59-121">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>](create-master-details-lists-with-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="47a59-122">デザイナーを使用して、親子のリレーションシップで結合されている 2 つのテーブルを、2 つの `DataGrid` コントロールに個別に表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47a59-122">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls using the designer.</span></span>  
  
 <span data-ttu-id="47a59-123">方法: Windows フォーム DataGrid コントロールでマスター/詳細リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="47a59-123">How to: Create Master-Details Lists with the Windows Forms DataGrid Control</span></span>  
 <span data-ttu-id="47a59-124">親子のリレーションシップで結合されている 2 つのテーブルを、2 つの `DataGrid` コントロールに個別に表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47a59-124">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls.</span></span>  
  
 [<span data-ttu-id="47a59-125">方法: 削除、または Windows フォームの DataGrid コントロール内の列を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="47a59-125">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="47a59-126">`DataGrid` コントロール内で列を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47a59-126">Describes how to remove columns in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="47a59-127">方法: デザイナーを使用して Windows フォーム DataGrid コントロールを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="47a59-127">How to: Format the Windows Forms DataGrid Control Using the Designer</span></span>](how-to-format-the-windows-forms-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="47a59-128">デザイナーを使用して、`DataGrid` コントロールの外観に関連するプロパティを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47a59-128">Describes how to change the appearance-related properties of the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="47a59-129">方法: Windows フォームの DataGrid コントロールの書式設定します。</span><span class="sxs-lookup"><span data-stu-id="47a59-129">How to: Format the Windows Forms DataGrid Control</span></span>](how-to-format-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="47a59-130">`DataGrid` コントロールの外観に関連するプロパティを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47a59-130">Describes how to change the appearance-related properties of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="47a59-131">Windows フォームの DataGrid コントロール内の移動に使用できるキーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="47a59-131">Keyboard Shortcuts for the Windows Forms DataGrid Control</span></span>](keyboard-shortcuts-for-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="47a59-132">`DataGrid` コントロール内の移動に使用できるキーボード ショートカットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="47a59-132">Lists shortcuts for navigating through the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="47a59-133">方法: Windows フォームの DataGrid コントロールのクリックに応答するには</span><span class="sxs-lookup"><span data-stu-id="47a59-133">How to: Respond to Clicks in the Windows Forms DataGrid Control</span></span>](how-to-respond-to-clicks-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="47a59-134">ユーザーがクリックした `DataGrid` コントロール内のセルを確認する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="47a59-134">Describes how to determine which cell a user has clicked in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="47a59-135">方法: Windows フォーム DataGrid コントロールで入力を検証します。</span><span class="sxs-lookup"><span data-stu-id="47a59-135">How to: Validate Input with the Windows Forms DataGrid Control</span></span>](how-to-validate-input-with-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="47a59-136">`DataGrid` コントロールにバインドされたデータセット内の入力データを検証する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="47a59-136">Describes how to validate input in the dataset bound to the `DataGrid` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="47a59-137">参照</span><span class="sxs-lookup"><span data-stu-id="47a59-137">Reference</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <span data-ttu-id="47a59-138">概要、<xref:System.Windows.Forms.DataGrid>クラス。</span><span class="sxs-lookup"><span data-stu-id="47a59-138">Provides an overview of the <xref:System.Windows.Forms.DataGrid> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGrid.DataSource%2A>  
 <span data-ttu-id="47a59-139">このプロパティを使用してバインドする方法の詳細を提供します、<xref:System.Windows.Forms.DataGrid>コントロールをデータにします。</span><span class="sxs-lookup"><span data-stu-id="47a59-139">Provides details about using this property to bind the <xref:System.Windows.Forms.DataGrid> control to data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="47a59-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="47a59-140">Related Sections</span></span>  
 [<span data-ttu-id="47a59-141">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="47a59-141">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="47a59-142">Windows フォームのデータ結合に関するトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="47a59-142">Provides links to topics on data binding in Windows Forms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a59-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="47a59-143">See also</span></span>

- [<span data-ttu-id="47a59-144">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="47a59-144">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="47a59-145">Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて</span><span class="sxs-lookup"><span data-stu-id="47a59-145">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)

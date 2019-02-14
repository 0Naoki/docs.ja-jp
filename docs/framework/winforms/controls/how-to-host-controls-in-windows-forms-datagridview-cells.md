---
title: '方法: Windows フォーム DataGridView Cells でコントロールをホスト'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: 86a1577174c12e55b23dd8bce2cf00ac0e780abb
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261259"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a><span data-ttu-id="13569-102">方法: Windows フォーム DataGridView Cells でコントロールをホスト</span><span class="sxs-lookup"><span data-stu-id="13569-102">How to: Host Controls in Windows Forms DataGridView Cells</span></span>
<span data-ttu-id="13569-103">
  <xref:System.Windows.Forms.DataGridView> コントロールには数種類の列があり、ユーザーはさまざまな方法で値を入力し、編集できます。</span><span class="sxs-lookup"><span data-stu-id="13569-103">The <xref:System.Windows.Forms.DataGridView> control provides several column types, enabling your users to enter and edit values in a variety of ways.</span></span> <span data-ttu-id="13569-104">ただし、これらの種類の列がデータ入力の要件を満たさない場合は、独自の種類の列を作成して、任意のコントロールをホストするセルを用意できます。</span><span class="sxs-lookup"><span data-stu-id="13569-104">If these column types do not meet your data-entry needs, however, you can create your own column types with cells that host controls of your choosing.</span></span> <span data-ttu-id="13569-105">これを作成するには、<xref:System.Windows.Forms.DataGridViewColumn> および <xref:System.Windows.Forms.DataGridViewCell> から派生する各クラスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13569-105">To do this, you must define classes that derive from <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewCell>.</span></span> <span data-ttu-id="13569-106">また、<xref:System.Windows.Forms.Control> から派生し、<xref:System.Windows.Forms.IDataGridViewEditingControl> インターフェイスを実装するクラスを定義する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="13569-106">You must also define a class that derives from <xref:System.Windows.Forms.Control> and implements the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
 <span data-ttu-id="13569-107">予定表の列を作成する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="13569-107">The following code example shows how to create a calendar column.</span></span> <span data-ttu-id="13569-108">この列のセルは、通常のテキスト ボックスのセルに日付を表示しますが、ユーザーがセルを編集するときには <xref:System.Windows.Forms.DateTimePicker> コントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="13569-108">The cells of this column display dates in ordinary text box cells, but when the user edits a cell, a <xref:System.Windows.Forms.DateTimePicker> control appears.</span></span> <span data-ttu-id="13569-109">テキスト ボックスの表示機能を再度実装しなくてもすむように、`CalendarCell` クラスは、<xref:System.Windows.Forms.DataGridViewCell> クラスを直接継承するのではなく <xref:System.Windows.Forms.DataGridViewTextBoxCell> クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="13569-109">In order to avoid having to implement text box display functionality again, the `CalendarCell` class derives from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> class rather than inheriting the <xref:System.Windows.Forms.DataGridViewCell> class directly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13569-110"><xref:System.Windows.Forms.DataGridViewCell> や <xref:System.Windows.Forms.DataGridViewColumn> から派生したクラスに新しいプロパティを追加するときは、`Clone` メソッドをオーバーライドし、複製操作時に新しいプロパティをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13569-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="13569-111">また、基底クラスの `Clone` メソッドを呼び出して、基底クラスのプロパティを新しいセルまたは列にコピーする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="13569-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13569-112">例</span><span class="sxs-lookup"><span data-stu-id="13569-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="13569-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="13569-113">Compiling the Code</span></span>  
 <span data-ttu-id="13569-114">この例には、次の項目が必要です。</span><span class="sxs-lookup"><span data-stu-id="13569-114">The following example requires:</span></span>  
  
-   <span data-ttu-id="13569-115">System アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="13569-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="13569-116">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="13569-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="13569-117">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="13569-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13569-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="13569-118">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>
- <xref:System.Windows.Forms.IDataGridViewEditingControl>
- <xref:System.Windows.Forms.DateTimePicker>
- [<span data-ttu-id="13569-119">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="13569-119">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="13569-120">DataGridView コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="13569-120">DataGridView Control Architecture</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="13569-121">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="13569-121">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)

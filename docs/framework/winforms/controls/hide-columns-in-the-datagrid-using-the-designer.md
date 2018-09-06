---
title: '方法 : デザイナーを使用して Windows フォーム DataGridView コントロールの列を非表示にする'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: 0187d85a639fc446f207a7b532fecc5ee707ae55
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43785359"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="510ac-102">方法 : デザイナーを使用して Windows フォーム DataGridView コントロールの列を非表示にする</span><span class="sxs-lookup"><span data-stu-id="510ac-102">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="510ac-103">Windows フォームの <xref:System.Windows.Forms.DataGridView> コントロールで使用できる列の一部のみを表示したいときがあります。</span><span class="sxs-lookup"><span data-stu-id="510ac-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="510ac-104">たとえば、従業員を表示するたい給与の列には他のユーザーが非表示の管理資格情報を持つユーザーをします。</span><span class="sxs-lookup"><span data-stu-id="510ac-104">For example, you may want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="510ac-105">または、その一部のみを表示する多くの列を含むデータ ソースにコントロールをバインドすることがあります。</span><span class="sxs-lookup"><span data-stu-id="510ac-105">Alternately, you may want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="510ac-106">この場合、非表示にするのではなく、表示する必要のない列は通常削除されます。</span><span class="sxs-lookup"><span data-stu-id="510ac-106">In this case, you will typically remove the columns you are not interested in displaying rather than hiding them.</span></span> <span data-ttu-id="510ac-107">詳細については、次を参照してください。[方法: 追加すると、Windows フォーム DataGridView コントロールを使用して、デザイナーで列を削除](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="510ac-107">For more information, see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
 <span data-ttu-id="510ac-108">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="510ac-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="510ac-109">このようなプロジェクトの設定の詳細については、次を参照してください。[方法: Windows アプリケーション プロジェクトを作成](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)と[方法: Windows フォームにコントロールを追加](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="510ac-109">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="510ac-110">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="510ac-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="510ac-111">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="510ac-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="510ac-112">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="510ac-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-hide-a-column-using-the-designer"></a><span data-ttu-id="510ac-113">デザイナーを使用して列を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="510ac-113">To hide a column using the designer</span></span>  
  
1.  <span data-ttu-id="510ac-114">スマート タグ グリフをクリックします (![スマート タグ グリフ](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) の右上隅で、 <xref:System.Windows.Forms.DataGridView> 、制御し、**列の編集**します。</span><span class="sxs-lookup"><span data-stu-id="510ac-114">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="510ac-115">列を選択、**選択した列**一覧。</span><span class="sxs-lookup"><span data-stu-id="510ac-115">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="510ac-116">**列プロパティ**グリッドで、設定、<xref:System.Windows.Forms.DataGridViewColumn.Visible%2A>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="510ac-116">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property to `false`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="510ac-117">オフにして追加する際に、列を隠すことも、 **Visible**  チェック ボックス、**列の追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="510ac-117">You can also hide a column when adding it by clearing the **Visible** check box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="510ac-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="510ac-118">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="510ac-119">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="510ac-119">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="510ac-120">方法: Windows アプリケーション プロジェクトを作成</span><span class="sxs-lookup"><span data-stu-id="510ac-120">How to: Create a Windows Application Project</span></span>](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="510ac-121">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="510ac-121">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)

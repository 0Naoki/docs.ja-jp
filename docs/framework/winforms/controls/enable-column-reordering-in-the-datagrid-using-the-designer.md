---
title: '方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列の並べ替えを有効にする'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 966ffe131d10b97fe9632bb1ff23273b1dabd061
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194969"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="d956e-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列の並べ替えを有効にする</span><span class="sxs-lookup"><span data-stu-id="d956e-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="d956e-103">Windows フォームに表示されるデータを表示するときに<xref:System.Windows.Forms.DataGridView>コントロール、ユーザーことがありますする特定の列の値を比較します。</span><span class="sxs-lookup"><span data-stu-id="d956e-103">When viewing data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, users sometimes want to compare the values in specific columns.</span></span> <span data-ttu-id="d956e-104">これは、できますしない列は、コントロールでは、広く区切られている場合に便利な特にで関心のあるすべての列を表示するには、ユーザーが前後へ水平方向にスクロールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d956e-104">This can be inconvenient if the columns are widely separated in the control, especially if users must scroll back and forth horizontally in order to see all the columns they are interested in.</span></span> <span data-ttu-id="d956e-105">列の順序を変更できるので、列の値を容易に比較を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d956e-105">You can make the task of comparing column values easier by enabling your users to reorder the columns.</span></span> <span data-ttu-id="d956e-106">列の並べ替えを有効にすると、ユーザーは、マウスで列ヘッダーをドラッグして列を新しい位置に移動できます。</span><span class="sxs-lookup"><span data-stu-id="d956e-106">When you enable column reordering, users can move a column to a new position by dragging the column header with the mouse.</span></span>  
  
 <span data-ttu-id="d956e-107">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d956e-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d956e-108">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="d956e-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d956e-109">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d956e-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d956e-110">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d956e-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d956e-111">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d956e-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-enable-column-reordering"></a><span data-ttu-id="d956e-112">列の並べ替えを有効にするには</span><span class="sxs-lookup"><span data-stu-id="d956e-112">To enable column reordering</span></span>  
  
-   <span data-ttu-id="d956e-113">スマート タグ グリフをクリックします (![スマート タグ グリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) の右上隅で、 <xref:System.Windows.Forms.DataGridView> 、制御し、**列の並べ替えを有効にする**.</span><span class="sxs-lookup"><span data-stu-id="d956e-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Enable Column Reordering**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d956e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d956e-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d956e-115">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を固定する</span><span class="sxs-lookup"><span data-stu-id="d956e-115">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="d956e-116">方法: Windows フォーム アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d956e-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="d956e-117">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="d956e-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)

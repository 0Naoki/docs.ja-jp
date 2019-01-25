---
title: '方法: TableLayoutPanel コントロールの列と行を編集します。'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: b1ae7afe2a99870e4befc04992148080aff6bfad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720328"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="cd639-102">方法: TableLayoutPanel コントロールの列と行を編集します。</span><span class="sxs-lookup"><span data-stu-id="cd639-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>
<span data-ttu-id="cd639-103">コレクション エディターを使用することができます、<xref:System.Windows.Forms.TableLayoutPanel>というコントロール、**列と行のスタイル**行と、コントロールの列を編集するためのダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="cd639-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd639-104">コントロールに複数の行または列にまたがる場合は、設定、`RowSpan`と`ColumnSpan`コントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="cd639-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="cd639-105">詳細については、「[チュートリアル:TableLayoutPanel を使用して Windows フォーム コントロールの配置](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)します。</span><span class="sxs-lookup"><span data-stu-id="cd639-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="cd639-106">セル内のコントロールを配置する場合、またはコントロールのセル内をしたい場合を使用して、コントロールの<xref:System.Windows.Forms.Control.Anchor%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="cd639-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="cd639-107">詳細については、「[チュートリアル:TableLayoutPanel を使用して Windows フォーム コントロールの配置](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)します。</span><span class="sxs-lookup"><span data-stu-id="cd639-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="cd639-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd639-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="cd639-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd639-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="cd639-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd639-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-edit-rows-and-columns"></a><span data-ttu-id="cd639-111">行と列を編集するには</span><span class="sxs-lookup"><span data-stu-id="cd639-111">To edit rows and columns</span></span>  
  
1.  <span data-ttu-id="cd639-112"><xref:System.Windows.Forms.TableLayoutPanel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="cd639-112">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="cd639-113">をクリックして、<xref:System.Windows.Forms.TableLayoutPanel>コントロールのスマート タグ グリフ (![スマート タグ グリフ](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) を選択して**編集行と列**を開く、 **列と行のスタイル** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="cd639-113">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="cd639-114">クリックすることも右に、<xref:System.Windows.Forms.TableLayoutPanel>を制御し、選択**編集行と列**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="cd639-114">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="cd639-115">列を追加または削除、選択**列**から、**メンバーの種類**ドロップダウン リスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="cd639-115">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>  
  
4.  <span data-ttu-id="cd639-116">を追加または削除行に次のように選択します。**行**から、**メンバーの種類**ドロップダウン リスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="cd639-116">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>  
  
5.  <span data-ttu-id="cd639-117">をクリックして、**追加**の末尾に行または列を追加するボタン、**メンバー**一覧。</span><span class="sxs-lookup"><span data-stu-id="cd639-117">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>  
  
6.  <span data-ttu-id="cd639-118">をクリックして、**挿入**の一覧で行または現在選択されている項目の前に列を追加するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd639-118">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>  
  
7.  <span data-ttu-id="cd639-119">行または列を追加する場合は、選択、**サイズ型**新しい行または列。</span><span class="sxs-lookup"><span data-stu-id="cd639-119">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="cd639-120">詳細については、「 <xref:System.Windows.Forms.SizeType> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd639-120">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>  
  
8.  <span data-ttu-id="cd639-121">行または列を削除する をクリックして、**削除**で現在選択されている項目を削除するボタン、**メンバー**一覧。</span><span class="sxs-lookup"><span data-stu-id="cd639-121">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd639-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd639-122">See also</span></span>
- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="cd639-123">TableLayoutPanel コントロール</span><span class="sxs-lookup"><span data-stu-id="cd639-123">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)

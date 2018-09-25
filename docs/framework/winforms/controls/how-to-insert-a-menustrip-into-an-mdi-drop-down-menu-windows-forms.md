---
title: '方法: MDI ドロップダウン メニューに MenuStrip を挿入する (Windows フォーム)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
ms.openlocfilehash: 64e7e7875a635bcd4fbafb62d3ee7b7018214ee4
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47115023"
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="7e7b9-102">方法: MDI ドロップダウン メニューに MenuStrip を挿入する (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="7e7b9-102">How to: Insert a MenuStrip into an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="7e7b9-103">アプリケーションの中には、マルチ ドキュメント インターフェイス (MDI) 子ウィンドウの種類が MDI 親ウィンドウと異なるものがあります。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="7e7b9-104">たとえば、MDI 親がスプレッドシートで、MDI 子がグラフの場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="7e7b9-105">そのような場合は、異なる種類の MDI 子ウィンドウがアクティブになったときに、MDI 子メニューの内容で MDI 親メニューの内容を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="7e7b9-106">次の手順を使用して、 <xref:System.Windows.Forms.Form.IsMdiContainer%2A>、 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>、 <xref:System.Windows.Forms.MergeAction>、および<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>MDI 子メニューからメニュー項目のグループを MDI 親メニューのドロップダウン部分に挿入するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to insert a group of menu items from the MDI child menu into the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="7e7b9-107">MDI 子ウィンドウを閉じると、挿入されたメニュー項目が MDI 親から削除します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-107">Closing the MDI child window removes the inserted menu items from the MDI parent.</span></span>  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a><span data-ttu-id="7e7b9-108">MDI ドロップダウン メニューに MenuStrip を挿入するには</span><span class="sxs-lookup"><span data-stu-id="7e7b9-108">To insert a MenuStrip into an MDI drop-down menu</span></span>  
  
1.  <span data-ttu-id="7e7b9-109">フォームを作成し、その <xref:System.Windows.Forms.Form.IsMdiContainer%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="7e7b9-110"><xref:System.Windows.Forms.MenuStrip> を `Form1` に追加し、<xref:System.Windows.Forms.MenuStrip> の <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3.  <span data-ttu-id="7e7b9-111">トップレベル メニュー項目を `Form1` の <xref:System.Windows.Forms.MenuStrip> に追加し、その <xref:System.Windows.Forms.Control.Text%2A> プロパティを「`&File`」に設定しますす。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4.  <span data-ttu-id="7e7b9-112">3 つのサブメニュー項目を追加、`&File`メニュー項目とその<xref:System.Windows.Forms.ToolStripItem.Text%2A>プロパティを`&Open`、`&Import from`と`E&xit`。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5.  <span data-ttu-id="7e7b9-113">2 つのサブメニュー項目を追加、`&Import from`サブメニュー項目とその<xref:System.Windows.Forms.ToolStripItem.Text%2A>プロパティを`&Word`と`&Excel`します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6.  <span data-ttu-id="7e7b9-114">プロジェクトにフォームを追加し、フォームに <xref:System.Windows.Forms.MenuStrip> を追加し、`Form2` の <xref:System.Windows.Forms.MenuStrip> の <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> のプロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7.  <span data-ttu-id="7e7b9-115">トップレベル メニュー項目を `Form2` の <xref:System.Windows.Forms.MenuStrip> に追加し、その <xref:System.Windows.Forms.ToolStripItem.Text%2A> プロパティを「`&File`」に設定しますす。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8.  <span data-ttu-id="7e7b9-116">サブメニュー項目を追加、`&File`のメニュー`Form2`次の順序で: <xref:System.Windows.Forms.ToolStripSeparator>、 `&Save`、 `Save and &Close`、もう 1 つと<xref:System.Windows.Forms.ToolStripSeparator>します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-116">Add submenu items to the `&File` menu of `Form2` in the following order: a <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`, and another <xref:System.Windows.Forms.ToolStripSeparator>.</span></span>  
  
9. <span data-ttu-id="7e7b9-117">設定、<xref:System.Windows.Forms.MergeAction>と<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>のプロパティ、`Form2`メニュー項目を次の表に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="7e7b9-118">Form2 のメニュー項目</span><span class="sxs-lookup"><span data-stu-id="7e7b9-118">Form2 menu item</span></span>|<span data-ttu-id="7e7b9-119">MergeAction 値</span><span class="sxs-lookup"><span data-stu-id="7e7b9-119">MergeAction value</span></span>|<span data-ttu-id="7e7b9-120">MergeIndex 値</span><span class="sxs-lookup"><span data-stu-id="7e7b9-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="7e7b9-121">ファイル</span><span class="sxs-lookup"><span data-stu-id="7e7b9-121">File</span></span>|<span data-ttu-id="7e7b9-122">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="7e7b9-122">MatchOnly</span></span>|<span data-ttu-id="7e7b9-123">-1</span><span class="sxs-lookup"><span data-stu-id="7e7b9-123">-1</span></span>|  
    |<span data-ttu-id="7e7b9-124">区切り記号</span><span class="sxs-lookup"><span data-stu-id="7e7b9-124">Separator</span></span>|<span data-ttu-id="7e7b9-125">挿入</span><span class="sxs-lookup"><span data-stu-id="7e7b9-125">Insert</span></span>|<span data-ttu-id="7e7b9-126">2</span><span class="sxs-lookup"><span data-stu-id="7e7b9-126">2</span></span>|  
    |<span data-ttu-id="7e7b9-127">保存</span><span class="sxs-lookup"><span data-stu-id="7e7b9-127">Save</span></span>|<span data-ttu-id="7e7b9-128">挿入</span><span class="sxs-lookup"><span data-stu-id="7e7b9-128">Insert</span></span>|<span data-ttu-id="7e7b9-129">3</span><span class="sxs-lookup"><span data-stu-id="7e7b9-129">3</span></span>|  
    |<span data-ttu-id="7e7b9-130">保存して閉じる</span><span class="sxs-lookup"><span data-stu-id="7e7b9-130">Save and Close</span></span>|<span data-ttu-id="7e7b9-131">挿入</span><span class="sxs-lookup"><span data-stu-id="7e7b9-131">Insert</span></span>|<span data-ttu-id="7e7b9-132">4</span><span class="sxs-lookup"><span data-stu-id="7e7b9-132">4</span></span>|  
    |<span data-ttu-id="7e7b9-133">区切り記号</span><span class="sxs-lookup"><span data-stu-id="7e7b9-133">Separator</span></span>|<span data-ttu-id="7e7b9-134">挿入</span><span class="sxs-lookup"><span data-stu-id="7e7b9-134">Insert</span></span>|<span data-ttu-id="7e7b9-135">5</span><span class="sxs-lookup"><span data-stu-id="7e7b9-135">5</span></span>|  
  
10. <span data-ttu-id="7e7b9-136"><xref:System.Windows.Forms.ToolStripMenuItem> の `&Open` の <xref:System.Windows.Forms.Control.Click> イベントにイベント ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-136">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="7e7b9-137">このイベント ハンドラー内に次のコード例のようなコードを挿入し、`Form2` の新規インスタンスを `Form1` の MDI 子フォームとして作成し、表示します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-137">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
12. <span data-ttu-id="7e7b9-138">`&Open`<xref:System.Windows.Forms.ToolStripMenuItem> に次のコード例のようなコードを配置し、イベント ハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-138">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7e7b9-139">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="7e7b9-139">Compiling the Code</span></span>  
 <span data-ttu-id="7e7b9-140">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-140">This example requires:</span></span>  
  
-   <span data-ttu-id="7e7b9-141">`Form1` と `Form2` という名前の 2 つの <xref:System.Windows.Forms.Form> コントロール。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-141">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
-   <span data-ttu-id="7e7b9-142">`Form1` 上の `menuStrip1` という名前の <xref:System.Windows.Forms.MenuStrip> コントロールと、`Form2` 上の `menuStrip2` という名前の <xref:System.Windows.Forms.MenuStrip> コントロール。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-142">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
-   <span data-ttu-id="7e7b9-143"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-143">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e7b9-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e7b9-144">See Also</span></span>  
 [<span data-ttu-id="7e7b9-145">方法: MDI 親フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="7e7b9-145">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="7e7b9-146">方法: MDI 子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="7e7b9-146">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="7e7b9-147">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="7e7b9-147">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)

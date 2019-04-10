---
title: '方法: MenuStrip (Windows フォーム) を MDI ウィンドウ リストを作成します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: ec0d8af81e320bea3d9d69305f91bd56666ba7cc
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299645"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a><span data-ttu-id="82f93-102">方法: MenuStrip (Windows フォーム) を MDI ウィンドウ リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="82f93-102">How to: Create an MDI Window List with MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="82f93-103">マルチ ドキュメント インターフェイス (MDI) を使用して、同じ時およびコピーにいくつかのドキュメントを開くし、他の 1 つのドキュメントのコンテンツを貼り付けることができますアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="82f93-103">Use the multiple-document interface (MDI) to create applications that can open several documents at the same time and copy and paste content from one document to the other.</span></span>  
  
 <span data-ttu-id="82f93-104">この手順では、親のウィンドウ メニューで、すべてのアクティブな子フォームのリストを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="82f93-104">This procedure shows you how to create a list of all the active child forms on the parent's Window menu.</span></span>  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a><span data-ttu-id="82f93-105">MenuStrip を MDI ウィンドウ リストの作成</span><span class="sxs-lookup"><span data-stu-id="82f93-105">To create an MDI Window list on a MenuStrip</span></span>  
  
1. <span data-ttu-id="82f93-106">フォームを作成し、その <xref:System.Windows.Forms.Form.IsMdiContainer%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="82f93-106">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="82f93-107">フォームに <xref:System.Windows.Forms.MenuStrip> を追加します。</span><span class="sxs-lookup"><span data-stu-id="82f93-107">Add a <xref:System.Windows.Forms.MenuStrip> to the form.</span></span>  
  
3. <span data-ttu-id="82f93-108">2 つのトップレベルのメニュー項目を追加、<xref:System.Windows.Forms.MenuStrip>設定とその<xref:System.Windows.Forms.Control.Text%2A>プロパティを`&File`と`&Window`します。</span><span class="sxs-lookup"><span data-stu-id="82f93-108">Add two top-level menu items to the <xref:System.Windows.Forms.MenuStrip> and set their <xref:System.Windows.Forms.Control.Text%2A> properties to `&File` and `&Window`.</span></span>  
  
4. <span data-ttu-id="82f93-109">サブメニュー項目を `&File` メニュー項目に追加し、その <xref:System.Windows.Forms.ToolStripItem.Text%2A> プロパティを「`&Open`」に設定します。</span><span class="sxs-lookup"><span data-stu-id="82f93-109">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&Open`.</span></span>  
  
5. <span data-ttu-id="82f93-110">設定、<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>のプロパティ、<xref:System.Windows.Forms.MenuStrip>を`&Window`<xref:System.Windows.Forms.ToolStripMenuItem>します。</span><span class="sxs-lookup"><span data-stu-id="82f93-110">Set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property of the <xref:System.Windows.Forms.MenuStrip> to the `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
6. <span data-ttu-id="82f93-111">プロジェクトにフォームを追加し、別などの必要なコントロールを追加<xref:System.Windows.Forms.MenuStrip>します。</span><span class="sxs-lookup"><span data-stu-id="82f93-111">Add a form to the project and add the control you want to it, such as another <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
7. <span data-ttu-id="82f93-112">イベント ハンドラーを作成、<xref:System.Windows.Forms.Control.Click>のイベント、`&New`<xref:System.Windows.Forms.ToolStripMenuItem>します。</span><span class="sxs-lookup"><span data-stu-id="82f93-112">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
8. <span data-ttu-id="82f93-113">イベント ハンドラー内で作成の新しいインスタンスを表示するには、次のようなコードを挿入`Form2`の MDI 子フォームとして`Form1`します。</span><span class="sxs-lookup"><span data-stu-id="82f93-113">Within the event handler, insert code similar to the following to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. <span data-ttu-id="82f93-114">配置では、次のようなコード、`&New`<xref:System.Windows.Forms.ToolStripMenuItem>イベント ハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="82f93-114">Place code like the following in the `&New`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="82f93-115">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="82f93-115">Compiling the Code</span></span>  
 <span data-ttu-id="82f93-116">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82f93-116">This example requires:</span></span>  
  
-   <span data-ttu-id="82f93-117">`Form1` と `Form2` という名前の 2 つの <xref:System.Windows.Forms.Form> コントロール。</span><span class="sxs-lookup"><span data-stu-id="82f93-117">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
-   <span data-ttu-id="82f93-118">`Form1` 上の `menuStrip1` という名前の <xref:System.Windows.Forms.MenuStrip> コントロールと、`Form2` 上の `menuStrip2` という名前の <xref:System.Windows.Forms.MenuStrip> コントロール。</span><span class="sxs-lookup"><span data-stu-id="82f93-118">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
-   <span data-ttu-id="82f93-119"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="82f93-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82f93-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="82f93-120">See also</span></span>

- [<span data-ttu-id="82f93-121">方法: MDI 親フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="82f93-121">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="82f93-122">方法: MDI 子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="82f93-122">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="82f93-123">MenuStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="82f93-123">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)

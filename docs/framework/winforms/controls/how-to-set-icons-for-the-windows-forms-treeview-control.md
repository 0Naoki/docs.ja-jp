---
title: '方法: Windows フォーム TreeView コントロールのアイコンを設定します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: 49b44c604a8532c6d2beb39b917f3e5ade339c49
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564030"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="548f1-102">方法: Windows フォーム TreeView コントロールのアイコンを設定します。</span><span class="sxs-lookup"><span data-stu-id="548f1-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="548f1-103">Windows フォーム<xref:System.Windows.Forms.TreeView>コントロールは、各ノードの横にアイコンを表示できます。</span><span class="sxs-lookup"><span data-stu-id="548f1-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="548f1-104">アイコンは、ノードのテキストのすぐ左に配置されます。</span><span class="sxs-lookup"><span data-stu-id="548f1-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="548f1-105">これらのアイコンを表示するには、ツリー ビューを関連付ける必要があります、<xref:System.Windows.Forms.ImageList>コントロール。</span><span class="sxs-lookup"><span data-stu-id="548f1-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="548f1-106">イメージ リストの詳細については、次を参照してください。 [ImageList コンポーネント](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)と[方法。追加または削除のイメージで、Windows フォームの ImageList コンポーネント](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="548f1-106">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="548f1-107">Microsoft .NET Framework version 1.1 でのバグが表示されないイメージを防止<xref:System.Windows.Forms.TreeView>ノード アプリケーションが呼び出す<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="548f1-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="548f1-108">このバグを回避するには、呼び出す<xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>で、`Main`メソッドをすぐに呼び出して<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>します。</span><span class="sxs-lookup"><span data-stu-id="548f1-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="548f1-109">このバグを修正[!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="548f1-109">This bug is fixed in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="548f1-110">ツリー ビューでイメージを表示するには</span><span class="sxs-lookup"><span data-stu-id="548f1-110">To display images in a tree view</span></span>  
  
1.  <span data-ttu-id="548f1-111">設定、<xref:System.Windows.Forms.TreeView>コントロールの<xref:System.Windows.Forms.TreeView.ImageList%2A>プロパティを既存の<xref:System.Windows.Forms.ImageList>を使用するコントロール。</span><span class="sxs-lookup"><span data-stu-id="548f1-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="548f1-112">デザイナーの [プロパティ] ウィンドウまたはコードでは、これらのプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="548f1-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  <span data-ttu-id="548f1-113">ノードの設定<xref:System.Windows.Forms.TreeNode.ImageIndex%2A>と<xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="548f1-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="548f1-114"><xref:System.Windows.Forms.TreeNode.ImageIndex%2A>プロパティは、ノードの標準的な展開の状態に表示されるイメージを決定します。 および<xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>プロパティ ノードの選択された状態に表示されるイメージを決定します。</span><span class="sxs-lookup"><span data-stu-id="548f1-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="548f1-115">コードでは、または、TreeNode エディター内で、これらのプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="548f1-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="548f1-116">TreeNode エディターを開くには、省略記号ボタンをクリックします。 ( ![VisualStudioEllipsesButton スクリーン ショット](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 横に、 <xref:System.Windows.Forms.TreeView.Nodes%2A> [プロパティ] ウィンドウのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="548f1-116">To open the TreeNode Editor, click the ellipsis button ( ![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="548f1-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="548f1-117">See also</span></span>
- [<span data-ttu-id="548f1-118">TreeView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="548f1-118">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="548f1-119">方法: 追加して、Windows フォーム TreeView コントロールでノードを削除</span><span class="sxs-lookup"><span data-stu-id="548f1-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="548f1-120">方法: Windows フォーム TreeView コントロールのすべてのノードを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="548f1-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="548f1-121">方法: クリックしてされた TreeView ノードを決定します。</span><span class="sxs-lookup"><span data-stu-id="548f1-121">How to: Determine Which TreeView Node Was Clicked</span></span>](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="548f1-122">方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="548f1-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)

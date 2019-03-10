---
title: '方法: 追加して、デザイナーを使用して Windows フォーム TreeView コントロールでノードを削除'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: aca660c7b3269715e6551011261f9b84ba173db6
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710356"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="4753a-102">方法: 追加して、デザイナーを使用して Windows フォーム TreeView コントロールでノードを削除</span><span class="sxs-lookup"><span data-stu-id="4753a-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>
<span data-ttu-id="4753a-103">Windows フォームため<xref:System.Windows.Forms.TreeView>コントロールでは、親ノードに注意する必要がありますノードを追加するときに、階層的な方法でノードを表示します。</span><span class="sxs-lookup"><span data-stu-id="4753a-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>  
  
 <span data-ttu-id="4753a-104">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.TreeView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="4753a-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="4753a-105">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="4753a-105">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4753a-106">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4753a-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4753a-107">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4753a-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4753a-108">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4753a-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="4753a-109">追加またはデザイナーでのノードを削除するには</span><span class="sxs-lookup"><span data-stu-id="4753a-109">To add or remove nodes in the designer</span></span>  
  
1.  <span data-ttu-id="4753a-110">
  <xref:System.Windows.Forms.TreeView> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="4753a-110">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>  
  
2.  <span data-ttu-id="4753a-111">**プロパティ**ウィンドウで、をクリックして、**省略記号**(![VisualStudioEllipsesButton スクリーン ショット](../media/vbellipsesbutton.png "vbEllipsesButton")) ボタンを<xref:System.Windows.Forms.TreeView.Nodes%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4753a-111">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
     <span data-ttu-id="4753a-112">**TreeNode エディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4753a-112">The **TreeNode Editor** appears.</span></span>  
  
3.  <span data-ttu-id="4753a-113">ノードを追加するには、ルート ノードが存在する必要があります。最初にクリックして、ルートを追加する必要がありますいずれかが存在しない場合、**ルートの追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4753a-113">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="4753a-114">ルートまたは他の任意のノードを選択しをクリックすると子ノードを追加することができますし、**子の追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4753a-114">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>  
  
4.  <span data-ttu-id="4753a-115">ノードを削除するを削除し、をクリックし、ノードを選択します。、**削除**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4753a-115">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4753a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="4753a-116">See also</span></span>
- [<span data-ttu-id="4753a-117">TreeView コントロール</span><span class="sxs-lookup"><span data-stu-id="4753a-117">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="4753a-118">TreeView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="4753a-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="4753a-119">方法: Windows フォーム TreeView コントロールのアイコンを設定します。</span><span class="sxs-lookup"><span data-stu-id="4753a-119">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="4753a-120">方法: Windows フォーム TreeView コントロールのすべてのノードを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="4753a-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="4753a-121">方法: クリックしてされた TreeView ノードを決定します。</span><span class="sxs-lookup"><span data-stu-id="4753a-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="4753a-122">方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="4753a-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)

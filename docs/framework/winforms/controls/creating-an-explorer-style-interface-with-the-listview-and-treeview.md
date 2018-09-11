---
title: 'チュートリアル : デザイナーを使用した、ListView コントロールと TreeView コントロールを含むエクスプローラー スタイルのインターフェイスの作成'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: 73d3a0bef1ab075aee8e06f676ef17b853773552
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44267253"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="1127e-102">チュートリアル : デザイナーを使用した、ListView コントロールと TreeView コントロールを含むエクスプローラー スタイルのインターフェイスの作成</span><span class="sxs-lookup"><span data-stu-id="1127e-102">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>
<span data-ttu-id="1127e-103">Visual Studio の利点の 1 つは、時間の短い形式で本格的な Windows フォーム アプリケーションを作成する機能です。</span><span class="sxs-lookup"><span data-stu-id="1127e-103">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="1127e-104">一般的なシナリオがユーザー インターフェイス (UI) で作成して<xref:System.Windows.Forms.ListView>と<xref:System.Windows.Forms.TreeView>Windows オペレーティング システムの Windows エクスプ ローラーの機能のようなコントロール。</span><span class="sxs-lookup"><span data-stu-id="1127e-104">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="1127e-105">Windows エクスプ ローラーは、ユーザーのコンピューター上のファイルとフォルダーの階層構造を表示します。</span><span class="sxs-lookup"><span data-stu-id="1127e-105">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1127e-106">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1127e-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1127e-107">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1127e-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1127e-108">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1127e-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="1127e-109">ListView、TreeView コントロールを含むフォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="1127e-109">To create the form containing a ListView and TreeView control</span></span>  
  
1.  <span data-ttu-id="1127e-110">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1127e-110">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="1127e-111">**新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1127e-111">In the **New Project** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="1127e-112">カテゴリでいずれかを選択**Visual Basic**または**Visual c#** します。</span><span class="sxs-lookup"><span data-stu-id="1127e-112">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>  
  
    2.  <span data-ttu-id="1127e-113">テンプレートの一覧で選択**Windows フォーム アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="1127e-113">In the list of templates, choose **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="1127e-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1127e-114">Click **OK**.</span></span> <span data-ttu-id="1127e-115">新しい Windows フォーム プロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1127e-115">A new Windows Forms project is created.</span></span>  
  
4.  <span data-ttu-id="1127e-116">追加、<xref:System.Windows.Forms.SplitContainer>コントロールをフォームにし、設定、<xref:System.Windows.Forms.SplitContainer.Dock%2A>プロパティを<xref:System.Windows.Forms.DockStyle.Fill>します。</span><span class="sxs-lookup"><span data-stu-id="1127e-116">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5.  <span data-ttu-id="1127e-117">追加、<xref:System.Windows.Forms.ImageList>という名前の`imageList1`フォームと 2 つのイメージを追加する [プロパティ] ウィンドウを使用する: フォルダーのイメージとその順序で、ドキュメントのイメージ。</span><span class="sxs-lookup"><span data-stu-id="1127e-117">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>  
  
6.  <span data-ttu-id="1127e-118">追加、<xref:System.Windows.Forms.TreeView>という名前のコントロール`treeview1`をフォームに配置の左側にある、<xref:System.Windows.Forms.SplitContainer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="1127e-118">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="1127e-119">[プロパティ] ウィンドウで`treeView1`次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1127e-119">In the Properties window for `treeView1` do the following:</span></span>  
  
    1.  <span data-ttu-id="1127e-120"><xref:System.Windows.Forms.Control.Dock%2A> プロパティを <xref:System.Windows.Forms.DockStyle.Fill> に設定します。</span><span class="sxs-lookup"><span data-stu-id="1127e-120">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    2.  <span data-ttu-id="1127e-121"><xref:System.Windows.Forms.TreeView.ImageList%2A> プロパティを `imagelist1.` に設定します。</span><span class="sxs-lookup"><span data-stu-id="1127e-121">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>  
  
7.  <span data-ttu-id="1127e-122">追加、<xref:System.Windows.Forms.ListView>という名前のコントロール`listView1`をフォームの右側の上に移動し、<xref:System.Windows.Forms.SplitContainer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="1127e-122">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="1127e-123">[プロパティ] ウィンドウで`listview1`次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1127e-123">In the Properties window for `listview1` do the following:</span></span>  
  
    1.  <span data-ttu-id="1127e-124"><xref:System.Windows.Forms.Control.Dock%2A> プロパティを <xref:System.Windows.Forms.DockStyle.Fill> に設定します。</span><span class="sxs-lookup"><span data-stu-id="1127e-124">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    2.  <span data-ttu-id="1127e-125"><xref:System.Windows.Forms.ListView.View%2A> プロパティを <xref:System.Windows.Forms.View.Details> に設定します。</span><span class="sxs-lookup"><span data-stu-id="1127e-125">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
    3.  <span data-ttu-id="1127e-126">省略記号をクリックして、ColumnHeader コレクション エディターを開きます (![VisualStudioEllipsesButton スクリーン ショット](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) で、<xref:System.Windows.Forms.ListView.Columns%2A>プロパティ**します。**</span><span class="sxs-lookup"><span data-stu-id="1127e-126">Open the ColumnHeader Collection Editor by clicking the ellipses (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="1127e-127">3 つの列を追加し、設定、<xref:System.Windows.Forms.ColumnHeader.Text%2A>プロパティを`Name`、 `Type`、および`Last Modified`、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="1127e-127">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="1127e-128">**[OK]** をクリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1127e-128">Click **OK** to close the dialog box.</span></span>  
  
    4.  <span data-ttu-id="1127e-129"><xref:System.Windows.Forms.ListView.SmallImageList%2A> プロパティを `imageList1.` に設定します。</span><span class="sxs-lookup"><span data-stu-id="1127e-129">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>  
  
8.  <span data-ttu-id="1127e-130">データを読み込むコードを実装、<xref:System.Windows.Forms.TreeView>ノードおよびサブノードにします。</span><span class="sxs-lookup"><span data-stu-id="1127e-130">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="1127e-131">`Form1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1127e-131">Add this code to the `Form1` class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. <span data-ttu-id="1127e-132">前のコードでは、System.IO 名前空間を使用するため、適切な using の追加または、フォームの上部にあるステートメントをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1127e-132">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. <span data-ttu-id="1127e-133">フォームのコンス トラクターの前の手順からのセットアップ メソッドを呼び出すまたは<xref:System.Windows.Forms.Form.Load>イベント処理メソッド。</span><span class="sxs-lookup"><span data-stu-id="1127e-133">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="1127e-134">このコードをフォームのコンス トラクターに追加します。</span><span class="sxs-lookup"><span data-stu-id="1127e-134">Add this code to the form constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. <span data-ttu-id="1127e-135">処理、<xref:System.Windows.Forms.TreeView.NodeMouseClick>イベントを`treeview1` **、** を設定するコードを実装し、`listview1`ノードのコンテンツ ノードがクリックされたときに使用します。</span><span class="sxs-lookup"><span data-stu-id="1127e-135">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="1127e-136">`Form1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1127e-136">Add this code to the `Form1` class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     <span data-ttu-id="1127e-137">C# を使用している場合があることを確認、<xref:System.Windows.Forms.TreeView.NodeMouseClick>イベントのイベント処理メソッドに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="1127e-137">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="1127e-138">このコードをフォームのコンス トラクターに追加します。</span><span class="sxs-lookup"><span data-stu-id="1127e-138">Add this code to the form constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="1127e-139">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="1127e-139">Testing the Application</span></span>  
 <span data-ttu-id="1127e-140">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1127e-140">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="1127e-141">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="1127e-141">To test the form</span></span>  
  
-   <span data-ttu-id="1127e-142">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1127e-142">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="1127e-143">含む分割フォームが表示されます、<xref:System.Windows.Forms.TreeView>左側にある、プロジェクト ディレクトリを表示するコントロールと<xref:System.Windows.Forms.ListView>3 つの列の右側にあるコントロール。</span><span class="sxs-lookup"><span data-stu-id="1127e-143">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="1127e-144">走査することができます、<xref:System.Windows.Forms.TreeView>ディレクトリのノードを選択して、<xref:System.Windows.Forms.ListView>は選択したディレクトリの内容が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1127e-144">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1127e-145">次の手順</span><span class="sxs-lookup"><span data-stu-id="1127e-145">Next Steps</span></span>  
 <span data-ttu-id="1127e-146">このアプリケーションは、使用できる方法の例を示します<xref:System.Windows.Forms.TreeView>と<xref:System.Windows.Forms.ListView>化を制御します。</span><span class="sxs-lookup"><span data-stu-id="1127e-146">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="1127e-147">これらのコントロールの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1127e-147">For more information on these controls, see the following topics:</span></span>  
  
-   [<span data-ttu-id="1127e-148">方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加する</span><span class="sxs-lookup"><span data-stu-id="1127e-148">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
-   [<span data-ttu-id="1127e-149">方法: ListView コントロールに検索機能を追加する</span><span class="sxs-lookup"><span data-stu-id="1127e-149">How to: Add Search Capabilities to a ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
  
-   [<span data-ttu-id="1127e-150">方法: ショートカット メニューを TreeView ノードに追加する</span><span class="sxs-lookup"><span data-stu-id="1127e-150">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](../../../../docs/framework/winforms/controls/how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## <a name="see-also"></a><span data-ttu-id="1127e-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="1127e-151">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.TreeView>  
 [<span data-ttu-id="1127e-152">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="1127e-152">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="1127e-153">方法: Windows フォーム TreeView コントロールでノードを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="1127e-153">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [<span data-ttu-id="1127e-154">方法: Windows フォーム ListView コントロールで項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="1127e-154">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="1127e-155">方法: Windows フォーム ListView コントロールに列を追加する</span><span class="sxs-lookup"><span data-stu-id="1127e-155">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)

---
title: 'チュートリアル: WPF での ActiveX コントロールのホスト'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: 671138389b471ad9b9c62bd768895832d0324591
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486556"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="faeeb-102">チュートリアル: WPF での ActiveX コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="faeeb-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="faeeb-103">ブラウザーでの強化された操作を有効にするを使用できます[!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)]でコントロールを[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-ベースのアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="faeeb-103">To enable improved interaction with browsers, you can use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="faeeb-104">このチュートリアルでは、ホストする方法、[!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)]上のコントロールとして、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ページ。</span><span class="sxs-lookup"><span data-stu-id="faeeb-104">This walkthrough demonstrates how you can host the [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>  
  
 <span data-ttu-id="faeeb-105">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="faeeb-105">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="faeeb-106">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="faeeb-106">Creating the project.</span></span>  
  
-   <span data-ttu-id="faeeb-107">ActiveX コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-107">Creating the ActiveX control.</span></span>  
  
-   <span data-ttu-id="faeeb-108">WPF ページ上の ActiveX コントロールをホストします。</span><span class="sxs-lookup"><span data-stu-id="faeeb-108">Hosting the ActiveX control on a WPF Page.</span></span>  
  
 <span data-ttu-id="faeeb-109">使用する方法を理解するときに、このチュートリアルを完了すると、[!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)]でコントロールを[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-ベースのアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="faeeb-109">When you have completed this walkthrough, you will understand how to use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="faeeb-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="faeeb-110">Prerequisites</span></span>  
 <span data-ttu-id="faeeb-111">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="faeeb-111">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)]<span data-ttu-id="faeeb-112"> Visual Studio がインストールされているコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="faeeb-112"> installed on the computer where Visual Studio is installed.</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="faeeb-113">。</span><span class="sxs-lookup"><span data-stu-id="faeeb-113">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="faeeb-114">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="faeeb-114">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="faeeb-115">プロジェクトを作成し、設定するには</span><span class="sxs-lookup"><span data-stu-id="faeeb-115">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="faeeb-116">という名前の WPF アプリケーション プロジェクトを作成する`HostingAxInWpf`します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>  
  
2.  <span data-ttu-id="faeeb-117">Windows フォーム コントロール ライブラリ プロジェクトをソリューションに追加し、プロジェクト名前`WmpAxLib`します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>  
  
3.  <span data-ttu-id="faeeb-118">WmpAxLib プロジェクトでは、wmp.dll の名前は、Windows Media Player アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>  
  
4.  <span data-ttu-id="faeeb-119">開く、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-119">Open the **Toolbox**.</span></span>  
  
5.  <span data-ttu-id="faeeb-120">右クリックし、**ツールボックス**、 をクリックし、**アイテムの選択**します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>  
  
6.  <span data-ttu-id="faeeb-121">をクリックして、 **COM コンポーネント**] タブで、[、 **Windows Media Player**コントロールをクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="faeeb-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>  
  
     <span data-ttu-id="faeeb-122">Windows Media Player コントロールに追加されます、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-122">The Windows Media Player control is added to the **Toolbox**.</span></span>  
  
7.  <span data-ttu-id="faeeb-123">ソリューション エクスプ ローラーで右クリックし、 **UserControl1**ファイルを開き、をクリックし、**の名前を変更**します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>  
  
8.  <span data-ttu-id="faeeb-124">名を変更して`WmpAxControl.vb`または`WmpAxControl.cs`、言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="faeeb-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>  
  
9. <span data-ttu-id="faeeb-125">すべての参照の名前を変更するメッセージが表示されたら、クリックして**はい**します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-125">If you are prompted to rename all references, click **Yes**.</span></span>  
  
## <a name="creating-the-activex-control"></a><span data-ttu-id="faeeb-126">ActiveX コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-126">Creating the ActiveX Control</span></span>  
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]<span data-ttu-id="faeeb-127"> 自動的に生成、<xref:System.Windows.Forms.AxHost>のラッパー クラスを[!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)]デザイン サーフェイスにコントロールを追加するときを制御します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-127"> automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] control when the control is added to a design surface.</span></span> <span data-ttu-id="faeeb-128">次の手順では、AxInterop.WMPLib.dll という名前のマネージ アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>  
  
#### <a name="to-create-the-activex-control"></a><span data-ttu-id="faeeb-129">ActiveX コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="faeeb-129">To create the ActiveX control</span></span>  
  
1.  <span data-ttu-id="faeeb-130">Windows フォーム デザイナーで、WmpAxControl.vb またはに応じてを開きます。</span><span class="sxs-lookup"><span data-stu-id="faeeb-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="faeeb-131">**ツールボックス**、デザイン画面に、Windows Media Player コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>  
  
3.  <span data-ttu-id="faeeb-132">[プロパティ] ウィンドウで、Windows Media Player コントロールの値を設定<xref:System.Windows.Forms.Control.Dock%2A>プロパティを<xref:System.Windows.Forms.DockStyle.Fill>します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
4.  <span data-ttu-id="faeeb-133">WmpAxLib コントロール ライブラリ プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="faeeb-133">Build the WmpAxLib control library project.</span></span>  
  
## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="faeeb-134">WPF ページ上の ActiveX コントロールをホストしています。</span><span class="sxs-lookup"><span data-stu-id="faeeb-134">Hosting the ActiveX Control on a WPF Page</span></span>  
  
#### <a name="to-host-the-activex-control"></a><span data-ttu-id="faeeb-135">ActiveX コントロールをホストするには</span><span class="sxs-lookup"><span data-stu-id="faeeb-135">To host the ActiveX control</span></span>  
  
1.  <span data-ttu-id="faeeb-136">HostingAxInWpf プロジェクトで生成されたへの参照を追加[!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)]相互運用機能アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="faeeb-136">In the HostingAxInWpf project, add a reference to the generated [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] interoperability assembly.</span></span>  
  
     <span data-ttu-id="faeeb-137">このアセンブリは、AxInterop.WMPLib.dll の名前は、Windows Media Player コントロールがインポートされるときに、WmpAxLib プロジェクトの Debug フォルダーに追加されました。</span><span class="sxs-lookup"><span data-stu-id="faeeb-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>  
  
2.  <span data-ttu-id="faeeb-138">これは、WindowsFormsIntegration.dll がという名前 WindowsFormsIntegration アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="faeeb-139">参照を追加、 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] System.Windows.Forms.dll をという名前のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="faeeb-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>  
  
4.  <span data-ttu-id="faeeb-140">WPF デザイナーで、MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="faeeb-140">Open MainWindow.xaml in the WPF Designer.</span></span>  
  
5.  <span data-ttu-id="faeeb-141">名前、<xref:System.Windows.Controls.Grid>要素`grid1`します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>  
  
     [!code-xaml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]  
  
6.  <span data-ttu-id="faeeb-142">デザイン ビューまたは XAML ビューで、選択、<xref:System.Windows.Window>要素。</span><span class="sxs-lookup"><span data-stu-id="faeeb-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>  
  
7.  <span data-ttu-id="faeeb-143">[プロパティ] ウィンドウ、**イベント**タブ。</span><span class="sxs-lookup"><span data-stu-id="faeeb-143">In the Properties window, click the **Events** tab.</span></span>  
  
8.  <span data-ttu-id="faeeb-144">ダブルクリックして、<xref:System.Windows.FrameworkElement.Loaded>イベント。</span><span class="sxs-lookup"><span data-stu-id="faeeb-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
9. <span data-ttu-id="faeeb-145">処理するために次のコードを挿入、<xref:System.Windows.FrameworkElement.Loaded>イベント。</span><span class="sxs-lookup"><span data-stu-id="faeeb-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     <span data-ttu-id="faeeb-146">このコードのインスタンスを作成、<xref:System.Windows.Forms.Integration.WindowsFormsHost>を制御しのインスタンスを追加、`AxWindowsMediaPlayer`の子としてコントロール。</span><span class="sxs-lookup"><span data-stu-id="faeeb-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>  
  
     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="faeeb-147">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="faeeb-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faeeb-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="faeeb-148">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="faeeb-149">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="faeeb-149">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)  
 [<span data-ttu-id="faeeb-150">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="faeeb-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="faeeb-151">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="faeeb-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)

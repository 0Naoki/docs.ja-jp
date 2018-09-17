---
title: 'チュートリアル: デザイン時の Windows フォームでの WPF コンテンツの割り当て'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: 6db75e9d8ec5aeb1a0c7310d39391f8f264649d3
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2018
ms.locfileid: "45689276"
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="038e8-102">チュートリアル: デザイン時の Windows フォームでの WPF コンテンツの割り当て</span><span class="sxs-lookup"><span data-stu-id="038e8-102">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="038e8-103">このチュートリアルでは、フォームに表示する Windows Presentation Foundation (WPF) コントロール型を選択する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="038e8-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="038e8-104">プロジェクトに含まれている WPF コントロール型であれば、どれでも選択できます。</span><span class="sxs-lookup"><span data-stu-id="038e8-104">You can select any WPF control types which are included in your project.</span></span>  
  
 <span data-ttu-id="038e8-105">このチュートリアルでは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="038e8-105">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="038e8-106">プロジェクトを作成する。</span><span class="sxs-lookup"><span data-stu-id="038e8-106">Create the project.</span></span>  
  
-   <span data-ttu-id="038e8-107">WPF コントロール型を作成する。</span><span class="sxs-lookup"><span data-stu-id="038e8-107">Create the WPF control types.</span></span>  
  
-   <span data-ttu-id="038e8-108">WPF コントロールを選択する。</span><span class="sxs-lookup"><span data-stu-id="038e8-108">Select WPF controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="038e8-109">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="038e8-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="038e8-110">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="038e8-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="038e8-111">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="038e8-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="038e8-112">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="038e8-112">Prerequisites</span></span>  
 <span data-ttu-id="038e8-113">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="038e8-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="038e8-114">。</span><span class="sxs-lookup"><span data-stu-id="038e8-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="038e8-115">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="038e8-115">Creating the Project</span></span>  
 <span data-ttu-id="038e8-116">まず、Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="038e8-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="038e8-117">WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="038e8-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="038e8-118">プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="038e8-118">To create the project</span></span>  
  
-   <span data-ttu-id="038e8-119">Visual Basic または Visual c# のという名前で新しい Windows フォーム アプリケーション プロジェクトを作成する`SelectingWpfContent`します。</span><span class="sxs-lookup"><span data-stu-id="038e8-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="038e8-120">WPF コントロール型の作成</span><span class="sxs-lookup"><span data-stu-id="038e8-120">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="038e8-121">プロジェクトに追加した WPF コントロール型は、さまざまな <xref:System.Windows.Forms.Integration.ElementHost> コントロール内でホストできます。</span><span class="sxs-lookup"><span data-stu-id="038e8-121">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="038e8-122">WPF コントロール型を作成するには</span><span class="sxs-lookup"><span data-stu-id="038e8-122">To create WPF control types</span></span>  
  
1.  <span data-ttu-id="038e8-123">新しい WPF <xref:System.Windows.Controls.UserControl> プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="038e8-123">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="038e8-124">コントロール型の既定の名前である `UserControl1.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="038e8-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="038e8-125">詳細については、次を参照してください。[チュートリアル: 新しい WPF コンテンツの作成には、デザイン時に Windows フォーム](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)します。</span><span class="sxs-lookup"><span data-stu-id="038e8-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="038e8-126">デザイン ビューで `UserControl1` が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="038e8-126">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="038e8-127">詳細については、次を参照してください。[方法: 選択し、デザイン サーフェイス上の要素の移動](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474)します。</span><span class="sxs-lookup"><span data-stu-id="038e8-127">For more information, see [How to: Select and Move Elements on the Design Surface](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="038e8-128">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティ`200`します。</span><span class="sxs-lookup"><span data-stu-id="038e8-128">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="038e8-129">追加、<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>への制御、<xref:System.Windows.Controls.UserControl>の値を設定し、<xref:System.Windows.Controls.TextBox.Text%2A>プロパティを**ホストするコンテンツの**します。</span><span class="sxs-lookup"><span data-stu-id="038e8-129">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
5.  <span data-ttu-id="038e8-130">WPF <xref:System.Windows.Controls.UserControl> をプロジェクトにもう 1 つ追加します。</span><span class="sxs-lookup"><span data-stu-id="038e8-130">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="038e8-131">コントロール型の既定の名前である `UserControl2.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="038e8-131">Use the default name for the control type, `UserControl2.xaml`.</span></span>  
  
6.  <span data-ttu-id="038e8-132">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティ`200`します。</span><span class="sxs-lookup"><span data-stu-id="038e8-132">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
7.  <span data-ttu-id="038e8-133">追加、<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>への制御、<xref:System.Windows.Controls.UserControl>の値を設定し、<xref:System.Windows.Controls.TextBox.Text%2A>プロパティを**Hosted Content 2**します。</span><span class="sxs-lookup"><span data-stu-id="038e8-133">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>  
  
 <span data-ttu-id="038e8-134">**注**一般より高度な WPF コンテンツをホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="038e8-134">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="038e8-135">ここでは、説明する目的でのみ <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> コントロールを使用しています。</span><span class="sxs-lookup"><span data-stu-id="038e8-135">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
1.  <span data-ttu-id="038e8-136">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="038e8-136">Build the project.</span></span>  
  
## <a name="selecting-wpf-controls"></a><span data-ttu-id="038e8-137">WPF コントロールの選択</span><span class="sxs-lookup"><span data-stu-id="038e8-137">Selecting WPF Controls</span></span>  
 <span data-ttu-id="038e8-138">既にコンテンツをホストしている <xref:System.Windows.Forms.Integration.ElementHost> コントロールに異なる WPF コンテンツを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="038e8-138">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>  
  
#### <a name="to-select-wpf-controls"></a><span data-ttu-id="038e8-139">WPF コントロールを選択するには</span><span class="sxs-lookup"><span data-stu-id="038e8-139">To select WPF controls</span></span>  
  
1.  <span data-ttu-id="038e8-140">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="038e8-140">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="038e8-141">**ツールボックス**、 をダブルクリックします`UserControl1`のインスタンスを作成する`UserControl1`形式にします。</span><span class="sxs-lookup"><span data-stu-id="038e8-141">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="038e8-142">`UserControl1` のインスタンスは、`elementHost1` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="038e8-142">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="038e8-143">スマート タグ パネルで`elementHost1`、オープン、**ホストされているコンテンツの選択**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="038e8-143">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>  
  
4.  <span data-ttu-id="038e8-144">選択 **[usercontrol2]** ドロップダウン リスト ボックスから。</span><span class="sxs-lookup"><span data-stu-id="038e8-144">Select **UserControl2** from the drop-down list box.</span></span>  
  
     <span data-ttu-id="038e8-145">これで、`elementHost1` コントロールが `UserControl2` 型のインスタンスをホストするようになりました。</span><span class="sxs-lookup"><span data-stu-id="038e8-145">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>  
  
5.  <span data-ttu-id="038e8-146">**プロパティ**ウィンドウで、いることを確認、<xref:System.Windows.Forms.Integration.ElementHost.Child%2A>プロパティに設定されて **[usercontrol2]** します。</span><span class="sxs-lookup"><span data-stu-id="038e8-146">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>  
  
6.  <span data-ttu-id="038e8-147">**ツールボックス**の**WPF 相互運用性**グループで、ドラッグ、<xref:System.Windows.Forms.Integration.ElementHost>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="038e8-147">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>  
  
     <span data-ttu-id="038e8-148">新しい名前として、このコントロールの既定である `elementHost2` を使用します。</span><span class="sxs-lookup"><span data-stu-id="038e8-148">The default name for the new control is `elementHost2`.</span></span>  
  
7.  <span data-ttu-id="038e8-149">スマート タグ パネルで`elementHost2`、オープン、**ホストされているコンテンツの選択**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="038e8-149">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>  
  
8.  <span data-ttu-id="038e8-150">選択**UserControl1**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="038e8-150">Select **UserControl1** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="038e8-151">これで、`elementHost2` コントロールが `UserControl1` 型のインスタンスをホストするようになりました。</span><span class="sxs-lookup"><span data-stu-id="038e8-151">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="038e8-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="038e8-152">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="038e8-153">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="038e8-153">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="038e8-154">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="038e8-154">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="038e8-155">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="038e8-155">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)

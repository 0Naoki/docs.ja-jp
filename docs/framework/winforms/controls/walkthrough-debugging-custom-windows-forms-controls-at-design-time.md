---
title: 'チュートリアル : カスタム Windows フォーム コントロールのデザイン時のデバッグ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
ms.openlocfilehash: 824c1e47cf50dc13a3a986e48a49158b15dbb935
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44269073"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="3923d-102">チュートリアル : カスタム Windows フォーム コントロールのデザイン時のデバッグ</span><span class="sxs-lookup"><span data-stu-id="3923d-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="3923d-103">カスタム コントロールを作成するときに多くの場合、表示されますが、デザイン時の動作をデバッグするために必要です。</span><span class="sxs-lookup"><span data-stu-id="3923d-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="3923d-104">これは、カスタム コントロールのカスタム デザイナーを作成する場合に特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="3923d-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="3923d-105">詳細については、次を参照してください。[チュートリアル: 作成、Windows フォーム コントロールを受け取るの Visual Studio デザイン時機能を利用](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)します。</span><span class="sxs-lookup"><span data-stu-id="3923d-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
 <span data-ttu-id="3923d-106">その他の .NET Framework のクラスをデバッグする場合と同様に、Visual Studio を使用して、カスタム コントロールをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="3923d-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="3923d-107">違いは、カスタム コントロールのコードを実行している Visual Studio の別のインスタンスをデバッグすることです。</span><span class="sxs-lookup"><span data-stu-id="3923d-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>  
  
 <span data-ttu-id="3923d-108">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="3923d-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="3923d-109">カスタム コントロールをホストする Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3923d-109">Creating a Windows Forms project to host your custom control</span></span>  
  
-   <span data-ttu-id="3923d-110">コントロール ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3923d-110">Creating a control library project</span></span>  
  
-   <span data-ttu-id="3923d-111">カスタム コントロールにプロパティを追加</span><span class="sxs-lookup"><span data-stu-id="3923d-111">Adding a property to your custom control</span></span>  
  
-   <span data-ttu-id="3923d-112">ホストのフォームにカスタム コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="3923d-112">Adding your custom control to the host form</span></span>  
  
-   <span data-ttu-id="3923d-113">デザイン時のデバッグ プロジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="3923d-113">Setting up the project for design-time debugging</span></span>  
  
-   <span data-ttu-id="3923d-114">カスタム コントロールをデザイン時のデバッグ</span><span class="sxs-lookup"><span data-stu-id="3923d-114">Debugging your custom control at design time</span></span>  
  
 <span data-ttu-id="3923d-115">完了したら、カスタム コントロールのデザイン時の動作をデバッグするために必要な作業について理解があります。</span><span class="sxs-lookup"><span data-stu-id="3923d-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3923d-116">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3923d-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3923d-117">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3923d-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3923d-118">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3923d-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="3923d-119">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="3923d-119">Creating the Project</span></span>  
 <span data-ttu-id="3923d-120">最初の手順では、アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3923d-120">The first step is to create the application project.</span></span> <span data-ttu-id="3923d-121">このプロジェクトを使用すると、カスタム コントロールをホストするアプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3923d-121">You will use this project to build the application that hosts the custom control.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="3923d-122">プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="3923d-122">To create the project</span></span>  
  
-   <span data-ttu-id="3923d-123">"DebuggingExample"と呼ばれる Windows アプリケーション プロジェクトを作成 (**ファイル** > **新規** > **プロジェクト** >  **Visual c#** または**Visual Basic** > **クラシック デスクトップ** > **Windows フォーム アプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="3923d-123">Create a Windows Application project called "DebuggingExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
## <a name="creating-a-control-library-project"></a><span data-ttu-id="3923d-124">コントロール ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3923d-124">Creating a Control Library Project</span></span>  
 <span data-ttu-id="3923d-125">次の手順では、コントロール ライブラリ プロジェクトを作成し、カスタム コントロールを設定します。</span><span class="sxs-lookup"><span data-stu-id="3923d-125">The next step is to create the control library project and set up the custom control.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="3923d-126">コントロール ライブラリ プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="3923d-126">To create the control library project</span></span>  
  
1.  <span data-ttu-id="3923d-127">追加、 **Windows コントロール ライブラリ**プロジェクトがソリューションにします。</span><span class="sxs-lookup"><span data-stu-id="3923d-127">Add a **Windows Control Library** project to the solution.</span></span>  
  
2.  <span data-ttu-id="3923d-128">新しい追加**UserControl** DebugControlLibrary プロジェクトに項目。</span><span class="sxs-lookup"><span data-stu-id="3923d-128">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="3923d-129">詳細については、次を参照してください。 [NIB: 方法: 新しいプロジェクト項目の追加](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)します。</span><span class="sxs-lookup"><span data-stu-id="3923d-129">For details, see [NIB:How to: Add New Project Items](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span> <span data-ttu-id="3923d-130">新しいソース ファイルに「タブ」の基本の名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="3923d-130">Give the new source file a base name of "DebugControl".</span></span>  
  
3.  <span data-ttu-id="3923d-131">使用して、**ソリューション エクスプ ローラー**の基本名を持つコード ファイルを削除することによって、プロジェクトの既定のコントロールを削除"`UserControl1`"。</span><span class="sxs-lookup"><span data-stu-id="3923d-131">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="3923d-132">詳細については、次を参照してください。 [NIB: 方法: 削除、削除、および除外項目](https://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)します。</span><span class="sxs-lookup"><span data-stu-id="3923d-132">For details, see [NIB:How to: Remove, Delete, and Exclude Items](https://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
4.  <span data-ttu-id="3923d-133">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3923d-133">Build the solution.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="3923d-134">チェックポイント</span><span class="sxs-lookup"><span data-stu-id="3923d-134">Checkpoint</span></span>  
 <span data-ttu-id="3923d-135">この時点では、ことができますでカスタム コントロールを表示する、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="3923d-135">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>  
  
#### <a name="to-check-your-progress"></a><span data-ttu-id="3923d-136">進行状況をチェックするには</span><span class="sxs-lookup"><span data-stu-id="3923d-136">To check your progress</span></span>  
  
-   <span data-ttu-id="3923d-137">という新しいタブを見つけます**DebugControlLibrary コンポーネント** をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="3923d-137">Find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="3923d-138">開くときに、コントロールが表示されます**タブ**の横にある既定のアイコン。</span><span class="sxs-lookup"><span data-stu-id="3923d-138">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>  
  
## <a name="adding-a-property-to-your-custom-control"></a><span data-ttu-id="3923d-139">カスタム コントロールにプロパティを追加</span><span class="sxs-lookup"><span data-stu-id="3923d-139">Adding a Property to Your Custom Control</span></span>  
 <span data-ttu-id="3923d-140">デザイン時にカスタム コントロールのコードが実行されていることを示すためは、プロパティを追加し、プロパティを実装するコードにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="3923d-140">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>  
  
#### <a name="to-add-a-property-to-your-custom-control"></a><span data-ttu-id="3923d-141">カスタム コントロールにプロパティを追加するには</span><span class="sxs-lookup"><span data-stu-id="3923d-141">To add a property to your custom control</span></span>  
  
1.  <span data-ttu-id="3923d-142">開いている**タブ**で、**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="3923d-142">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="3923d-143">クラス定義には、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3923d-143">Add the following code to the class definition:</span></span>  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  <span data-ttu-id="3923d-144">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3923d-144">Build the solution.</span></span>  
  
## <a name="adding-your-custom-control-to-the-host-form"></a><span data-ttu-id="3923d-145">ホストのフォームにカスタム コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="3923d-145">Adding Your Custom Control to the Host Form</span></span>  
 <span data-ttu-id="3923d-146">カスタム コントロールのデザイン時の動作をデバッグするには、ホストのフォームにカスタム コントロール クラスのインスタンスを配置します。</span><span class="sxs-lookup"><span data-stu-id="3923d-146">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a><span data-ttu-id="3923d-147">ホストのフォームにカスタム コントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="3923d-147">To add your custom control to the host form</span></span>  
  
1.  <span data-ttu-id="3923d-148">"DebuggingExample"プロジェクトで、Form1 を開き、 **Windows フォーム デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="3923d-148">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="3923d-149">**ツールボックス**、オープン、 **DebugControlLibrary コンポーネント**タブし、ドラッグ、**タブ**フォーム上にインスタンス。</span><span class="sxs-lookup"><span data-stu-id="3923d-149">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>  
  
3.  <span data-ttu-id="3923d-150">検索、`DemoString`にカスタム プロパティ、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="3923d-150">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="3923d-151">他のプロパティと同様、その値を変更できますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3923d-151">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="3923d-152">場合にも注意してください、`DemoString`プロパティが選択されている場合の下部にあるプロパティの説明文字列が表示されます、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="3923d-152">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="3923d-153">デザイン時のデバッグ プロジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="3923d-153">Setting Up the Project for Design-Time Debugging</span></span>  
 <span data-ttu-id="3923d-154">カスタム コントロールのデザイン時の動作をデバッグするには、カスタム コントロールのコードを実行している Visual Studio の別のインスタンスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="3923d-154">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="3923d-155">デザイン時のデバッグ プロジェクトを設定するには</span><span class="sxs-lookup"><span data-stu-id="3923d-155">To set up the project for design-time debugging</span></span>  
  
1.  <span data-ttu-id="3923d-156">右クリックし、 **DebugControlLibrary**プロジェクト、**ソリューション エクスプ ローラー**選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="3923d-156">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="3923d-157">**DebugControlLibrary**プロパティ シート、**デバッグ**タブ。</span><span class="sxs-lookup"><span data-stu-id="3923d-157">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>  
  
     <span data-ttu-id="3923d-158">**開始動作**セクションで、**外部プログラムの開始**します。</span><span class="sxs-lookup"><span data-stu-id="3923d-158">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="3923d-159">されますので、省略記号をクリックして、Visual Studio の別のインスタンスをデバッグ (![VisualStudioEllipsesButton スクリーン ショット](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton"))、Visual Studio IDE を参照するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3923d-159">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="3923d-160">実行可能ファイルの名前は**devenv.exe**、され、パスは %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe で既定の場所にインストールした場合。</span><span class="sxs-lookup"><span data-stu-id="3923d-160">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>  
  
3.  <span data-ttu-id="3923d-161">**[OK]** をクリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3923d-161">Click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="3923d-162">右クリックし、 **DebugControlLibrary**順に選択して**スタートアップ プロジェクトとして設定**このデバッグ構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3923d-162">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>  
  
## <a name="debugging-your-custom-control-at-design-time"></a><span data-ttu-id="3923d-163">カスタム コントロールをデザイン時のデバッグ</span><span class="sxs-lookup"><span data-stu-id="3923d-163">Debugging Your Custom Control at Design Time</span></span>  
 <span data-ttu-id="3923d-164">デザイン モードで実行するときに、カスタム コントロールをデバッグする準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="3923d-164">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="3923d-165">デバッグ セッションを開始して、Visual Studio の新しいインスタンスを作成は"DebuggingExample"ソリューションの読み込みに使用します。</span><span class="sxs-lookup"><span data-stu-id="3923d-165">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="3923d-166">Form1 を開くと、**フォーム デザイナー**、カスタム コントロールのインスタンスが作成され、実行が開始されます。</span><span class="sxs-lookup"><span data-stu-id="3923d-166">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a><span data-ttu-id="3923d-167">デザイン時に、カスタム コントロールをデバッグするには</span><span class="sxs-lookup"><span data-stu-id="3923d-167">To debug your custom control at design time</span></span>  
  
1.  <span data-ttu-id="3923d-168">開く、**タブ**内のソース ファイル、**コード エディター**にブレークポイントを配置し、`Set`のアクセサー、`DemoString`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3923d-168">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>  
  
2.  <span data-ttu-id="3923d-169">F5 キーを押して、デバッグ セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="3923d-169">Press F5 to start the debugging session.</span></span> <span data-ttu-id="3923d-170">Visual Studio の新しいインスタンスが作成されたことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3923d-170">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="3923d-171">2 つの方法でインスタンスを区別することができます。</span><span class="sxs-lookup"><span data-stu-id="3923d-171">You can distinguish between the instances in two ways:</span></span>  
  
    -   <span data-ttu-id="3923d-172">デバッグ インスタンスが、word**を実行している**のタイトル バーに</span><span class="sxs-lookup"><span data-stu-id="3923d-172">The debugging instance has the word **Running** in its title bar</span></span>  
  
    -   <span data-ttu-id="3923d-173">デバッグ インスタンスが、**開始**のボタンではその**デバッグ**ツールバーを無効になっています</span><span class="sxs-lookup"><span data-stu-id="3923d-173">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>  
  
     <span data-ttu-id="3923d-174">デバッグ インスタンスで、ブレークポイントが設定されます。</span><span class="sxs-lookup"><span data-stu-id="3923d-174">Your breakpoint is set in the debugging instance.</span></span>  
  
3.  <span data-ttu-id="3923d-175">Visual Studio の新しいインスタンスでは、"DebuggingExample"ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="3923d-175">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="3923d-176">選択して、ソリューションを簡単に見つけることができます**最近使ったプロジェクト**から、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="3923d-176">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="3923d-177">"DebuggingExample.sln"ソリューション ファイルは、最近使用したファイルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="3923d-177">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>  
  
4.  <span data-ttu-id="3923d-178">Form1 を開き、**フォーム デザイナー**を選択し、**タブ**コントロール。</span><span class="sxs-lookup"><span data-stu-id="3923d-178">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>  
  
5.  <span data-ttu-id="3923d-179">値を変更、`DemoString`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3923d-179">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="3923d-180">変更をコミットするときに、Visual Studio のデバッグ インスタンスがフォーカスを取得し、実行がブレークポイントで停止に注意してください。</span><span class="sxs-lookup"><span data-stu-id="3923d-180">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="3923d-181">プロパティ アクセサーを 1 ステップを実行できますと同様、その他のコードには。</span><span class="sxs-lookup"><span data-stu-id="3923d-181">You can single-step through the property accessor just as your would any other code.</span></span>  
  
6.  <span data-ttu-id="3923d-182">Visual Studio のホスト インスタンスを閉じるか、クリックして終了する、デバッグ セッションがしたら、**デバッグの停止**デバッグ インスタンスでボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3923d-182">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3923d-183">次の手順</span><span class="sxs-lookup"><span data-stu-id="3923d-183">Next Steps</span></span>  
 <span data-ttu-id="3923d-184">これで、カスタム コントロールをデバッグするにはデザイン時に、Visual Studio IDE とコントロールの相互作用を拡張するためのさまざまな操作があります。</span><span class="sxs-lookup"><span data-stu-id="3923d-184">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>  
  
-   <span data-ttu-id="3923d-185">使用することができます、<xref:System.ComponentModel.Component.DesignMode%2A>のプロパティ、<xref:System.ComponentModel.Component>クラスはデザイン時にのみ実行するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="3923d-185">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="3923d-186">詳細については、「<xref:System.ComponentModel.Component.DesignMode%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3923d-186">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>  
  
-   <span data-ttu-id="3923d-187">いくつかの属性があるデザイナーを使用したカスタム コントロールの相互作用を操作するコントロールのプロパティに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="3923d-187">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="3923d-188">これらの属性を見つけることができます、<xref:System.ComponentModel?displayProperty=nameWithType>名前空間。</span><span class="sxs-lookup"><span data-stu-id="3923d-188">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>  
  
-   <span data-ttu-id="3923d-189">カスタム コントロールのカスタム デザイナーを記述できます。</span><span class="sxs-lookup"><span data-stu-id="3923d-189">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="3923d-190">これにより、Visual Studio によって公開される拡張可能なデザイナー インフラストラクチャを使用して、デザイン エクスペリエンスを完全に制御できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3923d-190">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="3923d-191">詳細については、次を参照してください。[チュートリアル: 作成、Windows フォーム コントロールを受け取るの Visual Studio デザイン時機能を利用](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)します。</span><span class="sxs-lookup"><span data-stu-id="3923d-191">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3923d-192">関連項目</span><span class="sxs-lookup"><span data-stu-id="3923d-192">See Also</span></span>  
 [<span data-ttu-id="3923d-193">チュートリアル: Visual Studio のデザイン時機能を活用した Windows フォーム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="3923d-193">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [<span data-ttu-id="3923d-194">方法: デザイン時サービスにアクセス</span><span class="sxs-lookup"><span data-stu-id="3923d-194">How to: Access Design-Time Services</span></span>](https://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [<span data-ttu-id="3923d-195">方法: Windows フォームでデザイン時サポートにアクセスする</span><span class="sxs-lookup"><span data-stu-id="3923d-195">How to: Access Design-Time Support in Windows Forms</span></span>](https://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)

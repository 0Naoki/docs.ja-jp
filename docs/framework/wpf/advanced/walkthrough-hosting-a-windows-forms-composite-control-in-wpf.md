---
title: 'チュートリアル: WPF で Windows フォーム複合コントロールのホスト'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: f18d6e98e40c8517bbee32702f03dad57064051a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661338"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a><span data-ttu-id="e7580-102">チュートリアル: WPF で Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="e7580-102">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="e7580-103">は、アプリケーションの作成に適した環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="e7580-103">provides a rich environment for creating applications.</span></span> <span data-ttu-id="e7580-104">ただしがある場合、かなりの投資[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コードをより効果的か以上で再利用するには、そのコードの一部、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションではなく最初から修正します。</span><span class="sxs-lookup"><span data-stu-id="e7580-104">However, when you have a substantial investment in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] code, it can be more effective to reuse at least some of that code in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application rather than to rewrite it from scratch.</span></span> <span data-ttu-id="e7580-105">最も一般的なシナリオでは、既存の Windows フォーム コントロールがある場合です。</span><span class="sxs-lookup"><span data-stu-id="e7580-105">The most common scenario is when you have existing Windows Forms controls.</span></span> <span data-ttu-id="e7580-106">場合によってもがありませんこれらのコントロールのソース コードにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e7580-106">In some cases, you might not even have access to the source code for these controls.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="e7580-107">このようなコントロールをホストするため、簡単な手順を提供する[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="e7580-107">provides a straightforward procedure for hosting such controls in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="e7580-108">たとえば、使用することができます[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]、特殊なをホストしているときに、プログラミングの大部分の<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="e7580-108">For example, you can use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] for most of your programming while hosting your specialized <xref:System.Windows.Forms.DataGridView> controls.</span></span>  
  
 <span data-ttu-id="e7580-109">このチュートリアルでのデータ入力を実行する Windows フォーム複合コントロールをホストするアプリケーションを通じて、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="e7580-109">This walkthrough steps you through an application that hosts a Windows Forms composite control to perform data entry in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="e7580-110">複合コントロールは DLL にパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="e7580-110">The composite control is packaged in a DLL.</span></span> <span data-ttu-id="e7580-111">この一般的な手順は、より複雑なアプリケーションやコントロールに拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="e7580-111">This general procedure can be extended to more complex applications and controls.</span></span> <span data-ttu-id="e7580-112">このチュートリアルの外観と機能をほぼ同じにする目的は[チュートリアル。Windows フォームでの WPF 複合コントロールをホストしている](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="e7580-112">This walkthrough is designed to be nearly identical in appearance and functionality to [Walkthrough: Hosting a WPF Composite Control in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span></span> <span data-ttu-id="e7580-113">主な違いは、ホストする側とされる側が逆であることです。</span><span class="sxs-lookup"><span data-stu-id="e7580-113">The primary difference is that the hosting scenario is reversed.</span></span>  
  
 <span data-ttu-id="e7580-114">このチュートリアルは、2 つのセクションに分かれています。</span><span class="sxs-lookup"><span data-stu-id="e7580-114">The walkthrough is divided into two sections.</span></span> <span data-ttu-id="e7580-115">最初のセクションでは、Windows フォーム複合コントロールの実装について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="e7580-115">The first section briefly describes the implementation of the Windows Forms composite control.</span></span> <span data-ttu-id="e7580-116">2 番目のセクションで詳細に複合コントロールをホストする方法について説明します、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションでは、コントロールからイベントを受信し、コントロールのプロパティの一部にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e7580-116">The second section discusses in detail how to host the composite control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, receive events from the control, and access some of the control's properties.</span></span>  
  
 <span data-ttu-id="e7580-117">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="e7580-117">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="e7580-118">Windows フォーム複合コントロールを実装します。</span><span class="sxs-lookup"><span data-stu-id="e7580-118">Implementing the Windows Forms composite control.</span></span>  
  
-   <span data-ttu-id="e7580-119">WPF ホスト アプリケーションの実装。</span><span class="sxs-lookup"><span data-stu-id="e7580-119">Implementing the WPF host application.</span></span>  
  
 <span data-ttu-id="e7580-120">このチュートリアルで示すタスクの完全なコード一覧については、次を参照してください。 [WPF サンプル Windows フォーム複合コントロールをホストしている](https://go.microsoft.com/fwlink/?LinkID=159999)します。</span><span class="sxs-lookup"><span data-stu-id="e7580-120">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a Windows Forms Composite Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159999).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e7580-121">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e7580-121">Prerequisites</span></span>  

<span data-ttu-id="e7580-122">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="e7580-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="implementing-the-windows-forms-composite-control"></a><span data-ttu-id="e7580-123">Windows フォーム複合コントロールを実装します。</span><span class="sxs-lookup"><span data-stu-id="e7580-123">Implementing the Windows Forms Composite Control</span></span>  
 <span data-ttu-id="e7580-124">この例で使用される Windows フォーム複合コントロールは、単純なデータ入力フォームです。</span><span class="sxs-lookup"><span data-stu-id="e7580-124">The Windows Forms composite control used in this example is a simple data-entry form.</span></span> <span data-ttu-id="e7580-125">このフォームは、ユーザーの名前とアドレスを受け取るし、カスタム イベントを使用してホストにその情報を返します。</span><span class="sxs-lookup"><span data-stu-id="e7580-125">This form takes the user's name and address and then uses a custom event to return that information to the host.</span></span> <span data-ttu-id="e7580-126">次の図はレンダリングされたコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="e7580-126">The following illustration shows the rendered control.</span></span>  
  
 <span data-ttu-id="e7580-127">![単純な Windows フォーム コントロールの](../../../../docs/framework/wpf/advanced/media/wfcontrol.gif "WFControl")</span><span class="sxs-lookup"><span data-stu-id="e7580-127">![Simple Windows Forms control](../../../../docs/framework/wpf/advanced/media/wfcontrol.gif "WFControl")</span></span>  
<span data-ttu-id="e7580-128">Windows フォーム複合コントロール</span><span class="sxs-lookup"><span data-stu-id="e7580-128">Windows Forms composite control</span></span>  
  
### <a name="creating-the-project"></a><span data-ttu-id="e7580-129">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="e7580-129">Creating the Project</span></span>  
 <span data-ttu-id="e7580-130">プロジェクトを開始するには</span><span class="sxs-lookup"><span data-stu-id="e7580-130">To start the project:</span></span>  
  
1.  <span data-ttu-id="e7580-131">起動[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]を開き、**新しいプロジェクト** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e7580-131">Launch [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="e7580-132">ウィンドウのカテゴリの選択、 **Windows フォーム コントロール ライブラリ**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="e7580-132">In the Window category, select the **Windows Forms Control Library** template.</span></span>  
  
3.  <span data-ttu-id="e7580-133">新しいプロジェクトに `MyControls` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="e7580-133">Name the new project `MyControls`.</span></span>  
  
4.  <span data-ttu-id="e7580-134">など指定便利な名前付きの最上位フォルダーの場所`WpfHostingWindowsFormsControl`します。</span><span class="sxs-lookup"><span data-stu-id="e7580-134">For the location, specify a conveniently named top-level folder, such as `WpfHostingWindowsFormsControl`.</span></span> <span data-ttu-id="e7580-135">このフォルダーには後でホスト アプリケーションも配置します。</span><span class="sxs-lookup"><span data-stu-id="e7580-135">Later, you will put the host application in this folder.</span></span>  
  
5.  <span data-ttu-id="e7580-136">**[OK]** をクリックして、プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7580-136">Click **OK** to create the project.</span></span> <span data-ttu-id="e7580-137">既定のプロジェクトには、という名前の 1 つのコントロールが含まれています。`UserControl1`します。</span><span class="sxs-lookup"><span data-stu-id="e7580-137">The default project contains a single control named `UserControl1`.</span></span>  
  
6.  <span data-ttu-id="e7580-138">ソリューション エクスプローラで、名前を変更`UserControl1`に`MyControl1`します。</span><span class="sxs-lookup"><span data-stu-id="e7580-138">In Solution Explorer, rename `UserControl1` to `MyControl1`.</span></span>  
  
 <span data-ttu-id="e7580-139">プロジェクトは、以下のシステム DLL を参照している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7580-139">Your project should have references to the following system DLLs.</span></span> <span data-ttu-id="e7580-140">既定で含まれていないこれらの Dll のいずれかの場合は、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e7580-140">If any of these DLLs are not included by default, add them to the project.</span></span>  
  
-   <span data-ttu-id="e7580-141">システム</span><span class="sxs-lookup"><span data-stu-id="e7580-141">System</span></span>  
  
-   <span data-ttu-id="e7580-142">System.Data</span><span class="sxs-lookup"><span data-stu-id="e7580-142">System.Data</span></span>  
  
-   <span data-ttu-id="e7580-143">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="e7580-143">System.Drawing</span></span>  
  
-   <span data-ttu-id="e7580-144">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="e7580-144">System.Windows.Forms</span></span>  
  
-   <span data-ttu-id="e7580-145">System.Xml</span><span class="sxs-lookup"><span data-stu-id="e7580-145">System.Xml</span></span>  
  
### <a name="adding-controls-to-the-form"></a><span data-ttu-id="e7580-146">フォームへのコントロールの追加</span><span class="sxs-lookup"><span data-stu-id="e7580-146">Adding Controls to the Form</span></span>  
 <span data-ttu-id="e7580-147">コントロールをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="e7580-147">To add controls to the form:</span></span>  
  
-   <span data-ttu-id="e7580-148">開いている`MyControl1`デザイナー。</span><span class="sxs-lookup"><span data-stu-id="e7580-148">Open `MyControl1` in the designer.</span></span>  
  
 <span data-ttu-id="e7580-149">5 つ追加<xref:System.Windows.Forms.Label>コントロールとそれに対応する<xref:System.Windows.Forms.TextBox>コントロール、サイズ、およびフォーム上の図のように配置されます。</span><span class="sxs-lookup"><span data-stu-id="e7580-149">Add five <xref:System.Windows.Forms.Label> controls and their corresponding <xref:System.Windows.Forms.TextBox> controls, sized and arranged as they are in the preceding illustration, on the form.</span></span> <span data-ttu-id="e7580-150">例では、<xref:System.Windows.Forms.TextBox>コントロールの名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="e7580-150">In the example, the <xref:System.Windows.Forms.TextBox> controls are named:</span></span>  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 <span data-ttu-id="e7580-151">2 つ追加<xref:System.Windows.Forms.Button>というラベルの付いたコントロール**OK**と**キャンセル**します。</span><span class="sxs-lookup"><span data-stu-id="e7580-151">Add two <xref:System.Windows.Forms.Button> controls labeled **OK** and **Cancel**.</span></span> <span data-ttu-id="e7580-152">この例では、ボタン名は`btnOK`と`btnCancel`、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="e7580-152">In the example, the button names are `btnOK` and `btnCancel`, respectively.</span></span>  
  
### <a name="implementing-the-supporting-code"></a><span data-ttu-id="e7580-153">サポート コードを実装します。</span><span class="sxs-lookup"><span data-stu-id="e7580-153">Implementing the Supporting Code</span></span>  
 <span data-ttu-id="e7580-154">コード ビューで、フォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="e7580-154">Open the form in code view.</span></span> <span data-ttu-id="e7580-155">コントロールがそのホストにカスタムを発生させることによって、収集したデータを返します`OnButtonClick`イベント。</span><span class="sxs-lookup"><span data-stu-id="e7580-155">The control returns the collected data to its host by raising the custom `OnButtonClick` event.</span></span> <span data-ttu-id="e7580-156">データは、イベント引数オブジェクトに含まれます。</span><span class="sxs-lookup"><span data-stu-id="e7580-156">The data is contained in the event argument object.</span></span> <span data-ttu-id="e7580-157">次のコードでは、イベントとデリゲートの宣言を示します。</span><span class="sxs-lookup"><span data-stu-id="e7580-157">The following code shows the event and delegate declaration.</span></span>  
  
 <span data-ttu-id="e7580-158">`MyControl1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e7580-158">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 <span data-ttu-id="e7580-159">`MyControlEventArgs`クラスには、ホストに返される情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7580-159">The `MyControlEventArgs` class contains the information to be returned to the host.</span></span>

 <span data-ttu-id="e7580-160">フォームに次のクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="e7580-160">Add the following class to the form.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 <span data-ttu-id="e7580-161">ユーザーがクリックすると、 **ok**または**キャンセル** ボタン、<xref:System.Windows.Forms.Control.Click>イベント ハンドラーを作成、`MyControlEventArgs`データを格納しているオブジェクトさせ、`OnButtonClick`イベント。</span><span class="sxs-lookup"><span data-stu-id="e7580-161">When the user clicks the **OK** or **Cancel** button, the <xref:System.Windows.Forms.Control.Click> event handlers create a `MyControlEventArgs` object that contains the data and raises the `OnButtonClick` event.</span></span> <span data-ttu-id="e7580-162">2 つのハンドラーの唯一の違いは、イベント引数の`IsOK`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e7580-162">The only difference between the two handlers is the event argument's `IsOK` property.</span></span> <span data-ttu-id="e7580-163">このプロパティは、どのボタンがクリックされたかを判断するホストを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e7580-163">This property enables the host to determine which button was clicked.</span></span> <span data-ttu-id="e7580-164">設定されている`true`の **[ok]** ボタン、および`false`の**キャンセル**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7580-164">It is set to `true` for the **OK** button, and `false` for the **Cancel** button.</span></span> <span data-ttu-id="e7580-165">次のコードは、2 つのボタン ハンドラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="e7580-165">The following code shows the two button handlers.</span></span>

 <span data-ttu-id="e7580-166">`MyControl1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e7580-166">Add the following code to the `MyControl1` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a><span data-ttu-id="e7580-167">アセンブリに厳密な名前を付けると、アセンブリのビルド</span><span class="sxs-lookup"><span data-stu-id="e7580-167">Giving the Assembly a Strong Name and Building the Assembly</span></span>
 <span data-ttu-id="e7580-168">このアセンブリによって参照されるの[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションでは、厳密な名前必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7580-168">For this assembly to be referenced by a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, it must have a strong name.</span></span> <span data-ttu-id="e7580-169">厳密な名前を作成するには、Sn.exe でキー ファイルを作成し、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e7580-169">To create a strong name, create a key file with Sn.exe and add it to your project.</span></span>

1.  <span data-ttu-id="e7580-170">[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] のコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e7580-170">Open a [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] command prompt.</span></span> <span data-ttu-id="e7580-171">これを行うには、クリックして、**開始**] メニューの [クリックして**すべてのプログラムまたは Microsoft Visual Studio 2010 または Visual Studio ツール/visual Studio コマンド プロンプト**。</span><span class="sxs-lookup"><span data-stu-id="e7580-171">To do so, click the **Start** menu, and then select **All Programs/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio Command Prompt**.</span></span> <span data-ttu-id="e7580-172">これは、カスタマイズされた環境変数のコンソール ウィンドウを起動します。</span><span class="sxs-lookup"><span data-stu-id="e7580-172">This launches a console window with customized environment variables.</span></span>

2.  <span data-ttu-id="e7580-173">コマンド プロンプトを使用して、`cd`コマンドをプロジェクト フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="e7580-173">At the command prompt, use the `cd` command to go to your project folder.</span></span>

3.  <span data-ttu-id="e7580-174">次のコマンドを実行して MyControls.snk をという名前のキー ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="e7580-174">Generate a key file named MyControls.snk by running the following command.</span></span>

    ```
    Sn.exe -k MyControls.snk
    ```

4.  <span data-ttu-id="e7580-175">キー ファイルをプロジェクトに含めるにソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="e7580-175">To include the key file in your project, right-click the project name in Solution Explorer and then click **Properties**.</span></span> <span data-ttu-id="e7580-176">プロジェクト デザイナーで、クリックして、**署名**] タブで、[、**アセンブリに署名**チェック ボックスをオンし、キー ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="e7580-176">In the Project Designer, click the **Signing** tab, select the **Sign the assembly** check box and then browse to your key file.</span></span>

5.  <span data-ttu-id="e7580-177">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e7580-177">Build the solution.</span></span> <span data-ttu-id="e7580-178">ビルドでは、MyControls.dll という名前の DLL が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e7580-178">The build will produce a DLL named MyControls.dll.</span></span>

## <a name="implementing-the-wpf-host-application"></a><span data-ttu-id="e7580-179">WPF ホスト アプリケーションの実装</span><span class="sxs-lookup"><span data-stu-id="e7580-179">Implementing the WPF Host Application</span></span>
 <span data-ttu-id="e7580-180">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ホスト アプリケーションで使用する、<xref:System.Windows.Forms.Integration.WindowsFormsHost>コントロールをホストに`MyControl1`します。</span><span class="sxs-lookup"><span data-stu-id="e7580-180">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] host application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control to host `MyControl1`.</span></span> <span data-ttu-id="e7580-181">アプリケーションのハンドル、`OnButtonClick`コントロールからデータを受信するイベントです。</span><span class="sxs-lookup"><span data-stu-id="e7580-181">The application handles the `OnButtonClick` event to receive the data from the control.</span></span> <span data-ttu-id="e7580-182">コントロールのプロパティの一部を変更するためのオプション ボタンのコレクションがあります、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="e7580-182">It also has a collection of option buttons that enable you to change some of the control's properties from the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="e7580-183">次の図は、完成したアプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="e7580-183">The following illustration shows the finished application.</span></span>

 <span data-ttu-id="e7580-184">![WPF ページに埋め込まれたコントロール](../../../../docs/framework/wpf/advanced/media/avalonhost.gif "AvalonHost") 、完全なアプリケーションは、WPF アプリケーションに埋め込まれたコントロールを表示</span><span class="sxs-lookup"><span data-stu-id="e7580-184">![A control embedded in a WPF page](../../../../docs/framework/wpf/advanced/media/avalonhost.gif "AvalonHost") The complete application, showing the control embedded in the WPF application</span></span>

### <a name="creating-the-project"></a><span data-ttu-id="e7580-185">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="e7580-185">Creating the Project</span></span>
 <span data-ttu-id="e7580-186">プロジェクトを開始するには</span><span class="sxs-lookup"><span data-stu-id="e7580-186">To start the project:</span></span>

1.  <span data-ttu-id="e7580-187">開いている[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]、選択および**新しいプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="e7580-187">Open [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], and select **New Project**.</span></span>

2.  <span data-ttu-id="e7580-188">ウィンドウのカテゴリの選択、 **WPF アプリケーション**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="e7580-188">In the Window category, select the **WPF Application** template.</span></span>

3.  <span data-ttu-id="e7580-189">新しいプロジェクトに `WpfHost` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="e7580-189">Name the new project `WpfHost`.</span></span>

4.  <span data-ttu-id="e7580-190">配置場所として、MyControls の配置先と同じ最上位フォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7580-190">For the location, specify the same top-level folder that contains the MyControls project.</span></span>

5.  <span data-ttu-id="e7580-191">**[OK]** をクリックして、プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7580-191">Click **OK** to create the project.</span></span>

 <span data-ttu-id="e7580-192">含んでいる DLL への参照を追加する必要があります`MyControl1`およびその他のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="e7580-192">You also need to add references to the DLL that contains `MyControl1` and other assemblies.</span></span>

1.  <span data-ttu-id="e7580-193">ソリューション エクスプ ローラーでプロジェクト名を右クリックして**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="e7580-193">Right-click the project name in Solution Explorer and select **Add Reference**.</span></span>

2.  <span data-ttu-id="e7580-194">をクリックして、**参照**タブをクリックし、MyControls.dll を含むフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="e7580-194">Click the **Browse** tab, and browse to the folder that contains MyControls.dll.</span></span> <span data-ttu-id="e7580-195">このチュートリアルの場合は、MyControls\bin\Debug フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="e7580-195">For this walkthrough, this folder is MyControls\bin\Debug.</span></span>

3.  <span data-ttu-id="e7580-196">MyControls.dll を選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e7580-196">Select MyControls.dll, and then click **OK**.</span></span>

4.  <span data-ttu-id="e7580-197">これは、WindowsFormsIntegration.dll がという名前 WindowsFormsIntegration アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="e7580-197">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

### <a name="implementing-the-basic-layout"></a><span data-ttu-id="e7580-198">基本的なレイアウトを実装します。</span><span class="sxs-lookup"><span data-stu-id="e7580-198">Implementing the Basic Layout</span></span>
 <span data-ttu-id="e7580-199">[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] MainWindow.xaml で、ホストのアプリケーションを実装します。</span><span class="sxs-lookup"><span data-stu-id="e7580-199">The [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] of the host application is implemented in MainWindow.xaml.</span></span> <span data-ttu-id="e7580-200">このファイルを含む[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]レイアウトを定義し、Windows フォーム コントロールをホストするマークアップ。</span><span class="sxs-lookup"><span data-stu-id="e7580-200">This file contains [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup that defines the layout, and hosts the Windows Forms control.</span></span> <span data-ttu-id="e7580-201">アプリケーションは、3 つのリージョンに分かれています。</span><span class="sxs-lookup"><span data-stu-id="e7580-201">The application is divided into three regions:</span></span>

-   <span data-ttu-id="e7580-202">**コントロール プロパティ**パネルで、ホストされるコントロールのさまざまなプロパティを変更に使用できるオプション ボタンのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7580-202">The **Control Properties** panel, which contains a collection of option buttons that you can use to modify various properties of the hosted control.</span></span>

-   <span data-ttu-id="e7580-203">**コントロールからのデータ**パネルで、いくつか含む<xref:System.Windows.Controls.TextBlock>ホストされるコントロールからデータを表示する要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="e7580-203">The **Data from Control** panel, which contains several <xref:System.Windows.Controls.TextBlock> elements that display the data returned from the hosted control.</span></span>

-   <span data-ttu-id="e7580-204">ホストされるコントロール自体。</span><span class="sxs-lookup"><span data-stu-id="e7580-204">The hosted control itself.</span></span>

 <span data-ttu-id="e7580-205">次の XAML は、基本的なレイアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7580-205">The basic layout is shown in the following XAML.</span></span> <span data-ttu-id="e7580-206">ために必要なマークアップをホストに`MyControl1`をこの例から省略するは、後ほど説明します。</span><span class="sxs-lookup"><span data-stu-id="e7580-206">The markup that is needed to host `MyControl1` is omitted from this example, but will be discussed later.</span></span>

 <span data-ttu-id="e7580-207">MainWindow.xaml で XAML を次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e7580-207">Replace the XAML in MainWindow.xaml with the following.</span></span> <span data-ttu-id="e7580-208">Visual Basic を使用している場合にクラスを変更`x:Class="MainWindow"`します。</span><span class="sxs-lookup"><span data-stu-id="e7580-208">If you are using Visual Basic, change the class to `x:Class="MainWindow"`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 <span data-ttu-id="e7580-209">最初の<xref:System.Windows.Controls.StackPanel>要素には、複数のセットが含まれています。<xref:System.Windows.Controls.RadioButton>ホストされるコントロールのさまざまな既定のプロパティを変更できるようにするコントロール。</span><span class="sxs-lookup"><span data-stu-id="e7580-209">The first <xref:System.Windows.Controls.StackPanel> element contains several sets of <xref:System.Windows.Controls.RadioButton> controls that enable you to modify various default properties of the hosted control.</span></span> <span data-ttu-id="e7580-210">これは、後は、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素、どのホスト`MyControl1`します。</span><span class="sxs-lookup"><span data-stu-id="e7580-210">That is followed by a <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, which hosts `MyControl1`.</span></span> <span data-ttu-id="e7580-211">最終的な<xref:System.Windows.Controls.StackPanel>要素がいくつか含まれています<xref:System.Windows.Controls.TextBlock>ホストされるコントロールによって返されるデータを表示する要素。</span><span class="sxs-lookup"><span data-stu-id="e7580-211">The final <xref:System.Windows.Controls.StackPanel> element contains several <xref:System.Windows.Controls.TextBlock> elements that display the data that is returned by the hosted control.</span></span> <span data-ttu-id="e7580-212">要素の順序と<xref:System.Windows.Controls.DockPanel.Dock%2A>と<xref:System.Windows.FrameworkElement.Height%2A>属性の設定では、ウィンドウにホストされるコントロールを埋め込むギャップやゆがみがないです。</span><span class="sxs-lookup"><span data-stu-id="e7580-212">The ordering of the elements and the <xref:System.Windows.Controls.DockPanel.Dock%2A> and <xref:System.Windows.FrameworkElement.Height%2A> attribute settings embed the hosted control into the window with no gaps or distortion.</span></span>

#### <a name="hosting-the-control"></a><span data-ttu-id="e7580-213">コントロールをホストしています。</span><span class="sxs-lookup"><span data-stu-id="e7580-213">Hosting the Control</span></span>
 <span data-ttu-id="e7580-214">次の編集したバージョン以前の XAML のために必要な要素について重点的にホスト`MyControl1`します。</span><span class="sxs-lookup"><span data-stu-id="e7580-214">The following edited version of the previous XAML focuses on the elements that are needed to host `MyControl1`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 <span data-ttu-id="e7580-215">`xmlns`マッピング属性の名前空間への参照を作成し、`MyControls`ホストされるコントロールを含む名前空間。</span><span class="sxs-lookup"><span data-stu-id="e7580-215">The `xmlns` namespace mapping attribute creates a reference to the `MyControls` namespace that contains the hosted control.</span></span> <span data-ttu-id="e7580-216">このマッピングを使用すると、表す`MyControl1`で[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]として`<mcl:MyControl1>`します。</span><span class="sxs-lookup"><span data-stu-id="e7580-216">This mapping enables you to represent `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] as `<mcl:MyControl1>`.</span></span>

 <span data-ttu-id="e7580-217">2 つの要素、XAML では、ホスティングを処理します。</span><span class="sxs-lookup"><span data-stu-id="e7580-217">Two elements in the XAML handle the hosting:</span></span>

-   <span data-ttu-id="e7580-218">`WindowsFormsHost` 表す、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素での Windows フォーム コントロールをホストすることができます、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="e7580-218">`WindowsFormsHost` represents the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element that enables you to host a Windows Forms control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

-   <span data-ttu-id="e7580-219">`mcl:MyControl1`を表す`MyControl1`、に追加されます、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素の子のコレクション。</span><span class="sxs-lookup"><span data-stu-id="e7580-219">`mcl:MyControl1`, which represents `MyControl1`, is added to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child collection.</span></span> <span data-ttu-id="e7580-220">一部としてこの Windows フォーム コントロールを表示する結果として、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ウィンドウ、およびするが、アプリケーションからコントロールと通信できます。</span><span class="sxs-lookup"><span data-stu-id="e7580-220">As a result, this Windows Forms control is rendered as part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] window, and you can communicate with the control from the application.</span></span>

### <a name="implementing-the-code-behind-file"></a><span data-ttu-id="e7580-221">分離コード ファイルの実装</span><span class="sxs-lookup"><span data-stu-id="e7580-221">Implementing the Code-Behind File</span></span>
 <span data-ttu-id="e7580-222">MainWindow.xaml.vb または MainWindow.xaml.cs で、分離コード ファイルには機能を実装する手続き型コードが含まれています、[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]前のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="e7580-222">The code-behind file, MainWindow.xaml.vb or MainWindow.xaml.cs, contains the procedural code that implements the functionality of the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] discussed in the preceding section.</span></span> <span data-ttu-id="e7580-223">主な作業は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e7580-223">The primary tasks are:</span></span>

-   <span data-ttu-id="e7580-224">イベント ハンドラーをアタッチする`MyControl1`の`OnButtonClick`イベント。</span><span class="sxs-lookup"><span data-stu-id="e7580-224">Attaching an event handler to `MyControl1`'s `OnButtonClick` event.</span></span>

-   <span data-ttu-id="e7580-225">さまざまなプロパティを変更する`MyControl1`オプション ボタンのコレクションの設定方法に基づいて、します。</span><span class="sxs-lookup"><span data-stu-id="e7580-225">Modifying various properties of `MyControl1`, based on how the collection of option buttons are set.</span></span>

-   <span data-ttu-id="e7580-226">コントロールによって収集されたデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="e7580-226">Displaying the data collected by the control.</span></span>

#### <a name="initializing-the-application"></a><span data-ttu-id="e7580-227">アプリケーションの初期化</span><span class="sxs-lookup"><span data-stu-id="e7580-227">Initializing the Application</span></span>
 <span data-ttu-id="e7580-228">ウィンドウのイベント ハンドラーの初期化コードが含まれている<xref:System.Windows.FrameworkElement.Loaded>イベントをコントロールのイベント ハンドラーをアタッチおよび`OnButtonClick`イベント。</span><span class="sxs-lookup"><span data-stu-id="e7580-228">The initialization code is contained in an event handler for the window's <xref:System.Windows.FrameworkElement.Loaded> event and attaches an event handler to the control's `OnButtonClick` event.</span></span>

 <span data-ttu-id="e7580-229">MainWindow.xaml.vb または MainWindow.xaml.cs で次のコードを追加、`MainWindow`クラス。</span><span class="sxs-lookup"><span data-stu-id="e7580-229">In MainWindow.xaml.vb or MainWindow.xaml.cs, add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 <span data-ttu-id="e7580-230">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]以前に追加した説明`MyControl1`を<xref:System.Windows.Forms.Integration.WindowsFormsHost>キャストする要素の子要素のコレクション、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素の<xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A>への参照を取得する`MyControl1`します。</span><span class="sxs-lookup"><span data-stu-id="e7580-230">Because the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] discussed previously added `MyControl1` to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child element collection, you can cast the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> to get the reference to `MyControl1`.</span></span> <span data-ttu-id="e7580-231">イベント ハンドラーをアタッチするその参照を使用することができますし`OnButtonClick`します。</span><span class="sxs-lookup"><span data-stu-id="e7580-231">You can then use that reference to attach an event handler to `OnButtonClick`.</span></span>

 <span data-ttu-id="e7580-232">コントロール自体への参照を提供するだけでなく<xref:System.Windows.Forms.Integration.WindowsFormsHost>多数のアプリケーションから操作できるコントロールのプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="e7580-232">In addition to providing a reference to the control itself, <xref:System.Windows.Forms.Integration.WindowsFormsHost> exposes a number of the control's properties, which you can manipulate from the application.</span></span> <span data-ttu-id="e7580-233">初期化コードでは、プライベートのグローバル変数を後で、アプリケーションで使用するこれらの値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e7580-233">The initialization code assigns those values to private global variables for later use in the application.</span></span>

 <span data-ttu-id="e7580-234">内の型を簡単にアクセスできるように、 `MyControls` DLL では、次の追加`Imports`または`using`ファイルの先頭にステートメント。</span><span class="sxs-lookup"><span data-stu-id="e7580-234">So that you can easily access the types in the `MyControls` DLL, add the following `Imports` or `using` statement to the top of the file.</span></span>

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a><span data-ttu-id="e7580-235">OnButtonClick のイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="e7580-235">Handling the OnButtonClick Event</span></span>
 <span data-ttu-id="e7580-236">`MyControl1` 発生させる、`OnButtonClick`イベントかのコントロールのボタンをクリックするとします。</span><span class="sxs-lookup"><span data-stu-id="e7580-236">`MyControl1` raises the `OnButtonClick` event when the user clicks either of the control's buttons.</span></span>

 <span data-ttu-id="e7580-237">`MainWindow` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e7580-237">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 <span data-ttu-id="e7580-238">テキスト ボックス内のデータをまとめ、`MyControlEventArgs`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e7580-238">The data in the text boxes is packed into the `MyControlEventArgs` object.</span></span> <span data-ttu-id="e7580-239">ユーザーがクリックした場合、 **OK**ボタン、イベント ハンドラーは、データを抽出し、下のパネルに表示します`MyControl1`。</span><span class="sxs-lookup"><span data-stu-id="e7580-239">If the user clicks the **OK** button, the event handler extracts the data and displays it in the panel below `MyControl1`.</span></span>

#### <a name="modifying-the-controls-properties"></a><span data-ttu-id="e7580-240">コントロールのプロパティの変更</span><span class="sxs-lookup"><span data-stu-id="e7580-240">Modifying the Control’s Properties</span></span>
 <span data-ttu-id="e7580-241"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素がいくつかのホストされるコントロールの既定のプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="e7580-241">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element exposes several of the hosted control's default properties.</span></span> <span data-ttu-id="e7580-242">その結果、アプリケーションのスタイルをより厳密に一致するようにコントロールの外観を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e7580-242">As a result, you can change the appearance of the control to match the style of your application more closely.</span></span> <span data-ttu-id="e7580-243">左側のパネルのオプション ボタンのセットは、いくつかの色とフォントのプロパティを変更するユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e7580-243">The sets of option buttons in the left panel enable the user to modify several color and font properties.</span></span> <span data-ttu-id="e7580-244">ボタンの各セットのハンドラーがある、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベントでは、ユーザーのオプション ボタンの選択を検出し、コントロールに対応するプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="e7580-244">Each set of buttons has a handler for the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which detects the user's option button selections and changes the corresponding property on the control.</span></span>

 <span data-ttu-id="e7580-245">`MainWindow` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e7580-245">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 <span data-ttu-id="e7580-246">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="e7580-246">Build and run the application.</span></span> <span data-ttu-id="e7580-247">Windows フォーム複合コントロールでテキストを追加し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e7580-247">Add some text in the Windows Forms composite control and then click **OK**.</span></span> <span data-ttu-id="e7580-248">そのテキストがラベルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7580-248">The text appears in the labels.</span></span> <span data-ttu-id="e7580-249">コントロールに影響を表示するさまざまなオプション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7580-249">Click the different radio buttons to see the effect on the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7580-250">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7580-250">See also</span></span>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="e7580-251">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="e7580-251">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="e7580-252">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="e7580-252">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="e7580-253">チュートリアル: Windows フォームでの WPF 複合コントロールをホストしています。</span><span class="sxs-lookup"><span data-stu-id="e7580-253">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)

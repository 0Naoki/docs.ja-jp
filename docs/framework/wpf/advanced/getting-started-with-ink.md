---
title: Visual Studio で WPF アプリに InkCanvas を作成します。
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: 600d8528125606c6e1af5b031e2fc31aabb79206
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925045"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="ffbf3-102">WPF のインクを概要します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="ffbf3-103">Windows Presentation Foundation (WPF) が、インク機能を使用するデジタル インクをアプリに組み込むことで簡単です。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ffbf3-104">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ffbf3-104">Prerequisites</span></span>

<span data-ttu-id="ffbf3-105">次の例については、最初に使用する[Microsoft Visual Studio インストール](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-105">To use the following examples, first [install Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span></span> <span data-ttu-id="ffbf3-106">基本的な WPF アプリを記述する方法を理解することもできます。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="ffbf3-107">WPF の概要については、次を参照してください。[チュートリアル: 初めての WPF デスクトップ アプリケーション](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="ffbf3-108">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="ffbf3-108">Quick Start</span></span>

<span data-ttu-id="ffbf3-109">このセクションでは、インクを収集する簡単な WPF アプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="ffbf3-110">インクを入手されましたか。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-110">Got Ink?</span></span>

<span data-ttu-id="ffbf3-111">WPF アプリを作成するには、インクをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="ffbf3-112">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="ffbf3-113">新規作成**WPF アプリ**します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="ffbf3-114">**新しいプロジェクト**ダイアログ ボックスで、展開、**インストール済み** > **Visual c#** または**Visual Basic**  >  **Windows デスクトップ**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="ffbf3-115">次に、選択、 **WPF アプリ (.NET Framework)** アプリ テンプレート。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="ffbf3-116">名前を入力し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="ffbf3-117">Visual Studio は、プロジェクトを作成し、 *MainWindow.xaml*デザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="ffbf3-118">型`<InkCanvas/>`間、`<Grid>`タグ。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![InkCanvas タグを持つ XAML デザイナー](media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="ffbf3-120">キーを押して**F5**デバッガーでアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="ffbf3-121">スタイラス ペンやマウスを使用して、記述**hello world**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="ffbf3-122">インクと同等の 12 のキー操作で"hello world"アプリケーションを記述しました。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="ffbf3-123">アプリを改良します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-123">Spice Up Your App</span></span>

<span data-ttu-id="ffbf3-124">WPF の機能がいくつかの利点を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="ffbf3-125">開始タグと終了の間ですべてのものを置き換える\<ウィンドウ > 次のマークアップ タグ。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

<span data-ttu-id="ffbf3-126">この XAML は、手描き入力サーフェイス グラデーション ブラシのバック グラウンドを作成します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![WPF アプリで画面を手描き入力のグラデーションの色](media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="ffbf3-128">一部の XAML コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="ffbf3-129">XAML を使用する非常に簡単にユーザー インターフェイスをデザイン、現実世界の任意のアプリケーションはイベントを処理するコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="ffbf3-130">マウスから応答を右クリックして、インクにズーム インする簡単な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="ffbf3-131">設定、 `MouseRightButtonUp` XAML 内のハンドラー。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="ffbf3-132">**ソリューション エクスプ ローラー**MainWindow.xaml を展開し、分離コード ファイル (MainWindow.xaml.cs または MainWindow.xaml.vb) を開きます。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="ffbf3-133">次のイベント ハンドラーのコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="ffbf3-134">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-134">Run the application.</span></span> <span data-ttu-id="ffbf3-135">、手描き入力を追加し、マウスで右クリックまたはプレス アンド ホールドに相当するスタイラスを使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="ffbf3-136">マウスの右ボタンをクリックするたびに拡大表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="ffbf3-137">手続き型コードを使用して、XAML ではなく</span><span class="sxs-lookup"><span data-stu-id="ffbf3-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="ffbf3-138">手続き型コードからすべての WPF 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="ffbf3-139">Wpf の XAML をまったく使用しない"こんにちはインク World"アプリケーションを作成する次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="ffbf3-140">Visual Studio で新しいコンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="ffbf3-141">**新しいプロジェクト**ダイアログ ボックスで、展開、**インストール済み** > **Visual c#** または**Visual Basic**  >  **Windows デスクトップ**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="ffbf3-142">次に、選択、**コンソール アプリ (.NET Framework)** アプリ テンプレート。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="ffbf3-143">名前を入力し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="ffbf3-144">次のコードを Program.cs または Program.vb ファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="ffbf3-145">右クリックし、PresentationCore、PresentationFramework、WindowsBase アセンブリへの参照を追加**参照**で**ソリューション エクスプ ローラー**を選択して**参照の追加**.</span><span class="sxs-lookup"><span data-stu-id="ffbf3-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![PresentationCore と PresentationFramework を示す参照マネージャー](media/getting-started-with-ink/references.png)

1. <span data-ttu-id="ffbf3-147">キーを押してアプリケーションをビルド**F5**します。</span><span class="sxs-lookup"><span data-stu-id="ffbf3-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffbf3-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffbf3-148">See Also</span></span>

- [<span data-ttu-id="ffbf3-149">デジタル インク</span><span class="sxs-lookup"><span data-stu-id="ffbf3-149">Digital Ink</span></span>](../../../../docs/framework/wpf/advanced/digital-ink.md)
- [<span data-ttu-id="ffbf3-150">インクの収集</span><span class="sxs-lookup"><span data-stu-id="ffbf3-150">Collecting Ink</span></span>](../../../../docs/framework/wpf/advanced/collecting-ink.md)
- [<span data-ttu-id="ffbf3-151">手書き認識</span><span class="sxs-lookup"><span data-stu-id="ffbf3-151">Handwriting Recognition</span></span>](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)
- [<span data-ttu-id="ffbf3-152">インクの格納</span><span class="sxs-lookup"><span data-stu-id="ffbf3-152">Storing Ink</span></span>](../../../../docs/framework/wpf/advanced/storing-ink.md)

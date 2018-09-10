---
title: 'チュートリアル : WPF での Direct3D9 コンテンツのホスト'
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 5e7edfbeb9a3cddcdcd81d9c87e5e85bfc947339
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44069527"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="a57de-102">チュートリアル : WPF での Direct3D9 コンテンツのホスト</span><span class="sxs-lookup"><span data-stu-id="a57de-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>
<span data-ttu-id="a57de-103">このチュートリアルでは、Windows Presentation Foundation (WPF) アプリケーションでの Direct3D9 コンテンツをホストする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a57de-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="a57de-104">このチュートリアルでは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="a57de-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="a57de-105">Direct3D9 コンテンツをホストする WPF プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a57de-105">Create a WPF project to host the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="a57de-106">Direct3D9 コンテンツをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a57de-106">Import the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="a57de-107">使用しての Direct3D9 コンテンツの表示、<xref:System.Windows.Interop.D3DImage>クラス。</span><span class="sxs-lookup"><span data-stu-id="a57de-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>  
  
 <span data-ttu-id="a57de-108">完了したら、WPF アプリケーションでの Direct3D9 コンテンツをホストする方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="a57de-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a57de-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a57de-109">Prerequisites</span></span>  
 <span data-ttu-id="a57de-110">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="a57de-110">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="a57de-111">。</span><span class="sxs-lookup"><span data-stu-id="a57de-111">.</span></span>  
  
-   <span data-ttu-id="a57de-112">DirectX 9 以降の SDK です。</span><span class="sxs-lookup"><span data-stu-id="a57de-112">DirectX SDK 9 or later.</span></span>  
  
-   <span data-ttu-id="a57de-113">WPF と互換性のある形式での Direct3D9 コンテンツを含む DLL です。</span><span class="sxs-lookup"><span data-stu-id="a57de-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="a57de-114">詳細については、次を参照してください。 [WPF と Direct3D9 の相互運用性](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)と[チュートリアル: WPF でのホストの Direct3D9 のコンテンツを作成する](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)します。</span><span class="sxs-lookup"><span data-stu-id="a57de-114">For more information, see [WPF and Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>  
  
## <a name="creating-the-wpf-project"></a><span data-ttu-id="a57de-115">WPF プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a57de-115">Creating the WPF Project</span></span>  
 <span data-ttu-id="a57de-116">最初の手順では、WPF アプリケーションのプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a57de-116">The first step is to create the project for the WPF application.</span></span>  
  
#### <a name="to-create-the-wpf-project"></a><span data-ttu-id="a57de-117">WPF プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="a57de-117">To create the WPF project</span></span>  
  
-   <span data-ttu-id="a57de-118">新しい WPF アプリケーション プロジェクトを作成するという名前の Visual c# で`D3DHost`します。</span><span class="sxs-lookup"><span data-stu-id="a57de-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="a57de-119">詳細については、次を参照してください。[方法: 新しい WPF アプリケーション プロジェクトを作成する](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)します。</span><span class="sxs-lookup"><span data-stu-id="a57de-119">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
     <span data-ttu-id="a57de-120">MainWindow.xaml を開きます、[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a57de-120">MainWindow.xaml opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="a57de-121">Direct3D9 コンテンツのインポート</span><span class="sxs-lookup"><span data-stu-id="a57de-121">Importing the Direct3D9 Content</span></span>  
 <span data-ttu-id="a57de-122">使用してアンマネージ DLL から Direct3D9 コンテンツをインポートする、`DllImport`属性。</span><span class="sxs-lookup"><span data-stu-id="a57de-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>  
  
#### <a name="to-import-direct3d9-content"></a><span data-ttu-id="a57de-123">Direct3D9 コンテンツをインポートするには</span><span class="sxs-lookup"><span data-stu-id="a57de-123">To import Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="a57de-124">コード エディターでの MainWindow.xaml.cs を開きます。</span><span class="sxs-lookup"><span data-stu-id="a57de-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2.  <span data-ttu-id="a57de-125">自動的に生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a57de-125">Replace the automatically generated code with the following code.</span></span>  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="a57de-126">Direct3D9 コンテンツのホスト</span><span class="sxs-lookup"><span data-stu-id="a57de-126">Hosting the Direct3D9 Content</span></span>  
 <span data-ttu-id="a57de-127">最後に、使用して、 <xref:System.Windows.Interop.D3DImage> Direct3D9 コンテンツをホストするクラス。</span><span class="sxs-lookup"><span data-stu-id="a57de-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>  
  
#### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="a57de-128">Direct3D9 コンテンツをホストするには</span><span class="sxs-lookup"><span data-stu-id="a57de-128">To host the Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="a57de-129">MainWindow.xaml で、自動的に生成された XAML を次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a57de-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  <span data-ttu-id="a57de-130">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="a57de-130">Build the project.</span></span>  
  
3.  <span data-ttu-id="a57de-131">Bin/debug フォルダーに Direct3D9 コンテンツを含んでいる DLL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="a57de-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>  
  
4.  <span data-ttu-id="a57de-132">F5 キーを押してプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="a57de-132">Press F5 to run the project.</span></span>  
  
     <span data-ttu-id="a57de-133">WPF アプリケーション内での Direct3D9 コンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a57de-133">The Direct3D9 content appears within the WPF application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a57de-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="a57de-134">See Also</span></span>  
 <xref:System.Windows.Interop.D3DImage>  
 [<span data-ttu-id="a57de-135">Direct3D9 および WPF の相互運用性のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="a57de-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)

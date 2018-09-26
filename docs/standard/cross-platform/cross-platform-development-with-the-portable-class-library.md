---
title: 汎用性のあるクラス ライブラリを使用したプラットフォーム間の開発
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
author: mairaw
ms.author: mairaw
ms.openlocfilehash: afaa8e118bb21e5c1e4f1c53b1d0d29ca6bb3bf5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47172707"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a><span data-ttu-id="31315-102">ポータブル クラス ライブラリを使用したクロス プラットフォーム開発</span><span class="sxs-lookup"><span data-stu-id="31315-102">Cross-platform development with the Portable Class Library</span></span>

<span data-ttu-id="31315-103">Visual Studio でポータブル クラス ライブラリ プロジェクトの種類を使用して、迅速かつ簡単に、クロス プラットフォーム アプリとライブラリの Microsoft プラットフォームを構築できます。</span><span class="sxs-lookup"><span data-stu-id="31315-103">The Portable Class Library project type in Visual Studio helps you build cross-platform apps and libraries for Microsoft platforms quickly and easily.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

<span data-ttu-id="31315-104">ポータブル クラス ライブラリにより、コードの開発とテストにかかる時間とコストを削減できます。</span><span class="sxs-lookup"><span data-stu-id="31315-104">Portable class libraries can help you reduce the time and costs of developing and testing code.</span></span> <span data-ttu-id="31315-105">このプロジェクトの種類を使用して、書き込みし、ポータブルの .NET Framework アセンブリをビルドし、.NET Framework、iOS、またはファルダなどの複数のプラットフォームを対象とするアプリからこれらのアセンブリを参照</span><span class="sxs-lookup"><span data-stu-id="31315-105">Use this project type to write and build portable .NET Framework assemblies, and then reference those assemblies from apps that target multiple platforms such as the .NET Framework, iOS, or Mac.</span></span>

<span data-ttu-id="31315-106">Visual Studio でポータブル クラス ライブラリ プロジェクトを作成し、プロジェクトの開発を開始した後でも、ターゲット プラットフォームを変更できます。</span><span class="sxs-lookup"><span data-stu-id="31315-106">Even after you create a Portable Class Library project in Visual Studio and start developing it, you can change the target platforms.</span></span> <span data-ttu-id="31315-107">Visual Studio では、コードにする必要がある変更の特定に役立てることにより、新しいアセンブリでは、ライブラリをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="31315-107">Visual Studio compiles your library with the new assemblies, which helps you identify the changes you need to make in your code.</span></span>

## <a name="create-a-portable-class-library-project"></a><span data-ttu-id="31315-108">ポータブル クラス ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="31315-108">Create a Portable Class Library project</span></span>

<span data-ttu-id="31315-109">ポータブル クラス ライブラリを作成するには、Visual Studio で提供されているテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="31315-109">To create a Portable Class Library, use the template provided in Visual Studio.</span></span> <span data-ttu-id="31315-110">新しいプロジェクトを作成 (**ファイル** > **新しいプロジェクト**)、および、**新しいプロジェクト** ダイアログ ボックスを使用するプログラミング言語 (Visual c# または Visual Basic) を選択します。</span><span class="sxs-lookup"><span data-stu-id="31315-110">Create a new project (**File** > **New Project**), and in the **New Project** dialog box, select your programming language (Visual C# or Visual Basic).</span></span> <span data-ttu-id="31315-111">次に、選択、**クラス ライブラリ (レガシ ポータブル)** テンプレート。</span><span class="sxs-lookup"><span data-stu-id="31315-111">Then, select the **Class Library (Legacy Portable)** template.</span></span> <span data-ttu-id="31315-112">プロジェクトの名前を入力し、選択**OK**します。</span><span class="sxs-lookup"><span data-stu-id="31315-112">Enter a name for your project and choose **OK**.</span></span>

<span data-ttu-id="31315-113">**ポータブル クラス ライブラリの追加** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="31315-113">The **Add Portable Class Library** dialog box appears.</span></span> <span data-ttu-id="31315-114">2 つ以上のターゲットを選択し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="31315-114">Choose two or more targets, and then choose **OK**.</span></span>

![Visual Studio でのポータブル クラス ライブラリのターゲットを追加します。](media/add-portable-class-library.png)

## <a name="change-targets"></a><span data-ttu-id="31315-116">ターゲットを変更します。</span><span class="sxs-lookup"><span data-stu-id="31315-116">Change targets</span></span>

<span data-ttu-id="31315-117">作成するときに、または開発を開始した後は、ポータブル クラス ライブラリ プロジェクトのターゲット プラットフォームを変更できます。</span><span class="sxs-lookup"><span data-stu-id="31315-117">You can change the target platforms of a portable class library project when you create it or after you’ve started development.</span></span> <span data-ttu-id="31315-118">プロジェクトを作成した後、ターゲットを変更したい場合**ソリューション エクスプ ローラー**(ソリューションではなく)、ポータブル クラス ライブラリ プロジェクトのショートカット メニューを開き、選択し、**プロパティ**.</span><span class="sxs-lookup"><span data-stu-id="31315-118">If you want to change the targets after you’ve created your project, in **Solution Explorer**, open the shortcut menu for your Portable Class Library project (not the solution), and then choose **Properties**.</span></span> <span data-ttu-id="31315-119">プロジェクトのプロパティ ページ、**ライブラリ** タブは、プロジェクトが現在対象とするプラットフォームを示します。</span><span class="sxs-lookup"><span data-stu-id="31315-119">On the project properties page, the **Library** tab shows the platforms that your project currently targets.</span></span>

![Visual Studio でポータブル クラス ライブラリのプロジェクトのプロパティ](media/pcl-project-properties.png)

<span data-ttu-id="31315-121">追加またはターゲットの削除、選択、**変更** ボタンを選択して、該当するチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="31315-121">To add or remove targets, choose the **Change** button, and then select and clear the appropriate check boxes.</span></span>

<span data-ttu-id="31315-122">ターゲットを変更すると、変更後のターゲットに合わせて、プロジェクトの開発に使用できる API が変更されます。</span><span class="sxs-lookup"><span data-stu-id="31315-122">When you change the targets, the APIs that are available to you for developing your project will change to match your selection.</span></span> <span data-ttu-id="31315-123">Visual Studio は、ターゲットを変更したことで発生する可能性があるエラーと警告を報告します。</span><span class="sxs-lookup"><span data-stu-id="31315-123">Visual Studio reports the errors and warnings that may occur as a result of the targets changing.</span></span>

<span data-ttu-id="31315-124">Visual Studio で変更を加える前に、アセンブリの移植性を評価する場合は、使用することができます、 [.NET Portability Analyzer](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)します。</span><span class="sxs-lookup"><span data-stu-id="31315-124">If you want to evaluate the portability of your assemblies before you make changes in Visual Studio, you can use the [.NET Portability Analyzer](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b).</span></span>

## <a name="supported-types-and-members"></a><span data-ttu-id="31315-125">サポートされている型とメンバー</span><span class="sxs-lookup"><span data-stu-id="31315-125">Supported types and members</span></span>

<span data-ttu-id="31315-126">ポータブル クラス ライブラリのプロジェクトで使用できる型とメンバーは、互換性に関するいくつかの要因による制約を受けます。</span><span class="sxs-lookup"><span data-stu-id="31315-126">The types and members that are available in Portable Class Library projects are constrained by several compatibility factors:</span></span>

-   <span data-ttu-id="31315-127">選択したターゲット間で共有される必要があります。</span><span class="sxs-lookup"><span data-stu-id="31315-127">They must be shared across the targets you selected.</span></span>

-   <span data-ttu-id="31315-128">それらのターゲット間で同様に動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31315-128">The must behave similarly across those targets.</span></span>

-   <span data-ttu-id="31315-129">廃止候補であってはなりません。</span><span class="sxs-lookup"><span data-stu-id="31315-129">They must not be candidates for deprecation.</span></span>

-   <span data-ttu-id="31315-130">特にサポートしているメンバーがポータブルでない場合は、ポータブルな環境に意味がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="31315-130">They must make sense in a portable environment, especially when supporting members are not portable.</span></span>

<span data-ttu-id="31315-131">メンバーがポータブル クラス ライブラリでサポートされており、選択したターゲットのメンバーである場合、IntelliSense でプロジェクトにこのメンバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="31315-131">If a member is supported in the Portable Class Library and for your selected targets, it will appear in your project in IntelliSense.</span></span> <span data-ttu-id="31315-132">ただし、API がポータブル クラス ライブラリでサポートされている可能性があります。API を使用できるかどうかは、選択したターゲットによって異なります。</span><span class="sxs-lookup"><span data-stu-id="31315-132">However, remember that an API may be supported in the Portable Class Library, but whether you can use the API depends on the targets you select.</span></span>

## <a name="api-differences-in-the-portable-class-library"></a><span data-ttu-id="31315-133">ポータブル クラス ライブラリでの API の相違点</span><span class="sxs-lookup"><span data-stu-id="31315-133">API differences in the Portable Class Library</span></span>

<span data-ttu-id="31315-134">サポートされるすべてのプラットフォームでポータブル クラス ライブラリ アセンブリの互換性を確保するために、ポータブル クラス ライブラリでは一部のメンバーが若干変更されています。</span><span class="sxs-lookup"><span data-stu-id="31315-134">To make Portable Class Library assemblies compatible across all supported platforms, some members have been slightly changed in the Portable Class Library.</span></span>

## <a name="use-the-portable-class-library"></a><span data-ttu-id="31315-135">ポータブル クラス ライブラリを使用します。</span><span class="sxs-lookup"><span data-stu-id="31315-135">Use the Portable Class Library</span></span>

<span data-ttu-id="31315-136">ポータブル クラス ライブラリ プロジェクトをビルドしたら、他のプロジェクトからそのプロジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="31315-136">After you build your Portable Class Library project, you just reference it from other projects.</span></span> <span data-ttu-id="31315-137">プロジェクトを参照することも、アクセスする必要のあるクラスを含む特定のアセンブリを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="31315-137">You can reference either the project or specific assemblies that contain the classes you want to access.</span></span>

<span data-ttu-id="31315-138">ポータブル クラス ライブラリ アセンブリを参照するアプリを実行するには、ターゲット プラットフォームの必要なバージョン (またはそれ以上のバージョン) がコンピューターにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="31315-138">To run an app that references a Portable Class Library assembly, the required version (or later) of the targeted platforms must be installed on your computer.</span></span> <span data-ttu-id="31315-139">Visual Studio には必要なすべてのフレームワークが含まれるため、さらに変更を加えることなく、アプリケーションの開発に使用したコンピューターでアプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="31315-139">Visual Studio contains all the required frameworks, so you can run the app without further modification on the computer that you used to develop the app.</span></span>

### <a name="deploy-a-universal-windows-app"></a><span data-ttu-id="31315-140">ユニバーサル Windows アプリをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="31315-140">Deploy a Universal Windows app</span></span>

<span data-ttu-id="31315-141">ユニバーサル Windows アプリを作成するときに、ポータブル クラス ライブラリ アセンブリを参照して、アプリ パッケージに含まれているアプリを展開する必要があるすべてが以降の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="31315-141">When you create a Universal Windows app that references a Portable Class Library assembly, everything you need to deploy the app is included in the app package, and no further steps are required.</span></span>

### <a name="deploy-a-net-framework-app"></a><span data-ttu-id="31315-142">デプロイを .NET Framework アプリ</span><span class="sxs-lookup"><span data-stu-id="31315-142">Deploy a .NET Framework app</span></span>

<span data-ttu-id="31315-143">ポータブル クラス ライブラリ アセンブリを参照する .NET Framework アプリを配置するときは、.NET Framework の正しいバージョンに対する依存関係を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31315-143">When you deploy a .NET Framework app that references a Portable Class Library assembly, you must specify a dependency on the correct version of the .NET Framework.</span></span> <span data-ttu-id="31315-144">この依存関係を指定することで、必要なバージョンがアプリケーションと共に確実にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="31315-144">By specifying this dependency, you ensure that the required version is installed with your app.</span></span>

-   <span data-ttu-id="31315-145">ClickOnce 配置で依存関係を作成する: で**ソリューション エクスプ ローラー**、発行するプロジェクトのプロジェクト ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="31315-145">To create a dependency with ClickOnce deployment: In **Solution Explorer**, choose the project node for the project you want to publish.</span></span> <span data-ttu-id="31315-146">(これは、ポータブル クラス ライブラリ プロジェクトを参照するプロジェクトです。)メニュー バーで、**プロジェクト** > **プロパティ**を選択し、**発行**タブ。**発行**ページで、選択**の前提条件**します。</span><span class="sxs-lookup"><span data-stu-id="31315-146">(This is the project that references the Portable Class Library project.) On the menu bar, choose **Project** > **Properties**, and then choose the **Publish** tab. On the **Publish** page, choose **Prerequisites**.</span></span> <span data-ttu-id="31315-147">必須コンポーネントとして、必要な .NET Framework のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="31315-147">Select the required .NET Framework version as a prerequisite.</span></span>

-   <span data-ttu-id="31315-148">セットアップ プロジェクトの依存関係を作成する: で**ソリューション エクスプ ローラー**、セットアップ プロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="31315-148">To create a dependency with a setup project: In **Solution Explorer**, choose the setup project.</span></span> <span data-ttu-id="31315-149">メニュー バーで、**プロジェクト** > **プロパティ** > **の前提条件**します。</span><span class="sxs-lookup"><span data-stu-id="31315-149">On the menu bar, choose **Project** > **Properties** > **Prerequisites**.</span></span> <span data-ttu-id="31315-150">必須コンポーネントとして、必要な .NET Framework のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="31315-150">Select the required .NET Framework version as a prerequisite.</span></span>

<span data-ttu-id="31315-151">.NET Framework アプリの展開についての詳細については、次を参照してください。[開発者向け配置ガイド](../../../docs/framework/deployment/deployment-guide-for-developers.md)します。</span><span class="sxs-lookup"><span data-stu-id="31315-151">For more information about deploying .NET Framework apps, see [Deployment Guide for Developers](../../../docs/framework/deployment/deployment-guide-for-developers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="31315-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="31315-152">See also</span></span>

- [<span data-ttu-id="31315-153">MVVM を利用した汎用性のあるクラス ライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="31315-153">Using Portable Class Library with MVVM</span></span>](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md)
- [<span data-ttu-id="31315-154">複数のプラットフォームを対象とするライブラリのアプリケーション リソース</span><span class="sxs-lookup"><span data-stu-id="31315-154">App Resources for Libraries That Target Multiple Platforms</span></span>](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md)
- [<span data-ttu-id="31315-155">.NET portability Analyzer</span><span class="sxs-lookup"><span data-stu-id="31315-155">.NET Portability Analyzer</span></span>](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [<span data-ttu-id="31315-156">Windows ストア アプリおよび Windows ランタイムのための .NET Framework サポート</span><span class="sxs-lookup"><span data-stu-id="31315-156">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
- [<span data-ttu-id="31315-157">配置</span><span class="sxs-lookup"><span data-stu-id="31315-157">Deployment</span></span>](../../../docs/framework/deployment/net-framework-applications.md)

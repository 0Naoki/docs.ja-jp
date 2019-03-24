---
title: .NET Framework および .NET Core のプロジェクトを整理する
description: プロジェクト所有者が横並びの .NET Framework と .NET Core に対してソリューションをコンパイルするときに役立ちます。
author: conniey
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: ab484ccc2c5b51b2ee1dca57df51669d288f3e6b
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58186066"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a><span data-ttu-id="73f03-103">.NET Framework と .NET Core の両方をサポートするようにプロジェクトを整理する</span><span class="sxs-lookup"><span data-stu-id="73f03-103">Organize your project to support both .NET Framework and .NET Core</span></span>

<span data-ttu-id="73f03-104">.NET Framework と .NET Core 両方のコンパイルに同時に対応するソリューションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="73f03-104">Learn how to create a solution that compiles for both .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="73f03-105">この目標を達成できるようにプロジェクトを整理するいくつかのオプションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73f03-105">See several options to organize projects to help you achieve this goal.</span></span> <span data-ttu-id="73f03-106">ここでは、.NET Core でプロジェクト レイアウトを設定する方法について決定するときに考慮する典型的なシナリオを紹介します。</span><span class="sxs-lookup"><span data-stu-id="73f03-106">Here are some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="73f03-107">この一覧はプロジェクトのニーズに基づいて選択されており、すべてを網羅しるわけではりません。</span><span class="sxs-lookup"><span data-stu-id="73f03-107">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

* [<span data-ttu-id="73f03-108">**既存のプロジェクトと .NET Core プロジェクトを結合し、シングル プロジェクトを作成する**</span><span class="sxs-lookup"><span data-stu-id="73f03-108">**Combine existing projects and .NET Core projects into single projects**</span></span>](#replace-existing-projects-with-a-multi-targeted-net-core-project)

  <span data-ttu-id="73f03-109">*効果:*</span><span class="sxs-lookup"><span data-stu-id="73f03-109">*What this is good for:*</span></span>
  * <span data-ttu-id="73f03-110">複数のプロジェクトをコンパイルするのではなく、シングル プロジェクトをコンパイルすることでビルド プロセスをシンプルにします。それぞれ、異なる .NET Framework バージョンまたはプラットフォームをターゲットにします。</span><span class="sxs-lookup"><span data-stu-id="73f03-110">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  * <span data-ttu-id="73f03-111">ターゲットが複数のプロジェクトのソース ファイル管理をシンプルにします。シングル プロジェクト ファイルを管理することになります。</span><span class="sxs-lookup"><span data-stu-id="73f03-111">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="73f03-112">ソース ファイルの追加/削除時、代替方法では、これらを他のプロジェクトと手動で同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73f03-112">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  * <span data-ttu-id="73f03-113">使用する NuGet パッケージを簡単に生成します。</span><span class="sxs-lookup"><span data-stu-id="73f03-113">Easily generating a NuGet package for consumption.</span></span>
  * <span data-ttu-id="73f03-114">コンパイラ ディレクティブを利用することで、ライブラリの特定の .NET Framework バージョンに対してコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="73f03-114">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="73f03-115">*サポートされていないシナリオ:*</span><span class="sxs-lookup"><span data-stu-id="73f03-115">*Unsupported scenarios:*</span></span>
  * <span data-ttu-id="73f03-116">既存のプロジェクトを開くには、開発者が Visual Studio 2017 を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="73f03-116">Requires developers to use Visual Studio 2017 to open existing projects.</span></span> <span data-ttu-id="73f03-117">旧バージョンの Visual Studio をサポートするには、[プロジェクト ファイルを異なるフォルダーで保持する](#support-vs)ことが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="73f03-117">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

* <a name="support-vs"></a><span data-ttu-id="73f03-118">[**既存のプロジェクトと新しい .NET Core プロジェクトを別々に保存する**](#keep-existing-projects-and-create-a-net-core-project)</span><span class="sxs-lookup"><span data-stu-id="73f03-118">[**Keep existing projects and new .NET Core projects separate**](#keep-existing-projects-and-create-a-net-core-project)</span></span>

  <span data-ttu-id="73f03-119">*効果:*</span><span class="sxs-lookup"><span data-stu-id="73f03-119">*What this is good for:*</span></span>
  * <span data-ttu-id="73f03-120">既存のプロジェクトで引き続き開発をサポートします。Visual Studio 2017 を所有していない開発者/貢献者はアップグレードする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="73f03-120">Continuing to support development on existing projects without having to upgrade for developers/contributors who may not have Visual Studio 2017.</span></span>
  * <span data-ttu-id="73f03-121">既存のプロジェクトで新しいバグが発生する可能性が減ります。既存のプロジェクトではコード チャーンが要求されないためです。</span><span class="sxs-lookup"><span data-stu-id="73f03-121">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="73f03-122">例</span><span class="sxs-lookup"><span data-stu-id="73f03-122">Example</span></span>

<span data-ttu-id="73f03-123">次のリポジトリを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="73f03-123">Consider the repository below:</span></span>

![既存のプロジェクト](./media/project-structure/existing-project-structure.png)

[<span data-ttu-id="73f03-125">**ソース コード**</span><span class="sxs-lookup"><span data-stu-id="73f03-125">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/)

<span data-ttu-id="73f03-126">下に説明する既存のプロジェクトの制約や複雑性にもよりますが、このリポジトリのために .NET Core のサポートを追加する方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="73f03-126">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="73f03-127">既存のプロジェクトとターゲットが複数ある .NET Core Project を置換します</span><span class="sxs-lookup"><span data-stu-id="73f03-127">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="73f03-128">リポジトリを再整理できます。既存の *\*.csproj* ファイルが削除され、複数のフレームワークをターゲットにするシングル *\*.csproj* ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="73f03-128">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="73f03-129">異なるフレームワークに対してシングル プロジェクトでコンパイルできるので、この方法が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="73f03-129">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="73f03-130">さまざまなコンパイル オプション、ターゲットにするフレームワークごとの依存関係などを処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="73f03-130">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

![複数のフレームワークをターゲットにする csproj の作成](./media/project-structure/multi-targeted-project.png)

[<span data-ttu-id="73f03-132">**ソース コード**</span><span class="sxs-lookup"><span data-stu-id="73f03-132">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/)

<span data-ttu-id="73f03-133">注目するべき変更点:</span><span class="sxs-lookup"><span data-stu-id="73f03-133">Changes to note are:</span></span>

* <span data-ttu-id="73f03-134">*packages.config* と *\*.csproj* が新しい [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj) に置き換わりました。</span><span class="sxs-lookup"><span data-stu-id="73f03-134">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj).</span></span> <span data-ttu-id="73f03-135">NuGet パッケージが `<PackageReference> ItemGroup` で指定されています。</span><span class="sxs-lookup"><span data-stu-id="73f03-135">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="73f03-136">既存のプロジェクトを保持し、.NET Core プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="73f03-136">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="73f03-137">古いフレームワークをターゲットにする既存のプロジェクトがあるとき、そのようなプロジェクトをそのまま残し、.NET Core プロジェクトを利用して今後のフレームワークをターゲットにすると効率的な場合があります。</span><span class="sxs-lookup"><span data-stu-id="73f03-137">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

![別のフォルダーに既存のプロジェクトがある .NET Core プロジェクト](./media/project-structure/separate-projects-same-source.png)

[<span data-ttu-id="73f03-139">**ソース コード**</span><span class="sxs-lookup"><span data-stu-id="73f03-139">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/)

<span data-ttu-id="73f03-140">注目するべき変更点:</span><span class="sxs-lookup"><span data-stu-id="73f03-140">Changes to note are:</span></span>

* <span data-ttu-id="73f03-141">.NET Core と既存のプロジェクトを別々のフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="73f03-141">The .NET Core and existing projects are kept in separate folders.</span></span>
  * <span data-ttu-id="73f03-142">プロジェクトを別々のフォルダーに保存すれば、Visual Studio 2017 を所有する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="73f03-142">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017.</span></span> <span data-ttu-id="73f03-143">古いプロジェクトだけを開く別個のソリューションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="73f03-143">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="73f03-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="73f03-144">See also</span></span>

<span data-ttu-id="73f03-145">.NET Core に移行する方法の詳細なガイダンスについては、[.NET Core の移植に関するドキュメント](index.md)のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73f03-145">Please see the [.NET Core porting documentation](index.md) for more guidance on migrating to .NET Core.</span></span>

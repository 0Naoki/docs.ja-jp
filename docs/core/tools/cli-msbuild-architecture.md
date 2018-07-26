---
title: .NET Core コマンドライン ツールのアーキテクチャ
description: .NET Core ツール レイヤーと最近のバージョンの変更内容について説明します。
author: blackdwarf
ms.date: 03/06/2017
ms.openlocfilehash: 1d96a0b1e19bf84af0ab645ebd104afc899ae656
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245130"
---
# <a name="high-level-overview-of-changes-in-the-net-core-tools"></a><span data-ttu-id="58256-103">.NET Core ツールの変更の概要</span><span class="sxs-lookup"><span data-stu-id="58256-103">High-level overview of changes in the .NET Core tools</span></span>

<span data-ttu-id="58256-104">このドキュメントでは、*project.json* から MSBuild への移行に関連する変更について、および *csproj* プロジェクト システムについて、.NET Core ツールのレイヤー化と CLI コマンド実装の変更に関する情報と共に説明します。</span><span class="sxs-lookup"><span data-stu-id="58256-104">This document describes the changes associated with moving from *project.json* to MSBuild and the *csproj* project system with information on the changes to the layering of the .NET Core tooling and the implementation of the CLI commands.</span></span> <span data-ttu-id="58256-105">これらの変更は、2017 年 3 月 7 日の .NET Core SDK 1.0 および Visual Studio 2017 のリリース ([アナウンス](https://blogs.msdn.microsoft.com/dotnet/2017/03/07/announcing-net-core-tools-1-0/)をご覧ください) に伴って発生しましたが、.NET Core SDK Preview 3 のリリースで初めて実装されました。</span><span class="sxs-lookup"><span data-stu-id="58256-105">These changes occurred with the release of .NET Core SDK 1.0 and Visual Studio 2017 on March 7, 2017 (see the [announcement](https://blogs.msdn.microsoft.com/dotnet/2017/03/07/announcing-net-core-tools-1-0/)) but were initially implemented with the release of the .NET Core SDK Preview 3.</span></span>

## <a name="moving-away-from-projectjson"></a><span data-ttu-id="58256-106">project.json から移行する</span><span class="sxs-lookup"><span data-stu-id="58256-106">Moving away from project.json</span></span>
<span data-ttu-id="58256-107">.NET Core のツールの最大の違いは、プロジェクト システムが [project.json から csproj に移行](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/)されることです。</span><span class="sxs-lookup"><span data-stu-id="58256-107">The biggest change in the tooling for .NET Core is certainly the [move away from project.json to csproj](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) as the project system.</span></span> <span data-ttu-id="58256-108">最新バージョンのコマンドライン ツールは *project.json* ファイルをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="58256-108">The latest versions of the command-line tools don't support *project.json* files.</span></span> <span data-ttu-id="58256-109">これは、project.json を使用してアプリケーションやライブラリを構築、実行、発行できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="58256-109">That means that it cannot be used to build, run or publish project.json based applications and libraries.</span></span> <span data-ttu-id="58256-110">このバージョンのツールを使用するには、既存のプロジェクトを移行するか、新規に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58256-110">In order to use this version of the tools, you will need to migrate your existing projects or start new ones.</span></span> 

<span data-ttu-id="58256-111">この移行の一環として、project.json プロジェクトの構築用に開発されたカスタム ビルド エンジンが、[MSBuild](https://github.com/Microsoft/msbuild) と呼ばれる、成熟した完全な機能を持つビルド エンジンに置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="58256-111">As part of this move, the custom build engine that was developed to build project.json projects was replaced with a mature and fully capable build engine called [MSBuild](https://github.com/Microsoft/msbuild).</span></span> <span data-ttu-id="58256-112">MSBuild は、プラットフォームの最初のリリース以来重要なテクノロジとなっているエンジンで、.NET コミュニティでは広く知られています。</span><span class="sxs-lookup"><span data-stu-id="58256-112">MSBuild is a well-known engine in the .NET community, since it has been a key technology since the platform's first release.</span></span> <span data-ttu-id="58256-113">MSBuild では .NET Core アプリケーションを構築するので、もちろん .NET Core に移植され、.NET Core を実行するすべてのプラットフォームで使用できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="58256-113">Of course, because it needs to build .NET Core applications, MSBuild has been ported to .NET Core and can be used on any platform that .NET Core runs on.</span></span> <span data-ttu-id="58256-114">.NET Core の最大の保証の 1 つは、これがクロスプラット フォームの開発スタックであるということです。この動きによってこれは保証され続けるように努めました。</span><span class="sxs-lookup"><span data-stu-id="58256-114">One of the main promises of .NET Core is that of a cross-platform development stack, and we have made sure that this move does not break that promise.</span></span>

> [!NOTE]
> <span data-ttu-id="58256-115">MSBuild を初めて使用する際に詳細を学習するには、まず、「[MSBuild の概念](/visualstudio/msbuild/msbuild-concepts)」という記事をお読みください。</span><span class="sxs-lookup"><span data-stu-id="58256-115">If you are new to MSBuild and would like to learn more about it, you can start by reading the [MSBuild Concepts](/visualstudio/msbuild/msbuild-concepts) article.</span></span> 

## <a name="the-tooling-layers"></a><span data-ttu-id="58256-116">ツールの階層</span><span class="sxs-lookup"><span data-stu-id="58256-116">The tooling layers</span></span>
<span data-ttu-id="58256-117">既存のプロジェクト システムとビルド エンジンが切り替わるにあたり、これらの変更によって .NET Core ツールのエコシステム全体の "レイヤー" には全体的な変更があるのかという疑問が当然生じると思います。</span><span class="sxs-lookup"><span data-stu-id="58256-117">With the move away from the existing project system as well as with building engine switches, the question that naturally follows is do any of these changes change the overall "layering" of the whole .NET Core tooling ecosystem?</span></span> <span data-ttu-id="58256-118">小さなものからコンポーネントまで、新しいものはありますか?</span><span class="sxs-lookup"><span data-stu-id="58256-118">Are there new bits and components?</span></span>

<span data-ttu-id="58256-119">次の図で Preview 2 のレイヤーを簡単に再確認してみましょう。</span><span class="sxs-lookup"><span data-stu-id="58256-119">Let's start with a quick refresher on Preview 2 layering as shown in the following picture:</span></span>

![Preview 2 のツールの概要](media/cli-msbuild-architecture/p2-arch.png)

<span data-ttu-id="58256-121">ツールのレイヤーはかなり単純です。</span><span class="sxs-lookup"><span data-stu-id="58256-121">The layering of the tools is quite simple.</span></span> <span data-ttu-id="58256-122">最下層には .NET Core のコマンド ライン ツールが基礎としてあります。</span><span class="sxs-lookup"><span data-stu-id="58256-122">At the bottom we have the .NET Core Command Line tools as a foundation.</span></span> <span data-ttu-id="58256-123">Visual Studio または Visual Studio コードなどのその他のすべての上位レベルのツールは、プロジェクトの構築、依存関係の復元に CLI に依存します。</span><span class="sxs-lookup"><span data-stu-id="58256-123">All other, higher-level tools such as Visual Studio or Visual Studio Code, depend and rely on the CLI to build projects, restore dependencies and so on.</span></span> <span data-ttu-id="58256-124">これは、たとえば Visual Studio が復元操作を行う場合、CLI の `dotnet restore` ([注を参照](#dotnet-restore-note)) コマンドが呼び出されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="58256-124">This meant that, for example, if Visual Studio wanted to perform a restore operation, it would call into `dotnet restore` ([see note](#dotnet-restore-note)) command in the CLI.</span></span> 

<span data-ttu-id="58256-125">新しいプロジェクト システムに移行すると、前の図は以下のように変わります。</span><span class="sxs-lookup"><span data-stu-id="58256-125">With the move to the new project system, the previous diagram changes:</span></span> 

![.NET Core SDK 1.0.0 のアーキテクチャの概要](media/cli-msbuild-architecture/p3-arch.png)

<span data-ttu-id="58256-127">主な違いは、CLI が基本的なレイヤーではなくなり、この役割が "共有 SDK コンポーネント" に置き換えられたことです。</span><span class="sxs-lookup"><span data-stu-id="58256-127">The main difference is that the CLI is not the foundational layer anymore; this role is now filled by the "shared SDK component".</span></span> <span data-ttu-id="58256-128">この共有 SDK コンポーネントとは、一連のターゲットとそれに関連付けられている、コードのコンパイル、その発行、NuGet パッケージの作成などを担当するタスクです。SDK 自体はオープン ソースであり、GitHub の [SDK リポジトリ](https://github.com/dotnet/sdk)から入手できます。</span><span class="sxs-lookup"><span data-stu-id="58256-128">This shared SDK component is a set of targets and associated tasks that are responsible for compiling your code, publishing it, packing NuGet packages etc. The SDK itself is open-source and is available on GitHub on the [SDK repo](https://github.com/dotnet/sdk).</span></span> 

> [!NOTE]
> <span data-ttu-id="58256-129">"ターゲット" とは、MSBuild が呼び出すことのできる名前付きの操作を意味する MSBuild の用語です。</span><span class="sxs-lookup"><span data-stu-id="58256-129">A "target" is a MSBuild term that indicates a named operation that MSBuild can invoke.</span></span> <span data-ttu-id="58256-130">これは、通常ターゲットが行うことを期待されているいくつかのロジックを実行する 1 つ以上のタスクと連結されています。</span><span class="sxs-lookup"><span data-stu-id="58256-130">It is usually coupled with one or more tasks that execute some logic that the target is supposed to do.</span></span> <span data-ttu-id="58256-131">MSBuild では、`Copy` や `Execute` などの多数の既製ターゲットをサポートしています。また、ユーザーがマネージド コードを使用して、独自のタスクを記述し、それらのタスクをターゲットに実行させるよう定義することも可能です。</span><span class="sxs-lookup"><span data-stu-id="58256-131">MSBuild supports many ready-made targets such as `Copy` or `Execute`; it also allows users to write their own tasks using managed code and define targets to execute those tasks.</span></span> <span data-ttu-id="58256-132">詳細については、「[MSBuild タスク](/visualstudio/msbuild/msbuild-tasks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58256-132">For more information, see [MSBuild tasks](/visualstudio/msbuild/msbuild-tasks).</span></span> 

<span data-ttu-id="58256-133">すべてのツールセットは、CLI を含む、共有 SDK コンポーネントとそのターゲットを消費します。</span><span class="sxs-lookup"><span data-stu-id="58256-133">All the toolsets now consume the shared SDK component and its targets, CLI included.</span></span> <span data-ttu-id="58256-134">たとえば、Visual Studio の次のバージョンでは .NET Core プロジェクトの依存関係の復元に `dotnet restore` ([注を参照](#dotnet-restore-note)) コマンドを呼び出しません。直接 "Restore" ターゲットを使用します。</span><span class="sxs-lookup"><span data-stu-id="58256-134">For example, the next version of Visual Studio will not call into `dotnet restore` ([see note](#dotnet-restore-note)) command to restore dependencies for .NET Core projects, it will use the "Restore" target directly.</span></span> <span data-ttu-id="58256-135">これらは MSBuild のターゲットであるため、これらの実行に未加工の MSBuild の [dotnet msbuild](dotnet-msbuild.md) コマンドを使用することも可能です。</span><span class="sxs-lookup"><span data-stu-id="58256-135">Since these are MSBuild targets, you can also use raw MSBuild to execute them using the [dotnet msbuild](dotnet-msbuild.md) command.</span></span> 

### <a name="cli-commands"></a><span data-ttu-id="58256-136">CLI コマンド</span><span class="sxs-lookup"><span data-stu-id="58256-136">CLI commands</span></span>
<span data-ttu-id="58256-137">共有 SDK コンポーネントとは、大多数の既存の CLI コマンドが MSBuild のタスクやターゲットとして再実装されたものです。</span><span class="sxs-lookup"><span data-stu-id="58256-137">The shared SDK component means that the majority of existing CLI commands have been re-implemented as MSBuild tasks and targets.</span></span> <span data-ttu-id="58256-138">これは CLI コマンドやツールセットの使用にどのような意味があるのでしょうか?</span><span class="sxs-lookup"><span data-stu-id="58256-138">What does this mean for the CLI commands and your usage of the toolset?</span></span> 

<span data-ttu-id="58256-139">使用の観点からは、CLI の使用方法には変わりはありません。</span><span class="sxs-lookup"><span data-stu-id="58256-139">From an usage perspective, it doesn't change the way you use the CLI.</span></span> <span data-ttu-id="58256-140">CLI にはまだ Preview 2 リリースにある主要なコマンドがあります。</span><span class="sxs-lookup"><span data-stu-id="58256-140">The CLI still has the core commands that exist in Preview 2 release:</span></span>

* `new`
* `restore`
* `run` 
* `build`
* `publish`
* `test`
* `pack` 

<span data-ttu-id="58256-141">これらのコマンドは、現在も (新しいプロジェクトの作成、構築、発行、作成などの) 目的の動作をします。</span><span class="sxs-lookup"><span data-stu-id="58256-141">These commands still do what you expect them to do (new up a project, build it, publish it, pack it and so on).</span></span> <span data-ttu-id="58256-142">オプションの多くは変更されず残っています。変更の詳細については、コマンドのヘルプ画面を (`dotnet <command> --help` を使用して) 確認するか、このサイトのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58256-142">Majority of the options are not changed, and are still there, and you can consult either the commands' help screens (using `dotnet <command> --help`) or documentation on this site to get familiar with any changes.</span></span> 

<span data-ttu-id="58256-143">実行の観点から見た場合、CLI コマンドはそのパラメーターを取り、必要なプロパティを設定して目的のターゲットを実行する「未加工」の MSBuild への呼び出しを作成します。</span><span class="sxs-lookup"><span data-stu-id="58256-143">From an execution perspective, the CLI commands will take their parameters and construct a call to "raw" MSBuild that will set the needed properties and run the desired target.</span></span> <span data-ttu-id="58256-144">次の図でこれを分かりやすく説明します。</span><span class="sxs-lookup"><span data-stu-id="58256-144">To better illustrate this, consider the following command:</span></span> 

   `dotnet publish -o pub -c Release`
    
<span data-ttu-id="58256-145">このコマンドは、"Release" 構成を使用してアプリケーションを `pub` フォルダーに発行します。</span><span class="sxs-lookup"><span data-stu-id="58256-145">This command is publishing an application into a `pub` folder using the "Release" configuration.</span></span> <span data-ttu-id="58256-146">このコマンドは、内部では次の MSBuild の呼び出しに変換されます。</span><span class="sxs-lookup"><span data-stu-id="58256-146">Internally, this command gets translated into the following MSBuild invocation:</span></span> 

   `dotnet msbuild /t:Publish /p:OutputPath=pub /p:Configuration=Release`

<span data-ttu-id="58256-147">`new` と `run` のコマンドは、MSBuild のターゲットとして実装されておらず、このルールの主な例外です。</span><span class="sxs-lookup"><span data-stu-id="58256-147">The notable exception to this rule are `new` and `run` commands, as they have not been implemented as MSBuild targets.</span></span>

<a name="dotnet-restore-note"></a>  
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

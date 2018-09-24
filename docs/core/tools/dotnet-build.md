---
title: dotnet build コマンド - .NET Core CLI
description: dotnet build コマンドは、プロジェクトとそのすべての依存関係をビルドします。
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: da33647e583af8441218f64fb8ac76d5de3cee38
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2018
ms.locfileid: "46580110"
---
# <a name="dotnet-build"></a><span data-ttu-id="495ce-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="495ce-103">dotnet build</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="495ce-104">name</span><span class="sxs-lookup"><span data-stu-id="495ce-104">Name</span></span>

<span data-ttu-id="495ce-105">`dotnet build` - プロジェクトとそのすべての依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="495ce-105">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="495ce-106">構文</span><span class="sxs-lookup"><span data-stu-id="495ce-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="495ce-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="495ce-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--no-dependencies] [--no-incremental]
    [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="495ce-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="495ce-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--no-dependencies] [--no-incremental] [-o|--output]
    [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="495ce-109">説明</span><span class="sxs-lookup"><span data-stu-id="495ce-109">Description</span></span>

<span data-ttu-id="495ce-110">`dotnet build` コマンドは、プロジェクトとその依存関係をバイナリ セットにビルドします。</span><span class="sxs-lookup"><span data-stu-id="495ce-110">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="495ce-111">バイナリには、拡張子が *.dll* である中間言語 (IL) ファイルのプロジェクトのコードと、拡張子が *.pdb* でありデバッグに使われるシンボル ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="495ce-111">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="495ce-112">アプリケーションの依存関係を一覧表示する依存関係 JSON ファイル (*\*.deps.json*) が生成されます。</span><span class="sxs-lookup"><span data-stu-id="495ce-112">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="495ce-113">共有ランタイムと、そのアプリケーションのバージョンを指定する、*\*.runtimeconfig.json* ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="495ce-113">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="495ce-114">サードパーティ (NuGet のライブラリなど) との依存関係があるプロジェクトの場合、NuGet キャッシュから解決され、プロジェクトのビルドの出力では使うことができません。</span><span class="sxs-lookup"><span data-stu-id="495ce-114">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="495ce-115">この点を考慮すると、`dotnet build` の生成物は別のコンピューターに転送して実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="495ce-115">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="495ce-116">これは .NET Framework の動作とは対照的です。 .NET Framework の場合、実行可能なプロジェクト (アプリケーション) をビルドすると、.NET Framework がインストールされている任意のコンピューター上で実行できる出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="495ce-116">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="495ce-117">.NET Core でも同様の動作にするには、[dotnet publish](dotnet-publish.md) コマンドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="495ce-117">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="495ce-118">詳しくは、「[.NET Core アプリケーション展開](../deploying/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="495ce-118">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="495ce-119">ビルドには *project.assets.json* ファイルが必要です。このファイルには、アプリケーションの依存関係が一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="495ce-119">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="495ce-120">このファイルは、[`dotnet restore`](dotnet-restore.md) を実行すると作成されます。</span><span class="sxs-lookup"><span data-stu-id="495ce-120">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="495ce-121">アセット ファイルがないと、ツールは参照アセンブリを解決できないため、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="495ce-121">Without the assets file in place, the tooling cannot resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="495ce-122">.NET Core 1.x SDK の場合、`dotnet build` を実行する前に `dotnet restore` を明示的に実行する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="495ce-122">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="495ce-123">.NET Core 2.0 SDK 以降では、`dotnet build` を実行すると、`dotnet restore` が暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="495ce-123">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="495ce-124">ビルド コマンドの実行時に暗黙的な復元を無効にする場合は、`--no-restore` オプションを渡します。</span><span class="sxs-lookup"><span data-stu-id="495ce-124">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="495ce-125">`dotnet build` では MSBuild を使用してプロジェクトをビルドするため、並列ビルドとインクリメンタル ビルドの両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="495ce-125">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="495ce-126">詳しくは、「[インクリメンタル ビルド](/visualstudio/msbuild/incremental-builds)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495ce-126">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="495ce-127">このオプションに加え、`dotnet build` コマンドは、プロパティを設定する `-p` やロガーを定義する `-l` などの MSBuild オプションも受け入れます。</span><span class="sxs-lookup"><span data-stu-id="495ce-127">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="495ce-128">これらのオプションの詳細については、「[MSBuild コマンド ライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495ce-128">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="495ce-129">プロジェクトを実行できるかどうかは、プロジェクト ファイルの `<OutputType>` プロパティで決まります。</span><span class="sxs-lookup"><span data-stu-id="495ce-129">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="495ce-130">次の例は、実行可能なコードを生成するプロジェクトを示しています。</span><span class="sxs-lookup"><span data-stu-id="495ce-130">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="495ce-131">ライブラリを生成するには、`<OutputType>` プロパティを省略してください。</span><span class="sxs-lookup"><span data-stu-id="495ce-131">In order to produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="495ce-132">ビルドされる出力の主な違いは、ライブラリの IL DLL にはエントリ ポイントが含まれず、実行できないことです。</span><span class="sxs-lookup"><span data-stu-id="495ce-132">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

## <a name="arguments"></a><span data-ttu-id="495ce-133">引数</span><span class="sxs-lookup"><span data-stu-id="495ce-133">Arguments</span></span>

`PROJECT`

<span data-ttu-id="495ce-134">ビルドするプロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="495ce-134">The project file to build.</span></span> <span data-ttu-id="495ce-135">プロジェクト ファイルを指定しない場合、MSBuild は、現在の作業ディレクトリから *proj* で終わるファイル名拡張子を検索し、そのファイルを使います。</span><span class="sxs-lookup"><span data-stu-id="495ce-135">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="495ce-136">オプション</span><span class="sxs-lookup"><span data-stu-id="495ce-136">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="495ce-137">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="495ce-137">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="495ce-138">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="495ce-138">Defines the build configuration.</span></span> <span data-ttu-id="495ce-139">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="495ce-139">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="495ce-140">特定の[フレームワーク](../../standard/frameworks.md)用にコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="495ce-140">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="495ce-141">フレームワークは、[プロジェクト ファイル](csproj.md)で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="495ce-141">The framework must be defined in the [project file](csproj.md).</span></span>

`--force`

<span data-ttu-id="495ce-142">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="495ce-142">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="495ce-143">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="495ce-143">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="495ce-144">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="495ce-144">Prints out a short help for the command.</span></span>

`--no-dependencies`

<span data-ttu-id="495ce-145">プロジェクト間 (P2P) 参照を無視し、指定されたルート プロジェクトのみをビルドします。</span><span class="sxs-lookup"><span data-stu-id="495ce-145">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

`--no-incremental`

<span data-ttu-id="495ce-146">インクリメンタル ビルドとして安全でないビルドをマークします。</span><span class="sxs-lookup"><span data-stu-id="495ce-146">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="495ce-147">このフラグにより、インクリメンタル コンパイルは無効になり、プロジェクトの依存関係グラフのクリーン再ビルドが強制的に行われます。</span><span class="sxs-lookup"><span data-stu-id="495ce-147">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`--no-restore`

<span data-ttu-id="495ce-148">ビルド時に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="495ce-148">Doesn't execute an implicit restore during build.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="495ce-149">ビルド済みバイナリを配置するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="495ce-149">Directory in which to place the built binaries.</span></span> <span data-ttu-id="495ce-150">このオプションを指定する場合は、`--framework` を定義する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="495ce-150">You also need to define `--framework` when you specify this option.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="495ce-151">ターゲットのランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="495ce-151">Specifies the target runtime.</span></span> <span data-ttu-id="495ce-152">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="495ce-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="495ce-153">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="495ce-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="495ce-154">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="495ce-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="495ce-155">プロジェクト ファイルのバージョン フィールドでアスタリスク (`*`) のバージョン サフィックスを定義します。</span><span class="sxs-lookup"><span data-stu-id="495ce-155">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="495ce-156">形式は NuGet のバージョン ガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="495ce-156">The format follows NuGet's version guidelines.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="495ce-157">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="495ce-157">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="495ce-158">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="495ce-158">Defines the build configuration.</span></span> <span data-ttu-id="495ce-159">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="495ce-159">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="495ce-160">特定の[フレームワーク](../../standard/frameworks.md)用にコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="495ce-160">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="495ce-161">フレームワークは、[プロジェクト ファイル](csproj.md)で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="495ce-161">The framework must be defined in the [project file](csproj.md).</span></span>

`-h|--help`

<span data-ttu-id="495ce-162">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="495ce-162">Prints out a short help for the command.</span></span>

`--no-dependencies`

<span data-ttu-id="495ce-163">プロジェクト間 (P2P) 参照を無視し、指定されたルート プロジェクトのみをビルドします。</span><span class="sxs-lookup"><span data-stu-id="495ce-163">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

`--no-incremental`

<span data-ttu-id="495ce-164">インクリメンタル ビルドとして安全でないビルドをマークします。</span><span class="sxs-lookup"><span data-stu-id="495ce-164">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="495ce-165">このフラグにより、インクリメンタル コンパイルは無効になり、プロジェクトの依存関係グラフのクリーン再ビルドが強制的に行われます。</span><span class="sxs-lookup"><span data-stu-id="495ce-165">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="495ce-166">ビルド済みバイナリを配置するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="495ce-166">Directory in which to place the built binaries.</span></span> <span data-ttu-id="495ce-167">このオプションを指定する場合は、`--framework` を定義する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="495ce-167">You also need to define `--framework` when you specify this option.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="495ce-168">ターゲットのランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="495ce-168">Specifies the target runtime.</span></span> <span data-ttu-id="495ce-169">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="495ce-169">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="495ce-170">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="495ce-170">Sets the verbosity level of the command.</span></span> <span data-ttu-id="495ce-171">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="495ce-171">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="495ce-172">プロジェクト ファイルのバージョン フィールドでアスタリスク (`*`) のバージョン サフィックスを定義します。</span><span class="sxs-lookup"><span data-stu-id="495ce-172">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="495ce-173">形式は NuGet のバージョン ガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="495ce-173">The format follows NuGet's version guidelines.</span></span>

---

## <a name="examples"></a><span data-ttu-id="495ce-174">使用例</span><span class="sxs-lookup"><span data-stu-id="495ce-174">Examples</span></span>

<span data-ttu-id="495ce-175">プロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="495ce-175">Build a project and its dependencies:</span></span>

`dotnet build`

<span data-ttu-id="495ce-176">リリース構成を使用して、プロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="495ce-176">Build a project and its dependencies using Release configuration:</span></span>

`dotnet build --configuration Release`

<span data-ttu-id="495ce-177">特定のランタイム (この例では、Ubuntu 16.04) 用にプロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="495ce-177">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 16.04):</span></span>

`dotnet build --runtime ubuntu.16.04-x64`

<span data-ttu-id="495ce-178">プロジェクトをビルドし、復元操作中に指定された NuGet パッケージ ソースを使用します (.NET Core SDK 2.0 以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="495ce-178">Build the project and use the specified NuGet package source during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet build --source c:\packages\mypackages`
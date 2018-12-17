---
title: dotnet pack コマンド - .NET Core CLI
description: dotnet pack コマンドでは、.NET Core プロジェクトの NuGet パッケージを作成します。
ms.date: 12/04/2018
ms.openlocfilehash: 77770e715ef11595e8c95bb40be960138cd7ec61
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149602"
---
# <a name="dotnet-pack"></a><span data-ttu-id="3f0e1-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="3f0e1-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="3f0e1-104">name</span><span class="sxs-lookup"><span data-stu-id="3f0e1-104">Name</span></span>

<span data-ttu-id="3f0e1-105">`dotnet pack` - NuGet パッケージにコードをパックします。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3f0e1-106">構文</span><span class="sxs-lookup"><span data-stu-id="3f0e1-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="3f0e1-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3f0e1-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3f0e1-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3f0e1-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output]
    [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="3f0e1-109">説明</span><span class="sxs-lookup"><span data-stu-id="3f0e1-109">Description</span></span>

<span data-ttu-id="3f0e1-110">`dotnet pack` コマンドはプロジェクトをビルドし、NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="3f0e1-111">このコマンドの結果が NuGet パッケージです。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="3f0e1-112">`--include-symbols` オプションが存在する場合、デバッグ シンボルを含む別のパッケージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="3f0e1-113">パックされるプロジェクトの NuGet 依存関係が *.nuspec* ファイルに追加されるため、パッケージのインストール時に適切に解決されます。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="3f0e1-114">プロジェクト間参照はプロジェクト内にはパッケージ化されません。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="3f0e1-115">現時点では、プロジェクト間の依存関係がある場合は、プロジェクトごとにパッケージが必要になります。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="3f0e1-116">既定では、`dotnet pack` は最初にプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="3f0e1-117">この動作を避けたい場合は、`--no-build` オプションを渡します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="3f0e1-118">このオプションは、コードが既にビルドされていることがわかっている場合の継続的インテグレーション (CI) ビルド シナリオで役立つことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-118">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="3f0e1-119">パッキング プロセスのために `dotnet pack` コマンドに MSBuild のプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="3f0e1-120">詳細については、「[NuGet メタデータ プロパティ](csproj.md#nuget-metadata-properties)」と「[MSBuild コマンド ライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="3f0e1-121">「[例](#examples)」のセクションでは、MSBuild の -p スイッチを使用する方法について、2 つの異なるシナリオで説明します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-121">The [Examples](#examples) section shows how to use the MSBuild -p switch for a couple of different scenarios.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="3f0e1-122">引数</span><span class="sxs-lookup"><span data-stu-id="3f0e1-122">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="3f0e1-123">パックするプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-123">The project to pack.</span></span> <span data-ttu-id="3f0e1-124">[csproj ファイル](csproj.md)またはディレクトリのいずれかへのパスです。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-124">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="3f0e1-125">指定しない場合は、既定で現在のディレクトリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="3f0e1-126">オプション</span><span class="sxs-lookup"><span data-stu-id="3f0e1-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="3f0e1-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3f0e1-127">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="3f0e1-128">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-128">Defines the build configuration.</span></span> <span data-ttu-id="3f0e1-129">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-129">The default value is `Debug`.</span></span>

* **`--force`**

  <span data-ttu-id="3f0e1-130">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="3f0e1-131">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-131">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

* **`-h|--help`**

  <span data-ttu-id="3f0e1-132">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-132">Prints out a short help for the command.</span></span>

* **`--include-source`**

  <span data-ttu-id="3f0e1-133">NuGet パッケージにソース ファイルを含めます。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-133">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="3f0e1-134">ソース ファイルは、`nupkg` 内の `src` フォルダーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-134">The sources files are included in the `src` folder within the `nupkg`.</span></span>

* **`--include-symbols`**

  <span data-ttu-id="3f0e1-135">シンボルの `nupkg` を生成します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-135">Generates the symbols `nupkg`.</span></span>

* **`--no-build`**

  <span data-ttu-id="3f0e1-136">パッキングの前にプロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-136">Doesn't build the project before packing.</span></span> <span data-ttu-id="3f0e1-137">また、`--no-restore` フラグが暗黙的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-137">It also implicit sets the `--no-restore` flag.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="3f0e1-138">プロジェクト間参照を無視し、ルート プロジェクトのみを復元します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-138">Ignores project-to-project references and only restores the root project.</span></span>

* **`--no-restore`**

  <span data-ttu-id="3f0e1-139">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-139">Doesn't execute an implicit restore when running the command.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="3f0e1-140">指定したディレクトリにビルド済みパッケージを配置します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-140">Places the built packages in the directory specified.</span></span>

* **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="3f0e1-141">パッケージを復元するターゲット ランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-141">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="3f0e1-142">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-142">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-s|--serviceable`**

  <span data-ttu-id="3f0e1-143">パッケージに処理可能フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-143">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="3f0e1-144">詳しくは、「[.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing)」(.NET ブログ: .NET 4.5.1 は .NET NuGet ライブラリに対する Microsoft セキュリティ更新プログラムをサポートする) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-144">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="3f0e1-145">プロジェクトの `$(VersionSuffix)` MSBuild プロパティの値を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-145">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="3f0e1-146">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="3f0e1-147">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

> [!NOTE]
> <span data-ttu-id="3f0e1-148">Web プロジェクトは既定でパッケージ化可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-148">Web projects aren't packable by default.</span></span> <span data-ttu-id="3f0e1-149">既定の動作をオーバーライドするには、*.csproj* ファイルに次のプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-149">To override the default behavior, add the following property to your *.csproj* file:</span></span>
> ```xml
> <PropertyGroup>
>    <IsPackable>true</IsPackable>
> </PropertyGroup>
> ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3f0e1-150">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3f0e1-150">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="3f0e1-151">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-151">Defines the build configuration.</span></span> <span data-ttu-id="3f0e1-152">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-152">The default value is `Debug`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="3f0e1-153">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-153">Prints out a short help for the command.</span></span>

* **`--include-source`**

  <span data-ttu-id="3f0e1-154">NuGet パッケージにソース ファイルを含めます。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-154">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="3f0e1-155">ソース ファイルは、`nupkg` 内の `src` フォルダーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-155">The sources files are included in the `src` folder within the `nupkg`.</span></span>

* **`--include-symbols`**

  <span data-ttu-id="3f0e1-156">シンボルの `nupkg` を生成します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-156">Generates the symbols `nupkg`.</span></span>

* **`--no-build`**

  <span data-ttu-id="3f0e1-157">パッキングの前にプロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-157">Doesn't build the project before packing.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="3f0e1-158">指定したディレクトリにビルド済みパッケージを配置します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-158">Places the built packages in the directory specified.</span></span>

* **`-s|--serviceable`**

  <span data-ttu-id="3f0e1-159">パッケージに処理可能フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-159">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="3f0e1-160">詳しくは、「[.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing)」(.NET ブログ: .NET 4.5.1 は .NET NuGet ライブラリに対する Microsoft セキュリティ更新プログラムをサポートする) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-160">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="3f0e1-161">プロジェクトの `$(VersionSuffix)` MSBuild プロパティの値を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-161">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="3f0e1-162">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="3f0e1-163">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="3f0e1-164">使用例</span><span class="sxs-lookup"><span data-stu-id="3f0e1-164">Examples</span></span>

* <span data-ttu-id="3f0e1-165">現在のディレクトリのプロジェクトをパックします。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-165">Pack the project in the current directory:</span></span>

  ```console
  dotnet pack
  ```

* <span data-ttu-id="3f0e1-166">`app1` プロジェクトをパックします。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-166">Pack the `app1` project:</span></span>

  ```console
  dotnet pack ~/projects/app1/project.csproj
  ```

* <span data-ttu-id="3f0e1-167">プロジェクトを現在のディレクトリにパックし、`nupkgs` フォルダーに生成されたパッケージを配置します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-167">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

  ```console
  dotnet pack --output nupkgs
  ```

* <span data-ttu-id="3f0e1-168">現在のディレクトリのプロジェクトを `nupkgs` フォルダーにパックし、ビルド ステップをスキップします。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-168">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

  ```console
  dotnet pack --no-build --output nupkgs
  ```

* <span data-ttu-id="3f0e1-169">*.csproj* ファイルで `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` として構成されているプロジェクトのバージョン サフィックスで、現在のプロジェクトをパックし、結果のパッケージ バージョンを指定されたサフィックスで更新します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-169">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

  ```console
  dotnet pack --version-suffix "ci-1234"
  ```

* <span data-ttu-id="3f0e1-170">`PackageVersion` MSBuild プロパティで `2.1.0` にパッケージ バージョンを設定します。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-170">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

  ```console
  dotnet pack -p:PackageVersion=2.1.0
  ```

* <span data-ttu-id="3f0e1-171">プロジェクトを特定の[ターゲット フレームワーク](../../standard/frameworks.md)用にパックします。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-171">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

  ```console
  dotnet pack -p:TargetFrameworks=net45
  ```

* <span data-ttu-id="3f0e1-172">プロジェクトをパックして、復元操作の特定のランタイム (Windows 10) を使用します(.NET Core SDK 2.0 以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-172">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

  ```console
  dotnet pack --runtime win10-x64
  ```

* <span data-ttu-id="3f0e1-173">[.nuspec ファイル](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec)を使用してプロジェクトをパックします。</span><span class="sxs-lookup"><span data-stu-id="3f0e1-173">Pack the projec using a [.nuspec file](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span></span>

  ```console
  dotnet pack  ~/projects/app1/project.csproj /p:NuspecFile=~/projects/app1/project.nuspec /p:NuspecBasePath=~/projects/app1/nuget
  ```
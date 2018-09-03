---
title: dotnet tool install コマンド - .NET Core CLI
description: dotnet tool install コマンドでは、使用しているマシンに指定された .NET Core グローバル ツールをインストールします。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: aad5a3e815936749d90f40975a8b13d34e89386c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43418722"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="5c208-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="5c208-103">dotnet tool install</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="5c208-104">name</span><span class="sxs-lookup"><span data-stu-id="5c208-104">Name</span></span>

<span data-ttu-id="5c208-105">`dotnet tool install` - 使用しているマシンに指定された [.NET Core グローバル ツール](global-tools.md)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5c208-105">`dotnet tool install` - Installs the specified [.NET Core Global Tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5c208-106">構文</span><span class="sxs-lookup"><span data-stu-id="5c208-106">Synopsis</span></span>

```console
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a><span data-ttu-id="5c208-107">説明</span><span class="sxs-lookup"><span data-stu-id="5c208-107">Description</span></span>

<span data-ttu-id="5c208-108">`dotnet tool install` コマンドでは、使用しているマシンに .NET Core グローバル ツールをインストールするための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="5c208-108">The `dotnet tool install` command provides a way for you to install .NET Core Global Tools on your machine.</span></span> <span data-ttu-id="5c208-109">コマンドを使用するには、`--global` オプションを使用してユーザー全体のインストールを指定するか、`--tool-path` オプションを使用してツールをインストールするパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c208-109">To use the command, you either have to specify that you want a user-wide installation using the `--global` option or you specify a path to install it using the `--tool-path` option.</span></span>

<span data-ttu-id="5c208-110">グローバル ツールは、`-g` (または `--global`) オプションを指定した場合、既定では次のディレクトリにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5c208-110">Global Tools are installed in the following directories by default when you specify the `-g` (or `--global`) option:</span></span>

| <span data-ttu-id="5c208-111">OS</span><span class="sxs-lookup"><span data-stu-id="5c208-111">OS</span></span>          | <span data-ttu-id="5c208-112">パス</span><span class="sxs-lookup"><span data-stu-id="5c208-112">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="5c208-113">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="5c208-113">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="5c208-114">Windows</span><span class="sxs-lookup"><span data-stu-id="5c208-114">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

## <a name="arguments"></a><span data-ttu-id="5c208-115">引数</span><span class="sxs-lookup"><span data-stu-id="5c208-115">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="5c208-116">インストールする .NET Core グローバル ツールを含む、NuGet パッケージの名前または ID。</span><span class="sxs-lookup"><span data-stu-id="5c208-116">Name/ID of the NuGet package that contains the .NET Core Global Tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="5c208-117">オプション</span><span class="sxs-lookup"><span data-stu-id="5c208-117">Options</span></span>

`--add-source <SOURCE>`

<span data-ttu-id="5c208-118">インストール時に使用するために追加の NuGet パッケージ ソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c208-118">Adds an additional NuGet package source to use during installation.</span></span>

`--configfile <FILE>`

<span data-ttu-id="5c208-119">使用する NuGet 構成 (*nuget.config*) ファイル。</span><span class="sxs-lookup"><span data-stu-id="5c208-119">The NuGet configuration (*nuget.config*) file to use.</span></span>

`--framework <FRAMEWORK>`

<span data-ttu-id="5c208-120">ツールをインストールする[ターゲット フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c208-120">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="5c208-121">既定では、.NET Core SDK は最適なターゲット フレームワークの選択を試みます。</span><span class="sxs-lookup"><span data-stu-id="5c208-121">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

`-g|--global`

<span data-ttu-id="5c208-122">ユーザー全体のインストールを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c208-122">Specifies that the installation is user wide.</span></span> <span data-ttu-id="5c208-123">`--tool-path` オプションと組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="5c208-123">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="5c208-124">このオプションを指定しない場合は、`--tool-path` オプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c208-124">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="5c208-125">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="5c208-125">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="5c208-126">グローバル ツールをインストールする場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c208-126">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="5c208-127">PATH は絶対パスでも相対パスでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="5c208-127">PATH can be absolute or relative.</span></span> <span data-ttu-id="5c208-128">PATH が存在しない場合、コマンドではパスの作成を試みます。</span><span class="sxs-lookup"><span data-stu-id="5c208-128">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="5c208-129">`--global` オプションと組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="5c208-129">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="5c208-130">このオプションを指定しない場合は、`--global` オプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c208-130">If you don't specify this option, you must specify the `--global` option.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="5c208-131">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="5c208-131">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5c208-132">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="5c208-132">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version <VERSION_NUMBER>`

<span data-ttu-id="5c208-133">インストールするツールのバージョン。</span><span class="sxs-lookup"><span data-stu-id="5c208-133">The version of the tool to install.</span></span> <span data-ttu-id="5c208-134">既定では、安定した最新バージョンのパッケージがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5c208-134">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="5c208-135">このオプションを使用して、プレビューまたは古いバージョンのツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5c208-135">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="5c208-136">使用例</span><span class="sxs-lookup"><span data-stu-id="5c208-136">Examples</span></span>

<span data-ttu-id="5c208-137">既定の場所に [dotnetsay](https://www.nuget.org/packages/dotnetsay/) グローバル ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5c208-137">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool in the default location:</span></span>

`dotnet tool install -g dotnetsay`

<span data-ttu-id="5c208-138">特定の Windows フォルダーに [dotnetsay](https://www.nuget.org/packages/dotnetsay/) グローバル ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5c208-138">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool on a specific Windows folder:</span></span>

`dotnet tool install dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="5c208-139">特定の Linux/macOS フォルダーに [dotnetsay](https://www.nuget.org/packages/dotnetsay/) グローバル ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5c208-139">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool on a specific Linux/macOS folder:</span></span>

`dotnet tool install dotnetsay --tool-path ~/bin`

<span data-ttu-id="5c208-140">バージョン 2.0.0 の [dotnetsay](https://www.nuget.org/packages/dotnetsay/) グローバル ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5c208-140">Installs version 2.0.0 of the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool install -g dotnetsay --version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="5c208-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c208-141">See also</span></span>

* [<span data-ttu-id="5c208-142">.NET Core グローバル ツール</span><span class="sxs-lookup"><span data-stu-id="5c208-142">.NET Core Global Tools</span></span>](global-tools.md)
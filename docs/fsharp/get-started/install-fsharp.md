---
title: F# のインストールします。
description: お客様の環境に基づいて、f# をインストールする方法について説明します。
ms.date: 08/28/2018
ms.openlocfilehash: 909e1c07ff7f6d52db77a987639d1c749146fdca
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49120935"
---
# <a name="install-f"></a><span data-ttu-id="7abc8-103">F# のインストールします。</span><span class="sxs-lookup"><span data-stu-id="7abc8-103">Install F#</span></span> #

<span data-ttu-id="7abc8-104">複数の方法で f# をインストールと、環境に応じてことができます。</span><span class="sxs-lookup"><span data-stu-id="7abc8-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="7abc8-105">Visual Studio を使用した f# のインストールします。</span><span class="sxs-lookup"><span data-stu-id="7abc8-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="7abc8-106">ダウンロードしている場合[Visual Studio](https://visualstudio.microsoft.com/)最初に、これは最初にインストール、Visual Studio インストーラー。</span><span class="sxs-lookup"><span data-stu-id="7abc8-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="7abc8-107">インストーラーから、適切な SKU の Visual Studio をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7abc8-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="7abc8-108">既にインストールされていること、クリックして**変更**します。</span><span class="sxs-lookup"><span data-stu-id="7abc8-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="7abc8-109">次のワークロードの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="7abc8-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="7abc8-110">選択**ASP.NET および web 開発**f# サポートおよび ASP.NET Core プロジェクトの .NET Core のサポートがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7abc8-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="7abc8-111">次に、クリックして**変更**下部右側にあります。</span><span class="sxs-lookup"><span data-stu-id="7abc8-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="7abc8-112">これは、選択したすべてのものにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7abc8-112">This will install everything you have selected.</span></span> <span data-ttu-id="7abc8-113">クリックして、f# 言語サポートと Visual Studio 2017 を開くことができますし、**起動**します。</span><span class="sxs-lookup"><span data-stu-id="7abc8-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="7abc8-114">F# で Visual Studio for Mac をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7abc8-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="7abc8-115">既定で f# がインストールされている[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/)、選択した構成に関係なく。</span><span class="sxs-lookup"><span data-stu-id="7abc8-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/), no matter which configuration you choose.</span></span>

<span data-ttu-id="7abc8-116">インストールが完了した後は、"Visual Studio を起動する"を選択します。</span><span class="sxs-lookup"><span data-stu-id="7abc8-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="7abc8-117">起動してもかまいませんが Finder を macOS でします。</span><span class="sxs-lookup"><span data-stu-id="7abc8-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="7abc8-118">Visual Studio Code で f# のインストールします。</span><span class="sxs-lookup"><span data-stu-id="7abc8-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="7abc8-119">必要があります[git がインストールされている](https://git-scm.com/download)を PATH にで使用可能なプロジェクト テンプレートの使用します。</span><span class="sxs-lookup"><span data-stu-id="7abc8-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="7abc8-120">」と入力して正しくインストールされていることを確認する`git --version`キーを押して、コマンド プロンプトで**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="7abc8-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="7abc8-121">macOS</span><span class="sxs-lookup"><span data-stu-id="7abc8-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="7abc8-122">[Mono](http://www.mono-project.com)使用[f# Interactive](../tutorials/fsharp-interactive/index.md)をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7abc8-122">[Mono](http://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="7abc8-123">MacOS で Mono をインストールする最も簡単な方法は、Homebrew を使用してです。</span><span class="sxs-lookup"><span data-stu-id="7abc8-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="7abc8-124">単に、ターミナルに、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="7abc8-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="7abc8-125">インストールことも、 [.NET Core SDK](https://www.microsoft.com/net/download)します。</span><span class="sxs-lookup"><span data-stu-id="7abc8-125">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="7abc8-126">Linux</span><span class="sxs-lookup"><span data-stu-id="7abc8-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="7abc8-127">[Mono](https://www.mono-project.com)使用[f# Interactive](../tutorials/fsharp-interactive/index.md)をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7abc8-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="7abc8-128">Debian または Ubuntu の場合は、次を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7abc8-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="7abc8-129">インストールことも、 [.NET Core SDK](https://www.microsoft.com/net/download)します。</span><span class="sxs-lookup"><span data-stu-id="7abc8-129">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="7abc8-130">Windows</span><span class="sxs-lookup"><span data-stu-id="7abc8-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="7abc8-131">インストール[f# のサポートを使用した Visual Studio](#install-f-with-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="7abc8-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="7abc8-132">これにより、書き込み、コンパイル、および f# コードの実行に必要なすべてのコンポーネントがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7abc8-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="7abc8-133">インストールことも、 [.NET Core SDK](https://www.microsoft.com/net/download/)します。</span><span class="sxs-lookup"><span data-stu-id="7abc8-133">Also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="7abc8-134">その後[Visual Studio Code](https://code.visualstudio.com)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7abc8-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="7abc8-135">次に、「ionide の概要」の検索と拡張機能アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7abc8-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="7abc8-136">Visual Studio Code での f# サポートが必要な唯一のプラグイン[ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)します。</span><span class="sxs-lookup"><span data-stu-id="7abc8-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="7abc8-137">ただし、インストールすることも[Ionide フェイク](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)を取得する[フェイク](https://fsharp.github.io/FAKE/)サポートと[Ionide パケット](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)を取得する[パケットを作成](https://fsprojects.github.io/Paket/)をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7abc8-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="7abc8-138">偽の追加 f# コミュニティのツールをプロジェクトのビルドとの依存関係をそれぞれ管理は、パケットを作成します。</span><span class="sxs-lookup"><span data-stu-id="7abc8-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

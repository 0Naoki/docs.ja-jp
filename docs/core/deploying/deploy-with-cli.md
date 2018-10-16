---
title: CLI ツールで .NET Core アプリを展開する
description: コマンド ライン インターフェイス (CLI) ツールを使用して .NET Core アプリを展開する方法を説明します。
author: rpetrusha
ms.author: ronpet
ms.date: 09/05/2018
dev_langs:
- csharp
- vb
ms.openlocfilehash: a7e810372d831699eae777186385e45fe65cdf45
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2018
ms.locfileid: "47208251"
---
# <a name="deploying-net-core-apps-with-command-line-interface-cli-tools"></a><span data-ttu-id="f9966-103">コマンド ライン インターフェイス (CLI) ツールを使用して .NET Core アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="f9966-103">Deploying .NET Core apps with command-line interface (CLI) tools</span></span>

<span data-ttu-id="f9966-104">.NET Core アプリケーションは、アプリケーション バイナリは含むが対象のシステムに .NET Core バイナリが存在することに依存する*フレームワークに依存する展開*か、アプリケーションと .NET Core のバイナリの両方を含む*自己完結型の配置*のいずれかで展開できます。</span><span class="sxs-lookup"><span data-stu-id="f9966-104">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and the .NET Core binaries.</span></span> <span data-ttu-id="f9966-105">概要については、「[.NET Core アプリケーション展開](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9966-105">For an overview, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="f9966-106">以降のセクションでは、次のような展開を作成するために [.NET Core コマンド ライン インターフェイス ツール](../tools/index.md)を使用する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f9966-106">The following sections show how to use [.NET Core command-line interface tools](../tools/index.md) to create the following kinds of deployments:</span></span>

- <span data-ttu-id="f9966-107">フレームワークに依存する展開</span><span class="sxs-lookup"><span data-stu-id="f9966-107">Framework-dependent deployment</span></span>
- <span data-ttu-id="f9966-108">サードパーティの依存関係を含む、フレームワークに依存する展開</span><span class="sxs-lookup"><span data-stu-id="f9966-108">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="f9966-109">自己完結型の展開</span><span class="sxs-lookup"><span data-stu-id="f9966-109">Self-contained deployment</span></span>
- <span data-ttu-id="f9966-110">サードパーティの依存関係を含む、自己完結型の展開</span><span class="sxs-lookup"><span data-stu-id="f9966-110">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="f9966-111">コマンド ラインを使用する場合は、任意のプログラム エディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9966-111">When working from the command line, you can use a program editor of your choice.</span></span> <span data-ttu-id="f9966-112">プログラム エディターが [Visual Studio Code](https://code.visualstudio.com) の場合、**[表示]** > **[統合ターミナル]** を選択して、Visual Studio Code 環境内にコマンド コンソールを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="f9966-112">If your program editor is [Visual Studio Code](https://code.visualstudio.com), you can open a command console inside your Visual Studio Code environment by selecting **View** > **Integrated Terminal**.</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="f9966-113">フレームワークに依存する展開</span><span class="sxs-lookup"><span data-stu-id="f9966-113">Framework-dependent deployment</span></span>

<span data-ttu-id="f9966-114">サードパーティの依存関係を含まない、フレームワークに依存する展開を展開するプロセスには、アプリのビルド、テスト、および発行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f9966-114">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="f9966-115">C# で記述された次の単純な例は、このプロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="f9966-115">A simple example written in C# illustrates the process.</span></span>

1. <span data-ttu-id="f9966-116">プロジェクトのディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9966-116">Create a project directory.</span></span>

   <span data-ttu-id="f9966-117">プロジェクトのディレクトリを作成し、それを現在のディレクトリにします。</span><span class="sxs-lookup"><span data-stu-id="f9966-117">Create a directory for your project and make it your current directory.</span></span>

1. <span data-ttu-id="f9966-118">プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9966-118">Create the project.</span></span>

   <span data-ttu-id="f9966-119">コマンドラインから「[dotnet new console](../tools/dotnet-new.md)」と入力すると新しい C# コンソール プロジェクトが作成され、「[dotnet new console -lang vb](../tools/dotnet-new.md)」と入力するとこのディレクトリに新しい Visual Basic コンソール プロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f9966-119">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project or [dotnet new console -lang vb](../tools/dotnet-new.md) to create a new Visual Basic console project in that directory.</span></span>

1. <span data-ttu-id="f9966-120">アプリケーションのソース コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f9966-120">Add the application's source code.</span></span>

   <span data-ttu-id="f9966-121">エディターで *Program.cs* または *Program.vb* ファイルを開き、自動生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f9966-121">Open the *Program.cs* or *Program.vb* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="f9966-122">テキストの入力を求めるプロンプトが表示されてから、ユーザーが入力した個々の単語が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9966-122">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="f9966-123">正規表現 `\w+` を使用して、入力テキストの単語を分離します。</span><span class="sxs-lookup"><span data-stu-id="f9966-123">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]

1. <span data-ttu-id="f9966-124">プロジェクトの依存関係とツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="f9966-124">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="f9966-125">[dotnet restore](../tools/dotnet-restore.md) コマンドを実行して、プロジェクトで指定された依存関係を復元します ([注記参照](#dotnet-restore-note))。</span><span class="sxs-lookup"><span data-stu-id="f9966-125">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="f9966-126">アプリのデバッグ ビルドを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9966-126">Create a Debug build of your app.</span></span>

   <span data-ttu-id="f9966-127">[dotnet build](../tools/dotnet-build.md) コマンドを使用すると、アプリケーションをビルドでき、[dotnet run](../tools/dotnet-run.md) コマンドを使用すると、それをビルドして実行できます。</span><span class="sxs-lookup"><span data-stu-id="f9966-127">Use the [dotnet build](../tools/dotnet-build.md) command to build your application or the [dotnet run](../tools/dotnet-run.md) command to build and run it.</span></span>

1. <span data-ttu-id="f9966-128">アプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="f9966-128">Deploy your app.</span></span>

   <span data-ttu-id="f9966-129">プログラムをテストし、デバッグした後は、次のコマンドを使用して、展開を作成します。</span><span class="sxs-lookup"><span data-stu-id="f9966-129">After you've debugged and tested the program, create the deployment by using the following command:</span></span>

      ```console
      dotnet publish -f netcoreapp2.1 -c Release
      ```
   <span data-ttu-id="f9966-130">これにより、リリース (デバッグではなく) バージョンのアプリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f9966-130">This creates a Release (rather than a Debug) version of your app.</span></span> <span data-ttu-id="f9966-131">作成されたファイルは、プロジェクトの *bin* ディレクトリのサブディレクトリ内にある *publish* という名前のディレクトリに配置されます。</span><span class="sxs-lookup"><span data-stu-id="f9966-131">The resulting files are placed in a directory named *publish*      that's in a subdirectory of your project's *bin* directory.</span></span>

   <span data-ttu-id="f9966-132">アプリケーションのファイルと共に、発行プロセスは、アプリに関するデバッグ情報を含むプログラム データベース (.pdb) ファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="f9966-132">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="f9966-133">このファイルは、主に例外のデバッグに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f9966-133">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="f9966-134">これは、アプリケーションのファイルと一緒には配布しないよう選択できます。</span><span class="sxs-lookup"><span data-stu-id="f9966-134">You can choose not to distribute it with your application's files.</span></span> <span data-ttu-id="f9966-135">ただし、アプリのリリース ビルドをデバッグする場合のために、保存しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f9966-135">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

   <span data-ttu-id="f9966-136">アプリケーション ファイルの完全なセットは、任意の方法で展開できます。</span><span class="sxs-lookup"><span data-stu-id="f9966-136">You can deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="f9966-137">たとえば、Zip ファイルにパッケージ化したり、単純な `copy` コマンドを使用したり、任意のインストール パッケージで展開したりできます。</span><span class="sxs-lookup"><span data-stu-id="f9966-137">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

1. <span data-ttu-id="f9966-138">アプリの実行</span><span class="sxs-lookup"><span data-stu-id="f9966-138">Run your app</span></span>

   <span data-ttu-id="f9966-139">一度インストールすると、ユーザーは `dotnet` コマンドを使用して、`dotnet fdd.dll` などのアプリケーションのファイル名を入力してアプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f9966-139">Once installed, users can execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

   <span data-ttu-id="f9966-140">また、アプリケーション インストールの一環として、インストーラーはアプリケーション バイナリに加えて、共有フレームワーク インストーラーをバンドルするか、または前提条件として共有フレームワークがあるか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9966-140">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="f9966-141">共有フレームワークをインストールするには、管理者またはルートの権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="f9966-141">Installation of the shared framework requires Administrator/root access.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="f9966-142">サードパーティの依存関係を含む、フレームワークに依存する展開</span><span class="sxs-lookup"><span data-stu-id="f9966-142">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="f9966-143">1 つ以上のサードパーティの依存関係を備えたフレームワークに依存する展開を展開するには、それらの依存関係がプロジェクトで使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9966-143">Deploying a framework-dependent deployment with one or more third-party dependencies requires that those dependencies be available to your project.</span></span> <span data-ttu-id="f9966-144">`dotnet restore` コマンドを実行する前に、次の 2 つの追加手順を実行する必要があります([注記参照](#dotnet-restore-note))。</span><span class="sxs-lookup"><span data-stu-id="f9966-144">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="f9966-145">*csproj* ファイルの `<ItemGroup>` セクションに、必要なサードパーティ ライブラリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="f9966-145">Add references to required third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="f9966-146">次の `<ItemGroup>` セクションには、サードパーティ ライブラリとして [Json.NET](http://www.newtonsoft.com/json) への依存関係があります。</span><span class="sxs-lookup"><span data-stu-id="f9966-146">The following `<ItemGroup>` section contains a dependency on [Json.NET](http://www.newtonsoft.com/json) as a third-party library:</span></span>

      ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
      ```

1. <span data-ttu-id="f9966-147">サードパーティの依存関係を含む NuGet パッケージをまだダウンロードしていない場合は、ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f9966-147">If you haven't already, download the NuGet package containing the third-party dependency.</span></span> <span data-ttu-id="f9966-148">パッケージをダウンロードするには、依存関係を追加した後で `dotnet restore` コマンドを実行します ([注記参照](#dotnet-restore-note))。</span><span class="sxs-lookup"><span data-stu-id="f9966-148">To download the package, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="f9966-149">発行時に依存関係はローカルの NuGet キャッシュからが解決されるので、システムで使用可能になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9966-149">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="f9966-150">サードパーティの依存関係を含む、フレームワークに依存する展開は、サードパーティの依存関係と同じ移植性を持つことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f9966-150">Note that a framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="f9966-151">たとえば、サードパーティ ライブラリが macOS のみをサポートする場合、そのアプリを Windows システムに移植することはできません。</span><span class="sxs-lookup"><span data-stu-id="f9966-151">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="f9966-152">この状況は、サードパーティの依存関係自体がネイティブ コードに依存する場合に生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f9966-152">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="f9966-153">このよい例は、[libuv](https://github.com/libuv/libuv) に対してネイティブの依存関係が必要な [Kestrel サーバー](/aspnet/core/fundamentals/servers/kestrel)です。</span><span class="sxs-lookup"><span data-stu-id="f9966-153">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="f9966-154">このようなサードパーティの依存関係を含むアプリケーションに対して FDD が作成されると、発行された出力には、ネイティブの依存関係がサポートする (そして、その NuGet パッケージ内に存在する) 各[ランタイム識別子 (RID)](../rid-catalog.md) のフォルダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f9966-154">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <a name="simpleSelf"></a> <span data-ttu-id="f9966-155">サードパーティの依存関係を含まない、自己完結型の展開</span><span class="sxs-lookup"><span data-stu-id="f9966-155">Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="f9966-156">サードパーティの依存関係を含まない自己完結型の展開を展開するプロセスには、プロジェクトの作成、*csproj* ファイルの変更、アプリのビルド、テスト、および発行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f9966-156">Deploying a self-contained deployment without third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="f9966-157">C# で記述された次の単純な例は、このプロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="f9966-157">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="f9966-158">この例では、コマンド ラインから [dotnet ユーティリティ](../tools/dotnet.md)を使用して、自己完結型の展開を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f9966-158">The example shows how to create a self-contained deployment using the [dotnet utility](../tools/dotnet.md) from the command line.</span></span>

1. <span data-ttu-id="f9966-159">プロジェクトのディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9966-159">Create a directory for the project.</span></span>

   <span data-ttu-id="f9966-160">プロジェクトのディレクトリを作成し、それを現在のディレクトリにします。</span><span class="sxs-lookup"><span data-stu-id="f9966-160">Create a directory for your project, and make it your current directory.</span></span>

1. <span data-ttu-id="f9966-161">プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9966-161">Create the project.</span></span>

   <span data-ttu-id="f9966-162">コマンド ラインに [dotnet new console](../tools/dotnet-new.md) と入力して、そのディレクトリに新しい C# コンソール プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9966-162">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="f9966-163">アプリケーションのソース コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f9966-163">Add the application's source code.</span></span>

   <span data-ttu-id="f9966-164">エディターで *Program.cs* ファイルを開き、自動生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f9966-164">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="f9966-165">テキストの入力を求めるプロンプトが表示されてから、ユーザーが入力した個々の単語が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9966-165">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="f9966-166">正規表現 `\w+` を使用して、入力テキストの単語を分離します。</span><span class="sxs-lookup"><span data-stu-id="f9966-166">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]
1. <span data-ttu-id="f9966-167">アプリの対象プラットフォームを定義します。</span><span class="sxs-lookup"><span data-stu-id="f9966-167">Define the platforms that your app will target.</span></span>

   <span data-ttu-id="f9966-168">*csproj* ファイルで、アプリが対象とするプラットフォームを定義する `<RuntimeIdentifiers>` タグを `<PropertyGroup>` セクションに作成し、対象とする各プラットフォームのランタイム識別子 (RID) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9966-168">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets and specify the runtime identifier (RID) for each platform that you target.</span></span> <span data-ttu-id="f9966-169">なお、RID の分離にはセミコロンを追加する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f9966-169">Note that you also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="f9966-170">ランタイム識別子の一覧については、「[Runtime IDentifier catalog](../rid-catalog.md)」 (ランタイム識別子のカタログ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9966-170">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span>

   <span data-ttu-id="f9966-171">たとえば、次の `<PropertyGroup>` セクションは、アプリが 64 ビット Windows 10 オペレーティング システムおよび 64 ビット OS X バージョン 10.11 オペレーティング システムで実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="f9966-171">For example, the following `<PropertyGroup>` section indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

     ```xml
     <PropertyGroup>
         <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
     </PropertyGroup>
     ```

   <span data-ttu-id="f9966-172">`<RuntimeIdentifiers>` 要素は、*csproj* ファイルの任意の `<PropertyGroup>` に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f9966-172">Note that the `<RuntimeIdentifiers>` element can appear in any `<PropertyGroup>` in your *csproj* file.</span></span> <span data-ttu-id="f9966-173">*csproj* ファイルの完全なサンプルは、このセクションの後の部分で示しています。</span><span class="sxs-lookup"><span data-stu-id="f9966-173">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="f9966-174">プロジェクトの依存関係とツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="f9966-174">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="f9966-175">[dotnet restore](../tools/dotnet-restore.md) コマンドを実行して、プロジェクトで指定された依存関係を復元します ([注記参照](#dotnet-restore-note))。</span><span class="sxs-lookup"><span data-stu-id="f9966-175">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="f9966-176">グローバリゼーション インバリアント モードを使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f9966-176">Determine whether you want to use globalization invariant mode.</span></span>

   <span data-ttu-id="f9966-177">特にアプリの対象が Linux の場合、[グローバリゼーション インバリアント モード](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md)を活用することで展開の合計サイズを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="f9966-177">Particularly if your app targets Linux, you can reduce the total size of your deployment by taking advantage of [globalization invariant mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span></span> <span data-ttu-id="f9966-178">グローバリゼーション インバリアント モードは、全世界を意識するものではなく、[インバリアント カルチャ](xref:System.Globalization.CultureInfo.InvariantCulture)の書式設定規則、大文字/小文字の区別規則、文字列比較、並べ替え順序を使用できるアプリケーションにとって便利です。</span><span class="sxs-lookup"><span data-stu-id="f9966-178">Globalization invariant mode is useful for applications that are not globally aware and that can use the formatting conventions, casing conventions, and string comparison and sort order of the [invariant culture](xref:System.Globalization.CultureInfo.InvariantCulture).</span></span>

   <span data-ttu-id="f9966-179">インバリアント モードを有効にするには、**ソリューション エクスプローラー**で (ソリューションではなく) プロジェクトを右クリックし、**[SCD.csproj の編集]** または **[SCD.vbproj の編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9966-179">To enable invariant mode, right-click on your project (not the solution) in **Solution Explorer**, and select **Edit SCD.csproj** or **Edit SCD.vbproj**.</span></span> <span data-ttu-id="f9966-180">次の強調表示された行をファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="f9966-180">Then add the following highlighted lines to the file:</span></span>

 [!code-xml[globalization-invariant-mode](~/samples/snippets/core/deploying/xml/invariant.csproj)]

1. <span data-ttu-id="f9966-181">アプリのデバッグ ビルドを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9966-181">Create a Debug build of your app.</span></span>

   <span data-ttu-id="f9966-182">コマンド ラインから、[dotnet build](../tools/dotnet-build.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9966-182">From the command line, use the [dotnet build](../tools/dotnet-build.md) command.</span></span>

1. <span data-ttu-id="f9966-183">プログラムをデバッグしてテストしたら、アプリと共に展開するファイルをアプリの対象のプラットフォームごとに作成します。</span><span class="sxs-lookup"><span data-stu-id="f9966-183">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="f9966-184">両方の対象プラットフォームに、次のように `dotnet publish` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9966-184">Use the `dotnet publish` command for both target platforms as follows:</span></span>

      ```console
      dotnet publish -c Release -r win10-x64
      dotnet publish -c Release -r osx.10.11-x64
      ```

   <span data-ttu-id="f9966-185">これにより、各ターゲット プラットフォームに対してアプリのリリース (デバッグではなく) バージョンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f9966-185">This creates a Release (rather than a Debug) version of your app for each target platform.</span></span> <span data-ttu-id="f9966-186">作成されたファイルは、プロジェクトの *.\bin\Release\netcoreapp2.1\<runtime_identifier>* サブディレクトリにある *publish* という名前のサブディレクトリに配置されます。</span><span class="sxs-lookup"><span data-stu-id="f9966-186">The resulting files are placed in a subdirectory named *publish* that's in a subdirectory of your project's *.\bin\Release\netcoreapp2.1\<runtime_identifier>* subdirectory.</span></span> <span data-ttu-id="f9966-187">各サブディレクトリには、アプリの起動に必要なファイルの完全なセット (アプリ ファイルとすべての .NET Core ファイルの両方) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9966-187">Note that each subdirectory contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="f9966-188">アプリケーションのファイルと共に、発行プロセスは、アプリに関するデバッグ情報を含むプログラム データベース (.pdb) ファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="f9966-188">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="f9966-189">このファイルは、主に例外のデバッグに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f9966-189">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="f9966-190">これを、アプリケーションのファイルにはパッケージ化しないよう選択できます。</span><span class="sxs-lookup"><span data-stu-id="f9966-190">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="f9966-191">ただし、アプリのリリース ビルドをデバッグする場合のために、保存しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f9966-191">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="f9966-192">発行したファイルは、任意の方法で展開できます。</span><span class="sxs-lookup"><span data-stu-id="f9966-192">Deploy the published files in any way you like.</span></span> <span data-ttu-id="f9966-193">たとえば、Zip ファイルにパッケージ化したり、単純な `copy` コマンドを使用したり、任意のインストール パッケージで展開したりできます。</span><span class="sxs-lookup"><span data-stu-id="f9966-193">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="f9966-194">このプロジェクトの完全な *csproj* ファイルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f9966-194">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="f9966-195">サードパーティの依存関係を含む、自己完結型の展開</span><span class="sxs-lookup"><span data-stu-id="f9966-195">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="f9966-196">1 つまたは複数のサードパーティの依存関係を含む自己完結型の展開を展開するプロセスには、依存関係の追加が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f9966-196">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="f9966-197">`dotnet restore` コマンドを実行する前に、次の 2 つの追加手順を実行する必要があります([注記参照](#dotnet-restore-note))。</span><span class="sxs-lookup"><span data-stu-id="f9966-197">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="f9966-198">任意のサードパーティ ライブラリへの参照を *csproj* ファイルの `<ItemGroup>` セクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f9966-198">Add references to any third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="f9966-199">次の `<ItemGroup>` セクションは、サードパーティ ライブラリとして Json.NET を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9966-199">The following `<ItemGroup>` section uses Json.NET as a third-party library.</span></span>

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
    ```

1. <span data-ttu-id="f9966-200">サードパーティの依存関係を含む NuGet パッケージをシステムにまだダウンロードしていない場合は、ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f9966-200">If you haven't already, download the NuGet package containing the third-party dependency to your system.</span></span> <span data-ttu-id="f9966-201">依存関係をアプリで使用できるようにするには、依存関係を追加してから、`dotnet restore` コマンドを実行します ([注記参照](#dotnet-restore-note))。</span><span class="sxs-lookup"><span data-stu-id="f9966-201">To make the dependency available to your app, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="f9966-202">発行時に依存関係はローカルの NuGet キャッシュからが解決されるので、システムで使用可能になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9966-202">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="f9966-203">このプロジェクトの完全な *csproj* ファイルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f9966-203">The following is the complete *csproj* file for this project:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="f9966-204">アプリケーションを展開すると、アプリで使用されるすべてのサードパーティの依存関係も、アプリケーション ファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9966-204">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="f9966-205">アプリが実行されているシステムには、サードパーティ ライブラリは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f9966-205">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="f9966-206">サードパーティ ライブラリを含む自己完結型の展開は、そのライブラリでサポートされるプラットフォームにのみ展開できます。</span><span class="sxs-lookup"><span data-stu-id="f9966-206">Note that you can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="f9966-207">これは、フレームワークに依存する展開にサード パーティの依存関係とネイティブの依存関係があり、ネイティブの依存関係はアプリがインストールされたプラットフォームと対応している必要がある場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="f9966-207">This is similar to having third-party dependencies with native dependencies in a framework-dependent deployment, where the native dependencies must be compatible with the platform to which the app is deployed.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

## <a name="see-also"></a><span data-ttu-id="f9966-208">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9966-208">See also</span></span>

* [<span data-ttu-id="f9966-209">.NET Core アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="f9966-209">.NET Core Application Deployment</span></span>](index.md)
* [<span data-ttu-id="f9966-210">.NET Core のランタイム識別子 (RID) のカタログ</span><span class="sxs-lookup"><span data-stu-id="f9966-210">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

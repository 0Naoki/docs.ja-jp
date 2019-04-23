---
title: '方法: インストールされている .NET Framework バージョンを確認する'
ms.date: 04/02/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 364d28d5df8e284445d825fbbeb963c54b7b9e27
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176307"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="340a2-102">方法: インストールされている .NET Framework バージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="340a2-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="340a2-103">ユーザーはコンピューターに複数のバージョンの .NET Framework を[インストール](https://docs.microsoft.com/dotnet/framework/install)して実行できます。</span><span class="sxs-lookup"><span data-stu-id="340a2-103">Users can [install](https://docs.microsoft.com/dotnet/framework/install) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="340a2-104">アプリを開発または配置する場合、どのバージョンの .NET Framework がユーザーのコンピューターにインストールされているかを確認しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="340a2-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> 

<span data-ttu-id="340a2-105">.NET Framework は、個別にバージョン管理される 2 つの主要コンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="340a2-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
- <span data-ttu-id="340a2-106">アプリに機能を提供する型やリソースのコレクションである一連のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="340a2-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="340a2-107">.NET Framework とアセンブリは同じバージョン番号を共有します。</span><span class="sxs-lookup"><span data-stu-id="340a2-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
- <span data-ttu-id="340a2-108">アプリのコードを管理および実行する共通言語ランタイム (CLR)。</span><span class="sxs-lookup"><span data-stu-id="340a2-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="340a2-109">CLR は独自のバージョン番号で識別されます (「[バージョンおよび依存関係](~/docs/framework/migration-guide/versions-and-dependencies.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="340a2-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  

> [!NOTE]
> <span data-ttu-id="340a2-110">新しい各バージョンの .NET Framework には、1 つ前のバージョンの機能が含まれると共に、新機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="340a2-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="340a2-111">同じコンピューターに .NET Framework の複数のバージョンを同時に読み込むことができます。これは、以前のバージョンをアンインストールせずに、.NET Framework をインストールできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="340a2-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="340a2-112">一般に、以前の .NET Framework のバージョンはアンインストールしないでください。使用するアプリケーションが特定のバージョンに依存しており、そのバージョンが削除されると破損してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="340a2-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="340a2-113">.NET Framework のバージョンと CLR のバージョンの間には違いがあります。</span><span class="sxs-lookup"><span data-stu-id="340a2-113">There is a difference between the .NET Framework version and the CLR version:</span></span> 
> - <span data-ttu-id="340a2-114">.NET Framework は、.NET Framework のクラス ライブラリを構成するアセンブリのセットに基づいてバージョン管理されています。</span><span class="sxs-lookup"><span data-stu-id="340a2-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="340a2-115">たとえば、.NET Framework のバージョンには、4.5、4.6.1、および 4.7.2 が含まれます。</span><span class="sxs-lookup"><span data-stu-id="340a2-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span> 
>- <span data-ttu-id="340a2-116">CLR は、.NET Framework アプリケーションが実行されているランタイムに基づいてバージョン管理されています。</span><span class="sxs-lookup"><span data-stu-id="340a2-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="340a2-117">1 つの CLR バージョンは、通常複数の NET Framework バージョンをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="340a2-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="340a2-118">たとえば、CLR バージョン 4.0.30319.*xxxxx* は .NET Framework バージョン 4 から 4.5.2 をサポートしており、CLR バージョン 4.0.30319.42000 は .NET Framework 4.6 以降をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="340a2-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2 and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span> 
>
> <span data-ttu-id="340a2-119">バージョンの詳細については、「[.NET Framework のバージョンおよび依存関係](versions-and-dependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="340a2-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>

<span data-ttu-id="340a2-120">コンピューターにインストールされている .NET Framework のバージョンの一覧を取得するには、レジストリにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="340a2-120">To get a list of the .NET Framework versions installed on a computer, you access the registry.</span></span> <span data-ttu-id="340a2-121">レジストリを確認するには、レジストリ エディタを使用するか、次に従ってコードで照会します。</span><span class="sxs-lookup"><span data-stu-id="340a2-121">You can either use the Registry Editor to view the registry or use code to query it:</span></span>
 
- <span data-ttu-id="340a2-122">.NET Framework の新しいバージョンを探す (4.5 以降):</span><span class="sxs-lookup"><span data-stu-id="340a2-122">Find newer .NET Framework versions (4.5 and later):</span></span> 
     - [<span data-ttu-id="340a2-123">レジストリ エディターを使用し .NET Framework のバージョンを探す</span><span class="sxs-lookup"><span data-stu-id="340a2-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)  
     - [<span data-ttu-id="340a2-124">コードを使用し .NET Framework のバージョンのレジストリを照会する</span><span class="sxs-lookup"><span data-stu-id="340a2-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)  
     - [<span data-ttu-id="340a2-125">PowerShell を使用し .NET Framework のバージョンのレジストリを照会する</span><span class="sxs-lookup"><span data-stu-id="340a2-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)
- <span data-ttu-id="340a2-126">.NET Framework の古いバージョンを探す (1 から 4):</span><span class="sxs-lookup"><span data-stu-id="340a2-126">Find older .NET Framework versions (1&#8211;4):</span></span>
     - [<span data-ttu-id="340a2-127">レジストリ エディターを使用し .NET Framework のバージョンを探す</span><span class="sxs-lookup"><span data-stu-id="340a2-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
     - [<span data-ttu-id="340a2-128">コードを使用し .NET Framework のバージョンのレジストリを照会する</span><span class="sxs-lookup"><span data-stu-id="340a2-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)   

<span data-ttu-id="340a2-129">コンピューターにインストールされている CLR のバージョンの一覧を取得するには、次のツールまたはコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="340a2-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>  
  
- [<span data-ttu-id="340a2-130">Clrver ツールを使用する</span><span class="sxs-lookup"><span data-stu-id="340a2-130">Use the Clrver tool</span></span>](#clr_a)  
- [<span data-ttu-id="340a2-131">コードを使用して Environment クラスを照会する</span><span class="sxs-lookup"><span data-stu-id="340a2-131">Use code to query the Environment class</span></span>](#clr_b)  

<span data-ttu-id="340a2-132">.NET Framework の各バージョン用にインストールされている更新プログラムの検出については、「[方法:インストールされている .NET Framework の更新プログラムを確認する](how-to-determine-which-net-framework-updates-are-installed.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="340a2-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span> 

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="340a2-133">.NET Framework の新しいバージョンを探す (4.5 以降)</span><span class="sxs-lookup"><span data-stu-id="340a2-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<a name="net_b"></a> 
### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="340a2-134">レジストリで .NET Framework バージョン 4.5 以降を探す</span><span class="sxs-lookup"><span data-stu-id="340a2-134">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="340a2-135">**スタート** メニューの **[ファイル名を指定して実行]** を選択し、「*regedit*」と入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="340a2-135">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="340a2-136">regedit を実行するには、管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="340a2-136">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="340a2-137">レジストリ エディターで、次のサブキーを開きます。**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**</span><span class="sxs-lookup"><span data-stu-id="340a2-137">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="340a2-138">**Full** サブキーが存在しない場合は、.NET Framework 4.5 以降はインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="340a2-138">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="340a2-139">レジストリの **NET Framework セットアップ** フォルダーの先頭はピリオドでは "*ありません*"。</span><span class="sxs-lookup"><span data-stu-id="340a2-139">The **NET Framework Setup** folder in the registry does *not* begin with a period.</span></span>

3. <span data-ttu-id="340a2-140">**Release** という DWORD のエントリを探します。</span><span class="sxs-lookup"><span data-stu-id="340a2-140">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="340a2-141">それがある場合、.NET Framework 4.5 以降のバージョンがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="340a2-141">If it exists, then you have .NET Framework 4.5 or later versions installed.</span></span> <span data-ttu-id="340a2-142">その値は、.NET Framework の特定のバージョンのリリース キーです。</span><span class="sxs-lookup"><span data-stu-id="340a2-142">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="340a2-143">たとえば、次の図では、**Release** エントリの値は *378389* で、これは .NET Framework 4.5 のリリース キーです。</span><span class="sxs-lookup"><span data-stu-id="340a2-143">In the following figure, for example, the value of the **Release** entry is *378389*, which is the release key for .NET Framework 4.5.</span></span> 

     <span data-ttu-id="340a2-144">![.NET Framework 4.5 のレジストリ エントリ](media/clr-installdir.png ".NET Framework 4.5 のレジストリ エントリ")</span><span class="sxs-lookup"><span data-stu-id="340a2-144">![Registry entry for the .NET Framework 4.5](media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="340a2-145">次の表は、.NET Framework 4.5 以降のバージョンに対する個々のオペレーティング システムでの **Release** DWORD 値の一覧です。</span><span class="sxs-lookup"><span data-stu-id="340a2-145">The following table lists the value of the **Release** DWORD on individual operating systems for .NET Framework 4.5 and later versions.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="340a2-146">.NET Framework のバージョン</span><span class="sxs-lookup"><span data-stu-id="340a2-146">.NET Framework version</span></span>|<span data-ttu-id="340a2-147">Release DWORD の値</span><span class="sxs-lookup"><span data-stu-id="340a2-147">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="340a2-148">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="340a2-148">.NET Framework 4.5</span></span>|<span data-ttu-id="340a2-149">すべての Windows オペレーティング システム:378389</span><span class="sxs-lookup"><span data-stu-id="340a2-149">All Windows operating systems: 378389</span></span>|
|<span data-ttu-id="340a2-150">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="340a2-150">.NET Framework 4.5.1</span></span>|<span data-ttu-id="340a2-151">Windows 8.1 および Windows Server 2012 R2:378675</span><span class="sxs-lookup"><span data-stu-id="340a2-151">On Windows 8.1 and Windows Server 2012 R2: 378675</span></span><br /><span data-ttu-id="340a2-152">他のすべての Windows オペレーティング システム:378758</span><span class="sxs-lookup"><span data-stu-id="340a2-152">On all other Windows operating systems: 378758</span></span>|
|<span data-ttu-id="340a2-153">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="340a2-153">.NET Framework 4.5.2</span></span>|<span data-ttu-id="340a2-154">すべての Windows オペレーティング システム:379893</span><span class="sxs-lookup"><span data-stu-id="340a2-154">All Windows operating systems: 379893</span></span>|
|<span data-ttu-id="340a2-155">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="340a2-155">.NET Framework 4.6</span></span>|<span data-ttu-id="340a2-156">Windows 10:393295</span><span class="sxs-lookup"><span data-stu-id="340a2-156">On Windows 10: 393295</span></span><br /><span data-ttu-id="340a2-157">他のすべての Windows オペレーティング システム:393297</span><span class="sxs-lookup"><span data-stu-id="340a2-157">On all other Windows operating systems: 393297</span></span>|
|<span data-ttu-id="340a2-158">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="340a2-158">.NET Framework 4.6.1</span></span>|<span data-ttu-id="340a2-159">Windows 10 November Update システム:394254</span><span class="sxs-lookup"><span data-stu-id="340a2-159">On Windows 10 November Update systems: 394254</span></span><br /><span data-ttu-id="340a2-160">他のすべての Windows オペレーティング システム (Windows 10 を含む):394271</span><span class="sxs-lookup"><span data-stu-id="340a2-160">On all other Windows operating systems (including Windows 10): 394271</span></span>|
|<span data-ttu-id="340a2-161">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="340a2-161">.NET Framework 4.6.2</span></span>|<span data-ttu-id="340a2-162">Windows 10 Anniversary Update および Windows Server 2016 の場合:394802</span><span class="sxs-lookup"><span data-stu-id="340a2-162">On Windows 10 Anniversary Update and Windows Server 2016: 394802</span></span><br /><span data-ttu-id="340a2-163">他のすべての Windows オペレーティング システム (他の Windows 10 オペレーティング システムを含む):394806</span><span class="sxs-lookup"><span data-stu-id="340a2-163">On all other Windows operating systems (including other Windows 10 operating systems): 394806</span></span>|
|<span data-ttu-id="340a2-164">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="340a2-164">.NET Framework 4.7</span></span>|<span data-ttu-id="340a2-165">Windows 10 Creators Update:460798</span><span class="sxs-lookup"><span data-stu-id="340a2-165">On Windows 10 Creators Update: 460798</span></span><br /><span data-ttu-id="340a2-166">他のすべての Windows オペレーティング システム (他の Windows 10 オペレーティング システムを含む):460805</span><span class="sxs-lookup"><span data-stu-id="340a2-166">On all other Windows operating systems (including other Windows 10 operating systems): 460805</span></span>| 
|<span data-ttu-id="340a2-167">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="340a2-167">.NET Framework 4.7.1</span></span>|<span data-ttu-id="340a2-168">Windows 10 Fall Creators Update および Windows Server バージョン 1709:461308</span><span class="sxs-lookup"><span data-stu-id="340a2-168">On Windows 10 Fall Creators Update and Windows Server, version 1709: 461308</span></span><br/><span data-ttu-id="340a2-169">他のすべての Windows オペレーティング システム (他の Windows 10 オペレーティング システムを含む):461310</span><span class="sxs-lookup"><span data-stu-id="340a2-169">On all other Windows operating systems (including other Windows 10 operating systems): 461310</span></span>|
|<span data-ttu-id="340a2-170">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="340a2-170">.NET Framework 4.7.2</span></span>|<span data-ttu-id="340a2-171">Windows 10 April 2018 Update および Windows Server バージョン 1803:461808</span><span class="sxs-lookup"><span data-stu-id="340a2-171">On Windows 10 April 2018 Update and Windows Server, version 1803: 461808</span></span><br/><span data-ttu-id="340a2-172">Windows 10 April 2018 Update および Windows Server バージョン 1803 以外のすべての Windows オペレーティング システム:461814</span><span class="sxs-lookup"><span data-stu-id="340a2-172">On all Windows operating systems other than Windows 10 April 2018 Update and Windows Server, version 1803: 461814</span></span>|  

<span data-ttu-id="340a2-173">これらの値は次のように使用できます。</span><span class="sxs-lookup"><span data-stu-id="340a2-173">You can use these values as follows:</span></span>

- <span data-ttu-id="340a2-174">特定のバージョンの .NET Framework が特定のバージョンの Windows オペレーティング システムにインストールされているかどうかを判断するには、**Release** DWORD 値が表に記載されている値と "*同じ*" であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="340a2-174">To determine whether a specific version of the .NET Framework is installed on a particular version of the Windows operating system, test whether the **Release** DWORD value is *equal to* the value listed in the table.</span></span> <span data-ttu-id="340a2-175">たとえば、.NET Framework 4.6 が Windows 10 システム上に存在するかどうかを判断するには、**Release** 値が 393295 と "*同じ*" であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="340a2-175">For example, to determine whether .NET Framework 4.6 is present on a Windows 10 system, test for the a **Release** value that is *equal to* 393295.</span></span>

- <span data-ttu-id="340a2-176">.NET Framework の最小バージョンが存在するかどうかを判断するには、そのバージョン用の小さい **RELEASE** DWORD 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="340a2-176">To determine whether a minimum version of the .NET Framework is present, use the smaller **RELEASE** DWORD value for that version.</span></span> <span data-ttu-id="340a2-177">たとえば、アプリケーションが .NET Framework 4.6 以降のバージョンで実行されている場合、**RELEASE** DWORD 値が 393295 "*以上*" であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="340a2-177">For example, if your application runs under .NET Framework 4.6 or a later version, test for a **RELEASE** DWORD value that is *greater than or equal to* 393295.</span></span> <span data-ttu-id="340a2-178">各 .NET Framework バージョンの最小 **RELEASE** DWORD 値のみが記載された表については、「[The minimum values of the Release DWORD for .NET Framework 4.5 and later versions (.NET Framework 4.5 以降のバージョン用の Release DWORD の最小値)](minimum-release-dword.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="340a2-178">For a table that lists only the minimum **RELEASE** DWORD value for each .NET Framework version, see [The minimum values of the Release DWORD for .NET Framework 4.5 and later versions](minimum-release-dword.md).</span></span>

- <span data-ttu-id="340a2-179">複数のバージョンを確認するには、まず、値が最新の .NET Framework バージョン用の小さい DWORD 値 "*以上*" であることを確認してから、その値と、それよりも以前のバージョン用の小さい DWORD 値を順番に比較します。</span><span class="sxs-lookup"><span data-stu-id="340a2-179">To test for multiple versions, begin by testing for a value that is *greater than or equal to* the smaller DWORD value for the latest .NET Framework version, and then compare the value with the smaller DWORD value for each successive earlier version.</span></span> <span data-ttu-id="340a2-180">たとえば、アプリケーションに .NET Framework 4.7 以降が必要で、存在する .NET Framework の特定のバージョンを確認する場合は、461808 (.NET Framework 4.7.2 用の小さい DWORD 値) "*以上*" の **RELEASE** DWORD 値であることの確認から始めます。</span><span class="sxs-lookup"><span data-stu-id="340a2-180">For example, if your application requires .NET Framework 4.7 or later and you want to determine the specific version of .NET Framework present, start by testing for a **RELEASE** DWORD value that is *great than or equal to* to 461808 (the smaller DWORD value for .NET Framework 4.7.2).</span></span> <span data-ttu-id="340a2-181">次に、**RELEASE** DWORD 値と、以降の各 .NET Framework バージョン用の小さい値と比較します。</span><span class="sxs-lookup"><span data-stu-id="340a2-181">Then compare the **RELEASE** DWORD value with the smaller value for each later .NET Framework version.</span></span> <span data-ttu-id="340a2-182">各 .NET Framework バージョンの最小 **RELEASE** DWORD 値のみが記載された表については、「[The minimum values of the Release DWORD for .NET Framework 4.5 and later versions (.NET Framework 4.5 以降のバージョン用の Release DWORD の最小値)](minimum-release-dword.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="340a2-182">For a table that lists only the minimum **RELEASE** DWORD value for each .NET Framework version, see [The minimum values of the Release DWORD for .NET Framework 4.5 and later versions](minimum-release-dword.md).</span></span>

<a name="net_d"></a> 
### <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="340a2-183">コードで .NET Framework バージョン 4.5 以降を探す</span><span class="sxs-lookup"><span data-stu-id="340a2-183">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="340a2-184"><xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> メソッドと <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> メソッドを使用し、Windows レジストリの **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** サブキーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="340a2-184">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

    <span data-ttu-id="340a2-185">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** サブキーに **Release** DWORD があるということは、コンピューターに .NET Framework 4.5 以降のバージョンがインストールされていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="340a2-185">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span> 

2. <span data-ttu-id="340a2-186">**Release** エントリの値を確認して、インストールされているバージョンを判断します。</span><span class="sxs-lookup"><span data-stu-id="340a2-186">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="340a2-187">上位互換性があるかを確認するには、[.NET Framework のバージョンの表](#version_table)で示されている値以上の値があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="340a2-187">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="340a2-188">次の例では、レジストリから **Release** の値を確認し、インストールされている .NET Framework 4.5 以降のバージョンを探しています。</span><span class="sxs-lookup"><span data-stu-id="340a2-188">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="340a2-189">この例では、バージョンのチェックで推奨されている方法に従います。</span><span class="sxs-lookup"><span data-stu-id="340a2-189">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="340a2-190">**Release** エントリの値が、既知のリリース キー値*以上*かどうかを確認しています。</span><span class="sxs-lookup"><span data-stu-id="340a2-190">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="340a2-191">最新バージョンから最も古いバージョンの順にチェックします。</span><span class="sxs-lookup"><span data-stu-id="340a2-191">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="340a2-192">PowerShell を使用して最低限必要な .NET Framework のバージョン (4.5 以降) を確認する</span><span class="sxs-lookup"><span data-stu-id="340a2-192">Check for a minimum-required .NET Framework version (4.5 and later) with PowerShell</span></span>

- <span data-ttu-id="340a2-193">PowerShell コマンドを使用し、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** サブキーから **Release** エントリの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="340a2-193">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="340a2-194">次の例では、**Release** エントリの値を確認して、.NET Framework 4.6.2 以降がインストールされているかどうかを判断しています。</span><span class="sxs-lookup"><span data-stu-id="340a2-194">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="340a2-195">このコードでは、インストールされていない場合は、`True` が返され、されている場合は `False` が返されます。</span><span class="sxs-lookup"><span data-stu-id="340a2-195">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
# PowerShell 5
 Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' |  Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
 ```

```PowerShell
# PowerShell 4
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="340a2-196">さまざまな必要最低限の .NET Framework バージョンを確認するには、これらの例の *394802* を [.NET Framework のバージョンの表](#version_table)の **Release** 値と置き換えます。</span><span class="sxs-lookup"><span data-stu-id="340a2-196">To check for a different minimum-required .NET Framework version, replace *394802* in these examples with a **Release** value from the [.NET Framework version table](#version_table).</span></span>

## <a name="find-older-net-framework-versions-182114"></a><span data-ttu-id="340a2-197">.NET Framework の古いバージョンを探す (1 から 4)</span><span class="sxs-lookup"><span data-stu-id="340a2-197">Find older .NET Framework versions (1&#8211;4)</span></span>

<a name="net_a"></a>
### <a name="find-net-framework-versions-182114-in-the-registry"></a><span data-ttu-id="340a2-198">レジストリで .NET Framework バージョン 1 から 4 を探す</span><span class="sxs-lookup"><span data-stu-id="340a2-198">Find .NET Framework versions 1&#8211;4 in the registry</span></span> 
  
1. <span data-ttu-id="340a2-199">**スタート** メニューの **[ファイル名を指定して実行]** を選択し、「*regedit*」と入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="340a2-199">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>
  
    <span data-ttu-id="340a2-200">regedit を実行するには、管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="340a2-200">You must have administrative credentials to run regedit.</span></span>  

2. <span data-ttu-id="340a2-201">レジストリ エディターで、次のサブキーを開きます。**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span><span class="sxs-lookup"><span data-stu-id="340a2-201">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>  

    - <span data-ttu-id="340a2-202">.NET Framework バージョン 1.1 から 3.5 では、インストールされている各バージョンは **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** サブキーの下にサブキーとして列挙されます。</span><span class="sxs-lookup"><span data-stu-id="340a2-202">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="340a2-203">たとえば、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5** です。</span><span class="sxs-lookup"><span data-stu-id="340a2-203">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="340a2-204">バージョン番号は、バージョン サブキーの **Version** エントリに値として格納されています。</span><span class="sxs-lookup"><span data-stu-id="340a2-204">The version number is stored as a value in the version subkey's **Version** entry.</span></span> 
     
    - <span data-ttu-id="340a2-205">.NET Framework 4 では、**Version** エントリは、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** サブキー、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** サブキーまたは両サブキーの下にあります。</span><span class="sxs-lookup"><span data-stu-id="340a2-205">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="340a2-206">レジストリの **NET Framework セットアップ** フォルダーの先頭はピリオドではありません。</span><span class="sxs-lookup"><span data-stu-id="340a2-206">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="340a2-207">次の図では、.NET Framework 3.5 のサブキーとその **Version** エントリを示しています。</span><span class="sxs-lookup"><span data-stu-id="340a2-207">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="340a2-208">![.NET Framework 3.5 のレジストリ エントリ。](media/net-4-and-earlier.png ".NET Framework 3.5 以前のバージョン")</span><span class="sxs-lookup"><span data-stu-id="340a2-208">![The registry entry for the .NET Framework 3.5.](media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a> 
### <a name="find-net-framework-versions-182114-with-code"></a><span data-ttu-id="340a2-209">コードで .NET Framework バージョン 1 から 4 を探す</span><span class="sxs-lookup"><span data-stu-id="340a2-209">Find .NET Framework versions 1&#8211;4 with code</span></span>

- <span data-ttu-id="340a2-210"><xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> クラスを使用して、Windows レジストリの **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** サブキーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="340a2-210">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="340a2-211">次の例では、インストールされている .NET Framework のバージョン 1 から 4 が検索されています。</span><span class="sxs-lookup"><span data-stu-id="340a2-211">The following example finds the .NET Framework 1&#8211;4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a><span data-ttu-id="340a2-212">CLR のバージョンを探す</span><span class="sxs-lookup"><span data-stu-id="340a2-212">Find CLR versions</span></span>
  
<a name="clr_a"></a> 
### <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="340a2-213">Clrver.exe を使用して現在の CLR のバージョンを調べる</span><span class="sxs-lookup"><span data-stu-id="340a2-213">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="340a2-214">[CLR バージョン ツール (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) を使用して、コンピューターにインストールされている CLR のバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="340a2-214">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="340a2-215">[Visual Studio 用開発者コマンド プロンプト](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs)で「`clrver`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="340a2-215">From a [Developer Command Prompt for Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs), enter `clrver`.</span></span>

    <span data-ttu-id="340a2-216">出力例:</span><span class="sxs-lookup"><span data-stu-id="340a2-216">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a> 
### <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="340a2-217">Environment クラスを使用して現在の CLR のバージョンを調べる</span><span class="sxs-lookup"><span data-stu-id="340a2-217">Find the current CLR version with the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="340a2-218">.NET Framework 4.5 以降のバージョンでは、CLR のバージョンの検出に <xref:System.Environment.Version%2A?displayProperty=nameWithType> プロパティを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="340a2-218">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="340a2-219">代わりに、「[コードで .NET Framework バージョン 4.5 以降を探す](#net_d)」の説明に従い、レジストリを照会します。</span><span class="sxs-lookup"><span data-stu-id="340a2-219">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="340a2-220"><xref:System.Environment.Version?displayProperty=nameWithType> プロパティを照会し、<xref:System.Version> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="340a2-220">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span> 

    <span data-ttu-id="340a2-221">返された `System.Version` オブジェクトは、現在コードを実行しているランタイムのバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="340a2-221">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="340a2-222">コンピューターにインストールされている可能性のある、アセンブリのバージョンやランタイムのその他のバージョンは返されません。</span><span class="sxs-lookup"><span data-stu-id="340a2-222">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="340a2-223">.NET Framework バージョン 4、4.5、4.5.1、および 4.5.2 の場合は、返される <xref:System.Version> オブジェクトの文字列表現は 4.0.30319.*xxxxx* という形式です。</span><span class="sxs-lookup"><span data-stu-id="340a2-223">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*.</span></span> <span data-ttu-id="340a2-224">.NET Framework 4.6 以降のバージョンの場合は、4.0.30319.42000 という形式です。</span><span class="sxs-lookup"><span data-stu-id="340a2-224">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>    

2. <span data-ttu-id="340a2-225">`Version` オブジェクトを取得したら、次のように照会します。</span><span class="sxs-lookup"><span data-stu-id="340a2-225">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="340a2-226">メジャー リリース識別子 (たとえば、バージョン 4.0 の場合の *4*) には、<xref:System.Version.Major%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="340a2-226">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="340a2-227">マイナー リリース識別子 (たとえば、バージョン 4.0 の場合の *0*) には、<xref:System.Version.Minor%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="340a2-227">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="340a2-228">バージョンの完全な文字列 (たとえば、*4.0.30319.18010*) には、<xref:System.Version.ToString%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="340a2-228">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="340a2-229">このメソッドでは、コードを実行しているランタイムのバージョンを示す値が 1 つ返されます。</span><span class="sxs-lookup"><span data-stu-id="340a2-229">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="340a2-230">コンピューターにインストールされている可能性のあるアセンブリ バージョンやその他のランタイム バージョンは返されません。</span><span class="sxs-lookup"><span data-stu-id="340a2-230">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>

<span data-ttu-id="340a2-231">次の例では、<xref:System.Environment.Version%2A?displayProperty=nameWithType> プロパティを使用して CLR バージョンの情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="340a2-231">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="340a2-232">関連項目</span><span class="sxs-lookup"><span data-stu-id="340a2-232">See also</span></span>

- [<span data-ttu-id="340a2-233">方法: インストールされている .NET Framework の更新プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="340a2-233">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="340a2-234">開発者向けの .NET Framework のインストール</span><span class="sxs-lookup"><span data-stu-id="340a2-234">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="340a2-235">.NET Framework のバージョンおよび依存関係</span><span class="sxs-lookup"><span data-stu-id="340a2-235">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)

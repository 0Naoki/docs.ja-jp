---
title: ワークフロー サービス登録ツール (WFServicesReg.exe)
ms.date: 03/30/2017
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
ms.openlocfilehash: da377e865258169bdca16cfb0db3f8612d4e0f0d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613061"
---
# <a name="workflow-service-registration-tool-wfservicesregexe"></a><span data-ttu-id="5ca37-102">ワークフロー サービス登録ツール (WFServicesReg.exe)</span><span class="sxs-lookup"><span data-stu-id="5ca37-102">WorkFlow Service Registration Tool (WFServicesReg.exe)</span></span>
<span data-ttu-id="5ca37-103">ワークフロー サービス登録ツール (WFServicesReg.exe) は、Windows Workflow Foundation (WF) サービスの構成要素の追加、削除、または修復に使用できるスタンドアロン ツールです。</span><span class="sxs-lookup"><span data-stu-id="5ca37-103">Workflow Services Registration tool (WFServicesReg.exe) is a stand-alone tool that can be used to add, remove, or repair the configuration elements for Windows Workflow Foundation (WF) services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ca37-104">構文</span><span class="sxs-lookup"><span data-stu-id="5ca37-104">Syntax</span></span>  
  
```  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## <a name="remarks"></a><span data-ttu-id="5ca37-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="5ca37-105">Remarks</span></span>  
 <span data-ttu-id="5ca37-106">このツールは、[!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] のインストール場所である %windir%\Microsoft.NET\Framework\v3.5、または %windir%\Microsoft.NET\Framework64\v3.5 (64 ビット コンピューターの場合) にあります。</span><span class="sxs-lookup"><span data-stu-id="5ca37-106">The tool can be found at the [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installation location, specifically, %windir%\Microsoft.NET\Framework\v3.5, or at %windir%\Microsoft.NET\Framework64\v3.5 in 64-bit machines.</span></span>  
  
 <span data-ttu-id="5ca37-107">次の表は、ワークフロー サービス登録ツール (WFServicesReg.exe) で使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="5ca37-107">The following tables describe the options that can be used with the Workflow Services Registration tool (WFServicesReg.exe).</span></span>  
  
|<span data-ttu-id="5ca37-108">オプション</span><span class="sxs-lookup"><span data-stu-id="5ca37-108">Option</span></span>|<span data-ttu-id="5ca37-109">説明</span><span class="sxs-lookup"><span data-stu-id="5ca37-109">Description</span></span>|  
|------------|-----------------|  
|`/c`|<span data-ttu-id="5ca37-110">Windows ワークフロー サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="5ca37-110">Configures Windows Workflow Services.</span></span> <span data-ttu-id="5ca37-111">インストールおよび修復を行う場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="5ca37-111">Used in install and repair scenarios.</span></span>|  
|`/r`|<span data-ttu-id="5ca37-112">Windows ワークフロー サービスの構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="5ca37-112">Removes Windows Workflow Services Configuration.</span></span>|  
|`/v`|<span data-ttu-id="5ca37-113">構成または削除に関する詳細情報を印刷します。</span><span class="sxs-lookup"><span data-stu-id="5ca37-113">Print verbose information (for either configuration or removal).</span></span>|  
|`/m`|<span data-ttu-id="5ca37-114">MSI ログ形式を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5ca37-114">Enables MSI logging format.</span></span>|  
|`/i`|<span data-ttu-id="5ca37-115">アプリケーションの実行時にウィンドウを最小化します。</span><span class="sxs-lookup"><span data-stu-id="5ca37-115">Minimizes the window when the application runs.</span></span>|  
  
## <a name="registration"></a><span data-ttu-id="5ca37-116">登録</span><span class="sxs-lookup"><span data-stu-id="5ca37-116">Registration</span></span>  
 <span data-ttu-id="5ca37-117">このツールは Web.config ファイルを調べ、次の項目を登録します。</span><span class="sxs-lookup"><span data-stu-id="5ca37-117">The tool inspects the Web.config file and registers the following:</span></span>  
  
- [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] <span data-ttu-id="5ca37-118">参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="5ca37-118">reference assemblies.</span></span>  
  
- <span data-ttu-id="5ca37-119">.xoml ファイルのビルド プロバイダー</span><span class="sxs-lookup"><span data-stu-id="5ca37-119">A build provider for .xoml files.</span></span>  
  
- <span data-ttu-id="5ca37-120">.xoml ファイルおよび .rules ファイルの HTTP ハンドラー</span><span class="sxs-lookup"><span data-stu-id="5ca37-120">HTTP handlers for .xoml and .rules files.</span></span>  
  
 <span data-ttu-id="5ca37-121">このツールは Machine.config ファイルを調べ、次の拡張機能を登録します。</span><span class="sxs-lookup"><span data-stu-id="5ca37-121">The tool inspects the Machine.config file and registers the following extensions:</span></span>  
  
- <span data-ttu-id="5ca37-122">behaviorExtensions</span><span class="sxs-lookup"><span data-stu-id="5ca37-122">behaviorExtensions</span></span>  
  
- <span data-ttu-id="5ca37-123">bindingElementExtensions</span><span class="sxs-lookup"><span data-stu-id="5ca37-123">bindingElementExtensions</span></span>  
  
- <span data-ttu-id="5ca37-124">bindingExtensions</span><span class="sxs-lookup"><span data-stu-id="5ca37-124">bindingExtensions</span></span>  
  
 <span data-ttu-id="5ca37-125">さらに、次のクライアント メタデータ インポーターも登録します。</span><span class="sxs-lookup"><span data-stu-id="5ca37-125">The tool also registers the following client metadata importers:</span></span>  
  
- <span data-ttu-id="5ca37-126">policyImporters</span><span class="sxs-lookup"><span data-stu-id="5ca37-126">policyImporters</span></span>  
  
- <span data-ttu-id="5ca37-127">wsdlImporters</span><span class="sxs-lookup"><span data-stu-id="5ca37-127">wsdlImporters</span></span>  
  
 <span data-ttu-id="5ca37-128">このツールでは、IIS メタベース内の .xoml および .rules のスクリプトマップおよびハンドラーの登録も行われます。</span><span class="sxs-lookup"><span data-stu-id="5ca37-128">The tool also registers .xoml and .rules scriptmaps and handlers in the IIS metabase.</span></span>  
  
 <span data-ttu-id="5ca37-129">[!INCLUDE[ws2003](../../../includes/ws2003-md.md)] コンピューターと [!INCLUDE[wxp](../../../includes/wxp-md.md)] コンピューター (IIS 5.1 および [!INCLUDE[iis601](../../../includes/iis601-md.md)]) では、.xoml スクリプトマップと .rules スクリプトマップのセットが 1 つ登録されます。</span><span class="sxs-lookup"><span data-stu-id="5ca37-129">On [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../includes/wxp-md.md)] machines (IIS 5.1 and [!INCLUDE[iis601](../../../includes/iis601-md.md)]), one set of .xoml and .rules scriptmaps are registered.</span></span>  
  
 <span data-ttu-id="5ca37-130">64 ビット コンピューターでは、`Enable32BitAppOnWin64` スイッチが有効な場合は WOW モードのスクリプトマップが登録され、`Enable32BitAppOnWin64` スイッチが無効な場合はネイティブの 64 ビット スクリプトマップが登録されます。</span><span class="sxs-lookup"><span data-stu-id="5ca37-130">On 64-bit machines, the tool registers WOW mode scriptmaps if the `Enable32BitAppOnWin64` switch is enabled, or native 64-bit scriptmaps if the `Enable32BitAppOnWin64` switch is disabled.</span></span>  
  
 <span data-ttu-id="5ca37-131">[!INCLUDE[wv](../../../includes/wv-md.md)]および Windows Server 2008 (IIS 7.0 以降) のコンピューター、.xoml および .rules ハンドラーの 2 つのセットが登録: 統合モードとクラシック モードのいずれかのいずれか。</span><span class="sxs-lookup"><span data-stu-id="5ca37-131">On [!INCLUDE[wv](../../../includes/wv-md.md)] and Windows Server 2008 (IIS 7.0 and above) machines, two sets of .xoml and .rules handlers are registered: one for Integrated mode and one for Classic mode.</span></span>  
  
 <span data-ttu-id="5ca37-132">64 ビット コンピューターでは、`Enable32BitAppOnWin64` スイッチの状態にかかわらず、統合モード用、WOW クラシック モード用、およびネイティブ 64 ビット クラシック モード用の 3 セットのハンドラーが登録されます。</span><span class="sxs-lookup"><span data-stu-id="5ca37-132">On 64-bit machines, three sets of handlers are registered (regardless of the state of the `Enable32BitAppOnWin64` switch): one for Integrated mode, one for WOW Classic mode and one for native 64-bit Classic mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ca37-133">ServiceModelreg.exe とは異なり、WFServicesReg.exe では、特定の Web サイトのスクリプトマップまたはハンドラーの追加、削除、修復を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="5ca37-133">Unlike ServiceModelreg.exe, WFServicesReg.exe does not allow adding, removing, or repairing scriptmaps or handlers for a particular Web site.</span></span> <span data-ttu-id="5ca37-134">この問題の回避策については、「スクリプトマップの修復」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ca37-134">For a workaround to this issue, see the "Repairing the Scriptmaps" section.</span></span>  
  
## <a name="usage-scenarios"></a><span data-ttu-id="5ca37-135">使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="5ca37-135">Usage Scenarios</span></span>  
  
### <a name="installing-iis-after-net-framework-35-is-installed"></a><span data-ttu-id="5ca37-136">.NET Framework 3.5 インストール後の IIS のインストール</span><span class="sxs-lookup"><span data-stu-id="5ca37-136">Installing IIS after .NET Framework 3.5 is installed</span></span>  
 <span data-ttu-id="5ca37-137">[!INCLUDE[ws2003](../../../includes/ws2003-md.md)] コンピューターでは、IIS をインストールする前に [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5ca37-137">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] is installed prior to IIS installation.</span></span> <span data-ttu-id="5ca37-138">IIS メタベースを使用できないため、[!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] のインストールは、.xoml スクリプトマップと .rules スクリプトマップをインストールせずに正常に終了します。</span><span class="sxs-lookup"><span data-stu-id="5ca37-138">Due to the unavailability of the IIS metabase, installation of [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] succeeds without installing .xoml and .rules scriptmaps.</span></span>  
  
 <span data-ttu-id="5ca37-139">IIS をインストールした後、`/c` スイッチを指定して WFServicesReg.exe ツールを使用することで、特定のスクリプトマップをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="5ca37-139">After IIS is installed, you can use the WFServicesReg.exe tool with the `/c` switch to install these specific scriptmaps.</span></span>  
  
### <a name="repairing-the-scriptmaps"></a><span data-ttu-id="5ca37-140">スクリプトマップの修復</span><span class="sxs-lookup"><span data-stu-id="5ca37-140">Repairing the Scriptmaps</span></span>  
  
#### <a name="scriptmap-deleted-under-web-sites-node"></a><span data-ttu-id="5ca37-141">[Web サイト] ノードでスクリプトマップが削除される</span><span class="sxs-lookup"><span data-stu-id="5ca37-141">Scriptmap deleted under Web Sites node</span></span>  
 <span data-ttu-id="5ca37-142">[!INCLUDE[ws2003](../../../includes/ws2003-md.md)] コンピューターでは、[Web サイト] ノードから .xoml または .rules が誤って削除されます。</span><span class="sxs-lookup"><span data-stu-id="5ca37-142">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, .xoml or .rules is accidentally deleted from the Web Sites node.</span></span> <span data-ttu-id="5ca37-143">これは、`/c` スイッチを指定して WFServicesReg.exe ツールを実行することにより、修復できます。</span><span class="sxs-lookup"><span data-stu-id="5ca37-143">This can be repaired by running the WFServicesReg.exe tool with the `/c` switch.</span></span>  
  
#### <a name="scriptmap-deleted-under-a-particular-web-site"></a><span data-ttu-id="5ca37-144">特定の Web サイトでスクリプトマップが削除される</span><span class="sxs-lookup"><span data-stu-id="5ca37-144">Scriptmap deleted under a particular Web site</span></span>  
 <span data-ttu-id="5ca37-145">[!INCLUDE[ws2003](../../../includes/ws2003-md.md)] コンピューターでは、[Web サイト] ノードではなく、特定の Web サイト ([既定の Web サイト] など) から .xoml または .rules が誤って削除されます。</span><span class="sxs-lookup"><span data-stu-id="5ca37-145">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, .xoml or .rules is accidentally deleted from a particular Web site (for example, the Default Web Site) rather than from the Web Sites node.</span></span>  
  
 <span data-ttu-id="5ca37-146">特定の Web サイトの削除されたハンドラーを修復するには、"WFServicesReg.exe/r"を実行する必要がありますすべての Web サイトからハンドラーを削除する"WFServicesReg.exe/c"を実行し、すべての Web サイトを適切なハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5ca37-146">To repair deleted handlers for a particular Web site, you should run "WFServicesReg.exe /r" to remove handlers from all Web sites, then run "WFServicesReg.exe /c" to create the appropriate handlers for all Web sites.</span></span>  
  
### <a name="configuring-handlers-after-switching-iis-mode"></a><span data-ttu-id="5ca37-147">IIS モードの切り替え後のハンドラーの構成</span><span class="sxs-lookup"><span data-stu-id="5ca37-147">Configuring handlers after switching IIS mode</span></span>  
 <span data-ttu-id="5ca37-148">IIS が共有構成モードであり、[!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] がインストールされている場合、IIS メタベースは共有された場所で構成されます。</span><span class="sxs-lookup"><span data-stu-id="5ca37-148">When IIS is in shared configuration mode and [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] is installed, the IIS metabase is configured under a shared location.</span></span> <span data-ttu-id="5ca37-149">IIS を非共有構成モードに切り替えると、ローカル メタベースには必要なハンドラーが格納されません。</span><span class="sxs-lookup"><span data-stu-id="5ca37-149">If you switch IIS to non-shared configuration mode, the local metabase will not contain the required handlers.</span></span> <span data-ttu-id="5ca37-150">ローカル メタベースを正しく構成するには、か、ローカル、または実行"WFServicesReg.exe/c"をローカル メタベースを構成する共有メタベースをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="5ca37-150">To configure the local metabase properly, you can either import the shared metabase to local, or run "WFServicesReg.exe /c", which configures the local metabase.</span></span>

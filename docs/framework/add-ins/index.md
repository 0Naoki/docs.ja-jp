---
title: アドインおよび拡張機能
ms.date: 03/30/2017
helpviewer_keywords:
- extensibility [.NET Framework], add-ins
- add-ins [.NET Framework]
- add-ins [.NET Framework], about
- hosts [.NET Framework], compared to add-ins
- .NET Framework, add-ins
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], compared to hosts
- .NET Framework, extensibility
- versioning [.NET Framework], add-ins
ms.assetid: 8dd45b02-7218-40f9-857d-40d7b98b850b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb2485f2ecf0426360dba80d443500a92b5a7af6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510055"
---
# <a name="add-ins-and-extensibility"></a><span data-ttu-id="9c819-102">アドインおよび拡張機能</span><span class="sxs-lookup"><span data-stu-id="9c819-102">Add-ins and Extensibility</span></span>
<a name="top"></a> <span data-ttu-id="9c819-103">アドインには、ホスト アプリケーションのための拡張機能またはサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9c819-103">Add-ins provide extended features or services for a host application.</span></span> <span data-ttu-id="9c819-104">開発者は、 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] のプログラミング モデルを使用してアドインを開発し、ホスト アプリケーションでそれらをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="9c819-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides a programming model that developers can use to develop add-ins and activate them in their host application.</span></span> <span data-ttu-id="9c819-105">こうした機能は、このモデルで、ホストとアドインの間に通信パイプラインを構築することによって実現します。</span><span class="sxs-lookup"><span data-stu-id="9c819-105">The model achieves this by constructing a communication pipeline between the host and the add-in.</span></span> <span data-ttu-id="9c819-106">このモデルは、 <xref:System.AddIn>、 <xref:System.AddIn.Hosting>、 <xref:System.AddIn.Pipeline>、 <xref:System.AddIn.Contract> の各名前空間の型を使用することによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="9c819-106">The model is implemented by using the types in the <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>, and <xref:System.AddIn.Contract> namespaces.</span></span>  
  
 <span data-ttu-id="9c819-107">この概要は、次のセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="9c819-107">This overview contains the following sections:</span></span>  
  
-   [<span data-ttu-id="9c819-108">アドイン モデル</span><span class="sxs-lookup"><span data-stu-id="9c819-108">Add-in Model</span></span>](#addin_model)  
  
-   [<span data-ttu-id="9c819-109">アドインとホストの違い</span><span class="sxs-lookup"><span data-stu-id="9c819-109">Distinguishing Between Add-ins and Hosts</span></span>](#distinguishing_between_addins_and_hosts)  
  
-   [<span data-ttu-id="9c819-110">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9c819-110">Related Topics</span></span>](#related_topics)  
  
-   [<span data-ttu-id="9c819-111">参照</span><span class="sxs-lookup"><span data-stu-id="9c819-111">Reference</span></span>](#reference)  
  
> [!NOTE]
>  <span data-ttu-id="9c819-112">掲載その他のサンプル コード、およびツールのカスタマー テクノロジ プレビュー ビルド アドイン パイプラインの[CodePlex での Managed Extensibility and アドイン フレームワーク サイト](https://go.microsoft.com/fwlink/?LinkId=121190)します。</span><span class="sxs-lookup"><span data-stu-id="9c819-112">You can find additional sample code, and customer technology previews of tools for building add-in pipelines, at the [Managed Extensibility and Add-In Framework site on CodePlex](https://go.microsoft.com/fwlink/?LinkId=121190).</span></span>  
  
<a name="addin_model"></a>   
## <a name="add-in-model"></a><span data-ttu-id="9c819-113">アドイン モデル</span><span class="sxs-lookup"><span data-stu-id="9c819-113">Add-in Model</span></span>  
 <span data-ttu-id="9c819-114">アドイン モデルは、アドイン パイプライン (通信パイプラインとも呼ばれます) を構成する一連のセグメントで構成されます。アドイン パイプラインにより、アドインとホストの間の全通信がなされます。</span><span class="sxs-lookup"><span data-stu-id="9c819-114">The add-in model consists of a series of segments that make up the add-in pipeline (also known as the communication pipeline), that is responsible for all communication between the add-in and the host.</span></span> <span data-ttu-id="9c819-115">このパイプラインは、アドインとそのホスト間でデータを交換するセグメントの対称通信モデルです。</span><span class="sxs-lookup"><span data-stu-id="9c819-115">The pipeline is a symmetrical communication model of segments that exchange data between an add-in and its host.</span></span> <span data-ttu-id="9c819-116">ホストとアドインの間にこのようなセグメントを開発することで、アドインのバージョン管理と分離をサポートするために必要な抽象化レイヤーが得られます。</span><span class="sxs-lookup"><span data-stu-id="9c819-116">Developing these segments between the host and the add-in provides the required layers of abstraction that support versioning and isolation of the add-in.</span></span>  
  
 <span data-ttu-id="9c819-117">次の図に、そのパイプラインを示します。</span><span class="sxs-lookup"><span data-stu-id="9c819-117">The following illustration shows the pipeline.</span></span>  
  
 <span data-ttu-id="9c819-118">![追加&#45;パイプライン モデル。](../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span><span class="sxs-lookup"><span data-stu-id="9c819-118">![Add&#45;in pipeline model.](../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span></span>  
<span data-ttu-id="9c819-119">アドイン パイプライン</span><span class="sxs-lookup"><span data-stu-id="9c819-119">Add-in pipeline</span></span>  
  
 <span data-ttu-id="9c819-120">これらのセグメントのアセンブリが、同じアプリケーション ドメインに含まれている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9c819-120">The assemblies for these segments are not required to be in the same application domain.</span></span> <span data-ttu-id="9c819-121">専用の新規アプリケーション ドメイン、既存のアプリケーション ドメイン、さらにはホストのアプリケーション ドメインにも、アドインを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="9c819-121">You can load an add-in into its own new application domain, into an existing application domain, or even into the host's application domain.</span></span> <span data-ttu-id="9c819-122">同じアプリケーション ドメインに複数のアドインを読み込むことができます。これにより、リソースとセキュリティ コンテキストを他のアドインと共有できます。</span><span class="sxs-lookup"><span data-stu-id="9c819-122">You can load multiple add-ins into the same application domain, which enables the add-ins to share resources and security contexts.</span></span>  
  
 <span data-ttu-id="9c819-123">アドイン モデルでは、ホストとアドインの間に分離境界 (またはリモート境界) と呼ばれるオプションの境界がサポートされており、この使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9c819-123">The add-in model supports, and recommends, an optional boundary between the host and the add-in, which is called the isolation boundary (also known as a remoting boundary).</span></span> <span data-ttu-id="9c819-124">この境界をアプリケーション ドメインやプロセス境界に設定できます。</span><span class="sxs-lookup"><span data-stu-id="9c819-124">This boundary can be an application domain or process boundary.</span></span>  
  
 <span data-ttu-id="9c819-125">パイプラインの中間にあるコントラクト セグメントは、ホストのアプリケーション ドメインとアドインのアプリケーション ドメインの両方に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="9c819-125">The contract segment in the middle of the pipeline is loaded into both the host's application domain and the add-in's application domain.</span></span> <span data-ttu-id="9c819-126">コントラクトにより、ホストとアドインで相互に型を交換するために使用される仮想メソッドが定義されます。</span><span class="sxs-lookup"><span data-stu-id="9c819-126">The contract defines the virtual methods that the host and the add-in use to exchange types with each other.</span></span>  
  
 <span data-ttu-id="9c819-127">分離境界を通過して型を渡すには、型がコントラクトかシリアル化できる型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c819-127">To pass through the isolation boundary, types must be either contracts or serializable types.</span></span> <span data-ttu-id="9c819-128">コントラクトやシリアル化できる型でない型は、パイプラインのアダプター セグメントでコントラクトに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c819-128">Types that are not contracts or serializable types must be converted to contracts by the adapter segments in the pipeline.</span></span>  
  
 <span data-ttu-id="9c819-129">パイプラインのビュー セグメントは、コントラクトの定義に従って、ホストとアドインに共有メソッドのビューを提供する抽象基本クラスまたはインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="9c819-129">The view segments of the pipeline are abstract base classes or interfaces that provide the host and the add-in with a view of the methods that they share, as defined by the contract.</span></span>  
  
 <span data-ttu-id="9c819-130">パイプライン セグメントの開発の詳細については、「 [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c819-130">For more information about developing pipeline segments, see [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md).</span></span>  
  
 <span data-ttu-id="9c819-131">以降のセクションでは、アドイン モデルの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c819-131">The sections that follow describe the features of the add-in model.</span></span>  
  
### <a name="independent-versioning"></a><span data-ttu-id="9c819-132">独立バージョン管理</span><span class="sxs-lookup"><span data-stu-id="9c819-132">Independent Versioning</span></span>  
 <span data-ttu-id="9c819-133">アドイン モデルを使用して、ホストとアドインを別々にバージョン管理できます。</span><span class="sxs-lookup"><span data-stu-id="9c819-133">The add-in model allows hosts and add-ins to version independently.</span></span> <span data-ttu-id="9c819-134">つまり、アドイン モデルでは次のシナリオが有効です。</span><span class="sxs-lookup"><span data-stu-id="9c819-134">As a result, the add-in model enables the following scenarios:</span></span>  
  
-   <span data-ttu-id="9c819-135">ホストが、以前のバージョンのホスト用にビルドされたアドインを使用できるようにするアダプターの作成。</span><span class="sxs-lookup"><span data-stu-id="9c819-135">Creating an adapter that enables a host to use an add-in built for a previous version of the host.</span></span>  
  
-   <span data-ttu-id="9c819-136">ホストが、ホストの最新バージョンのホスト用にビルドされたアドインを使用できるようにするアダプターの作成。</span><span class="sxs-lookup"><span data-stu-id="9c819-136">Creating an adapter that enables a host to use an add-in built for a later version of the host.</span></span>  
  
-   <span data-ttu-id="9c819-137">ホストが、異なるホスト用にビルドされたアドインを使用できるようにするアダプターの作成。</span><span class="sxs-lookup"><span data-stu-id="9c819-137">Creating an adapter that enables a host to use add-ins built for a different host.</span></span>  
  
### <a name="discovery-and-activation"></a><span data-ttu-id="9c819-138">探索とアクティブ化</span><span class="sxs-lookup"><span data-stu-id="9c819-138">Discovery and Activation</span></span>  
 <span data-ttu-id="9c819-139">情報ストアに格納されている、アドインを表すコレクション内のトークンを使用して、アドインをアクティブにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9c819-139">You can activate an add-in by using a token from a collection that represents the add-ins found from an information store.</span></span> <span data-ttu-id="9c819-140">アドインは、アドインのホストのビューを定義する型によって検索されます。</span><span class="sxs-lookup"><span data-stu-id="9c819-140">Add-ins are found by searching for the type that defines the host's view of the add-in.</span></span> <span data-ttu-id="9c819-141">アドインを定義する型によって、特定のアドインを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="9c819-141">You can also find a specific add-in by the type that defines the add-in.</span></span> <span data-ttu-id="9c819-142">情報ストアは、パイプライン ストアとアドイン ストアの 2 つのキャッシュ ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="9c819-142">The information store consists of two cache files: the pipeline store and the add-in store.</span></span>  
  
 <span data-ttu-id="9c819-143">更新と、インフォメーション ストアを再構築については、次を参照してください。[アドイン探索](https://msdn.microsoft.com/library/5d268dde-11df-4c4d-a022-f58d88bbc421)します。</span><span class="sxs-lookup"><span data-stu-id="9c819-143">For information about updating and rebuilding the information store, see [Add-in Discovery](https://msdn.microsoft.com/library/5d268dde-11df-4c4d-a022-f58d88bbc421).</span></span> <span data-ttu-id="9c819-144">アドインをアクティブ化方法の詳細については、次を参照してください。[アドインをアクティブ化](https://msdn.microsoft.com/library/bedcbcdf-5964-4215-b5f3-3299798b2b3f)と[方法: さまざまな分離とセキュリティには、アドインをアクティブ化](https://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5)します。</span><span class="sxs-lookup"><span data-stu-id="9c819-144">For information about activating add-ins, see [Add-in Activation](https://msdn.microsoft.com/library/bedcbcdf-5964-4215-b5f3-3299798b2b3f) and [How to: Activate Add-ins with Different Isolation and Security](https://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span></span>  
  
### <a name="isolation-levels-and-external-processes"></a><span data-ttu-id="9c819-145">分離レベルと外部プロセス</span><span class="sxs-lookup"><span data-stu-id="9c819-145">Isolation Levels and External Processes</span></span>  
 <span data-ttu-id="9c819-146">アドイン モデルでは、アドインとホスト間、アドインと他のアドイン間について、複数の分離レベルがサポートされます。分離レベルの低いものから順に、次のレベルがあります。</span><span class="sxs-lookup"><span data-stu-id="9c819-146">The add-in model supports several levels of isolation between an add-in and its host or between add-ins. Starting from the least isolated, these levels are as follows:</span></span>  
  
-   <span data-ttu-id="9c819-147">アドインが、ホストと同じアプリケーション ドメインで実行される。</span><span class="sxs-lookup"><span data-stu-id="9c819-147">The add-in runs in the same application domain as the host.</span></span> <span data-ttu-id="9c819-148">この場合、さまざまなアプリケーション ドメインを使用することで得られる分離とアンロードの機能が使用できなくなるため、このレベルは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="9c819-148">This is not recommended because you lose the isolation and unloading capabilities that you get when you use different application domains.</span></span>  
  
-   <span data-ttu-id="9c819-149">ホストで使用されるアプリケーション ドメインとは異なる 1 つのアプリケーション ドメインに、複数のアドインが読み込まれる。</span><span class="sxs-lookup"><span data-stu-id="9c819-149">Multiple add-ins are loaded into the same application domain that is different from the application domain used by the host.</span></span>  
  
-   <span data-ttu-id="9c819-150">それぞれのアドインが専用のアプリケーション ドメインに排他的に読み込まれる。</span><span class="sxs-lookup"><span data-stu-id="9c819-150">Each add-in is loaded exclusively into its own application domain.</span></span> <span data-ttu-id="9c819-151">これが最も一般的な分離レベルです。</span><span class="sxs-lookup"><span data-stu-id="9c819-151">This is the most common level of isolation.</span></span>  
  
-   <span data-ttu-id="9c819-152">外部プロセスの同じアプリケーション ドメインに複数のアドインが読み込まれる。</span><span class="sxs-lookup"><span data-stu-id="9c819-152">Multiple add-ins are loaded into the same application domain in an external process.</span></span>  
  
-   <span data-ttu-id="9c819-153">外部プロセスの専用のアプリケーション ドメインに、それぞれのアドインが排他的に読み込まれる。</span><span class="sxs-lookup"><span data-stu-id="9c819-153">Each add-in is loaded exclusively into its own application domain in an external process.</span></span> <span data-ttu-id="9c819-154">これが最も分離レベルの高いシナリオです。</span><span class="sxs-lookup"><span data-stu-id="9c819-154">This is the most isolated scenario.</span></span>  
  
 <span data-ttu-id="9c819-155">外部プロセスの使用に関する詳細については、次を参照してください。[方法: さまざまな分離とセキュリティには、アドインをアクティブ化](https://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5)します。</span><span class="sxs-lookup"><span data-stu-id="9c819-155">For more information about using external processes, see [How to: Activate Add-ins with Different Isolation and Security](https://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span></span>  
  
### <a name="lifetime-management"></a><span data-ttu-id="9c819-156">有効期間管理</span><span class="sxs-lookup"><span data-stu-id="9c819-156">Lifetime Management</span></span>  
 <span data-ttu-id="9c819-157">アドイン モデルはアプリケーション ドメインとプロセス境界を横断するため、オブジェクトの解放と再要求を実行するにはガベージ コレクションだけでは不十分です。</span><span class="sxs-lookup"><span data-stu-id="9c819-157">Because the add-in model spans application domain and process boundaries, garbage collection by itself is not sufficient to release and reclaim objects.</span></span> <span data-ttu-id="9c819-158">アドイン モデルには、トークンと参照カウントを使用した有効期間管理機能があるため、通常は追加のプログラミングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9c819-158">The add-in model provides a lifetime management mechanism that uses tokens and reference counting, and usually does not require additional programming.</span></span> <span data-ttu-id="9c819-159">詳細については、次を参照してください。[有効期間管理](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5)します。</span><span class="sxs-lookup"><span data-stu-id="9c819-159">For more information, see [Lifetime Management](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
 [<span data-ttu-id="9c819-160">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="9c819-160">Back to top</span></span>](#top)  
  
<a name="distinguishing_between_addins_and_hosts"></a>   
## <a name="distinguishing-between-add-ins-and-hosts"></a><span data-ttu-id="9c819-161">アドインとホストの違い</span><span class="sxs-lookup"><span data-stu-id="9c819-161">Distinguishing Between Add-ins and Hosts</span></span>  
 <span data-ttu-id="9c819-162">アドインとホストの違いは、アドインをアクティブにするものがホストであるということのみです。</span><span class="sxs-lookup"><span data-stu-id="9c819-162">The difference between an add-in and a host is merely that the host is the one that activates the add-in.</span></span> <span data-ttu-id="9c819-163">ホストは、2 つのうち大きな方であることもあれば (ワード プロセッシング アプリケーションとスペル チェック機能の場合など)、小さな方であることもあります (メディア プレーヤーを埋め込んだインスタント メッセージング クライアントの場合など)。</span><span class="sxs-lookup"><span data-stu-id="9c819-163">The host can be the larger of the two, such as a word processing application and its spell checkers; or the host can be the smaller of the two, such as an instant messaging client that embeds a media player.</span></span> <span data-ttu-id="9c819-164">アドイン モデルでは、クライアントとサーバーの両方のシナリオでアドインがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9c819-164">The add-in model supports add-ins in both client and server scenarios.</span></span> <span data-ttu-id="9c819-165">サーバー アドインの例としては、電子メール サーバーにウイルス スキャン、スパム フィルター、IP 保護を適用するアドインなどがあります。</span><span class="sxs-lookup"><span data-stu-id="9c819-165">Examples of server add-ins include add-ins that provide mail servers with virus scanning, spam filters, and IP protection.</span></span> <span data-ttu-id="9c819-166">クライアントのアドインの例には、ワード プロセッサ、グラフィック プログラムやゲームなど、ローカルの電子メール クライアント用のウイルス スキャンに特化した機能の参照のアドインが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9c819-166">Client add-in examples include reference add-ins for word processors, specialized features for graphics programs and games, and virus scanning for local email clients.</span></span>  
  
 [<span data-ttu-id="9c819-167">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="9c819-167">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="9c819-168">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9c819-168">Related Topics</span></span>  
  
|<span data-ttu-id="9c819-169">タイトル</span><span class="sxs-lookup"><span data-stu-id="9c819-169">Title</span></span>|<span data-ttu-id="9c819-170">説明</span><span class="sxs-lookup"><span data-stu-id="9c819-170">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9c819-171">Pipeline Development</span><span class="sxs-lookup"><span data-stu-id="9c819-171">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)|<span data-ttu-id="9c819-172">ホスト アプリケーションからアドインへのセグメントの通信パイプラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9c819-172">Describes the communication pipeline of segments from the host application to the add-in.</span></span> <span data-ttu-id="9c819-173">パイプラインの構築方法とセグメントを Visual Studio でパイプラインをデプロイする方法について説明するチュートリアルのトピックでのコード例を示します。</span><span class="sxs-lookup"><span data-stu-id="9c819-173">Provides code examples in walkthrough topics that describe how to construct the pipeline and how to deploy segments to the pipeline in Visual Studio.</span></span>|  
|[<span data-ttu-id="9c819-174">アプリケーション ドメインとアセンブリ</span><span class="sxs-lookup"><span data-stu-id="9c819-174">Application Domains and Assemblies</span></span>](https://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)|<span data-ttu-id="9c819-175">セキュリティ、信頼性、バージョン管理、およびアセンブリのための分離の境界を提供するアプリケーション ドメイン間の関係について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c819-175">Describes the relationship between application domains, which provide an isolation boundary for security, reliability, and versioning, and assemblies.</span></span>|  
  
 [<span data-ttu-id="9c819-176">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="9c819-176">Back to top</span></span>](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a><span data-ttu-id="9c819-177">参照</span><span class="sxs-lookup"><span data-stu-id="9c819-177">Reference</span></span>  
 <xref:System.AddIn?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Contract?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Hosting?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Pipeline?displayProperty=nameWithType>  
  
 [<span data-ttu-id="9c819-178">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="9c819-178">Back to top</span></span>](#top)
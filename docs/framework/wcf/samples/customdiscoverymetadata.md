---
title: CustomDiscoveryMetadata
ms.date: 03/30/2017
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
ms.openlocfilehash: 181910db3f1dd6da892f6ae2ddcbf7bd5859ff17
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525422"
---
# <a name="customdiscoverymetadata"></a><span data-ttu-id="34c0b-102">CustomDiscoveryMetadata</span><span class="sxs-lookup"><span data-stu-id="34c0b-102">CustomDiscoveryMetadata</span></span>
<span data-ttu-id="34c0b-103">このサンプルでは、サービスによって公開される探索可能なエンドポイントの探索メタデータにカスタム XML メタデータを挿入する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="34c0b-103">This sample shows how to insert custom XML metadata into the discovery metadata for a discoverable endpoint exposed by a service.</span></span> <span data-ttu-id="34c0b-104">次に、クライアントがサービスを検索してこのカスタム データを抽出する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="34c0b-104">The sample then shows how a client can search for the service and extract this custom data.</span></span> <span data-ttu-id="34c0b-105">このサンプルは、2 つのプロジェクト (サービスとクライアント) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="34c0b-105">This sample consists of two projects, service and client.</span></span>  
  
## <a name="service"></a><span data-ttu-id="34c0b-106">サービス</span><span class="sxs-lookup"><span data-stu-id="34c0b-106">Service</span></span>  
 <span data-ttu-id="34c0b-107">サンプルの `main` メソッドでは、<xref:System.Xml.Linq.XElement> 型のオブジェクトに必要なフィールドが設定され、このオブジェクトが <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> に追加されます。</span><span class="sxs-lookup"><span data-stu-id="34c0b-107">In the `main` method, the sample shows that an object of type <xref:System.Xml.Linq.XElement> is populated with the desired fields and is added to the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span></span> <span data-ttu-id="34c0b-108">この <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> が特定のエンドポイントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="34c0b-108">This <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> is added to a particular endpoint.</span></span> <span data-ttu-id="34c0b-109">この特定のエンドポイントが探索されると、ここで追加されたカスタム データが探索メタデータに格納されます。</span><span class="sxs-lookup"><span data-stu-id="34c0b-109">When that particular endpoint is discovered, the discovery metadata contains the custom data that was added here.</span></span>  
  
## <a name="client"></a><span data-ttu-id="34c0b-110">Client</span><span class="sxs-lookup"><span data-stu-id="34c0b-110">Client</span></span>  
 <span data-ttu-id="34c0b-111">サンプルでは、<xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> で <xref:System.ServiceModel.Discovery.DiscoveryClient> メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="34c0b-111">The sample shows the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method being called on a <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span></span> <span data-ttu-id="34c0b-112">次に、生成された <xref:System.ServiceModel.Discovery.FindResponse> に対して適切かつ必要な XML 要素が照会されます。</span><span class="sxs-lookup"><span data-stu-id="34c0b-112">The resulting <xref:System.ServiceModel.Discovery.FindResponse> is then queried for the appropriate and expected XML elements.</span></span> <span data-ttu-id="34c0b-113">その後、これらの要素がコンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="34c0b-113">These elements are then printed to the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="34c0b-114">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="34c0b-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="34c0b-115">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] でプロジェクト ソリューションを読み込み、プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="34c0b-115">Load the project solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="34c0b-116">まず、[ソリューションの基本ディレクトリ]\service\bin\debug に生成されたサービス アプリケーションを実行します。次に、[ソリューションの基本ディレクトリ]\Client\bin\debug に生成されたクライアント アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="34c0b-116">First run the Service application, generated in [solution base directory]\service\bin\debug, and then run the Client application, generated in [solution base directory]\Client\bin\debug</span></span>  
  
3.  <span data-ttu-id="34c0b-117">サービスがオンラインになると、クライアントはサービスを検索し、エンドポイントで公開されているメタデータを出力します。</span><span class="sxs-lookup"><span data-stu-id="34c0b-117">Note that the service comes online, the client locates the service and prints the metadata published in the endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="34c0b-118">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="34c0b-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="34c0b-119">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="34c0b-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="34c0b-120">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="34c0b-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="34c0b-121">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="34c0b-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a><span data-ttu-id="34c0b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="34c0b-122">See Also</span></span>

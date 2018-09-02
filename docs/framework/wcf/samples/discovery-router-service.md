---
title: 探索ルーター サービス
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: 9c0c409eb6cf3146a198b9f4bcd6d76660f5da36
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43409115"
---
# <a name="discovery-router-service"></a><span data-ttu-id="b0dea-102">探索ルーター サービス</span><span class="sxs-lookup"><span data-stu-id="b0dea-102">Discovery Router Service</span></span>
<span data-ttu-id="b0dea-103">このサンプルでは、探索メッセージを別のエンドポイントに転送する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b0dea-103">This sample demonstrates how to forward discovery messages to another endpoint.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b0dea-104">使用例</span><span class="sxs-lookup"><span data-stu-id="b0dea-104">Demonstrates</span></span>  
 <span data-ttu-id="b0dea-105">探索ルーティング</span><span class="sxs-lookup"><span data-stu-id="b0dea-105">Discovery Routing</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="b0dea-106">説明</span><span class="sxs-lookup"><span data-stu-id="b0dea-106">Discussion</span></span>  
 <span data-ttu-id="b0dea-107">探索ルーティングは、プロキシがサービスを認識しないが、別のプロキシのことは認識する場合に、クライアントがプロキシを使用してそのようなサービスを検索するシナリオで役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="b0dea-107">Discovery routing is useful in a scenario in which a client is looking for a service using a proxy and the proxy is unaware of such a service, but knows of another proxy.</span></span> <span data-ttu-id="b0dea-108">このプロキシは、探索パケットをこのクライアントから 2 番目のプロキシに転送できます。</span><span class="sxs-lookup"><span data-stu-id="b0dea-108">This proxy can forward the discovery packet from this client to the second proxy.</span></span> <span data-ttu-id="b0dea-109">2 番目のプロキシはサービスを検索し、応答を元のクライアントに返します。</span><span class="sxs-lookup"><span data-stu-id="b0dea-109">The second proxy can look for the service and return the responses to the original client.</span></span>  
  
 <span data-ttu-id="b0dea-110">このサンプルでは、クライアントはメッセージを探索ルーティング コンポーネントに送信します。</span><span class="sxs-lookup"><span data-stu-id="b0dea-110">In this sample, a client sends a message to a discovery routing component.</span></span> <span data-ttu-id="b0dea-111">このメッセージは、探索ルーター上の特定のエンドポイントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b0dea-111">This message is sent to a specific endpoint on the discovery router.</span></span> <span data-ttu-id="b0dea-112">その後、このルーターはメッセージを UDP マルチキャスト エンドポイントに転送します。</span><span class="sxs-lookup"><span data-stu-id="b0dea-112">The router then forwards the message to a UDP multicast endpoint.</span></span> <span data-ttu-id="b0dea-113">プローブ メッセージはマルチキャスト エンドポイントに送信され、UDP マルチキャスト アドレスをリッスンするサービスは、その探索ルーターに応答します。</span><span class="sxs-lookup"><span data-stu-id="b0dea-113">The probe message goes out to the multicast endpoint and a service listening on a UDP multicast address responds to that discovery router.</span></span> <span data-ttu-id="b0dea-114">探索ルーターは応答を収集し、クライアントにその応答を返します。</span><span class="sxs-lookup"><span data-stu-id="b0dea-114">The discovery router collects the responses and sends them back to the client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b0dea-115">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="b0dea-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b0dea-116">このサンプルをビルドします。</span><span class="sxs-lookup"><span data-stu-id="b0dea-116">Build the sample.</span></span>  
  
2.  <span data-ttu-id="b0dea-117">DiscoveryRouter 実行可能ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0dea-117">Run the DiscoveryRouter executable.</span></span>  
  
3.  <span data-ttu-id="b0dea-118">ビルド ディレクトリからサービス実行可能ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0dea-118">Run the service executable from the build directory.</span></span>  
  
4.  <span data-ttu-id="b0dea-119">クライアント実行可能ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0dea-119">Run the client executable.</span></span> <span data-ttu-id="b0dea-120">クライアントでサービスが検索されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b0dea-120">Note that the client locates the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b0dea-121">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b0dea-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b0dea-122">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b0dea-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b0dea-123">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="b0dea-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b0dea-124">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b0dea-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`

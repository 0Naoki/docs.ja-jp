---
title: ブリッジとエラー処理
ms.date: 03/30/2017
ms.assetid: 4ae87d1a-b615-4014-a494-a53f63ff0137
ms.openlocfilehash: 6afaddc75855b7e95ad708b2179cabb9aee35001
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43389069"
---
# <a name="bridging-and-error-handling"></a><span data-ttu-id="bc780-102">ブリッジとエラー処理</span><span class="sxs-lookup"><span data-stu-id="bc780-102">Bridging and Error Handling</span></span>
<span data-ttu-id="bc780-103">このサンプルでは、クライアントと異なるバインディングを使用するサービスの間の通信をブリッジでの Windows Communication Foundation (WCF) ルーティング サービスを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bc780-103">This sample demonstrates how the Windows Communication Foundation (WCF) routing service is used for bridging communication between a client and a service that use different bindings.</span></span> <span data-ttu-id="bc780-104">また、バックアップ サービスを使用してフェールオーバーのシナリオに対処する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="bc780-104">This sample also shows how to use a back-up service for failover scenarios.</span></span> <span data-ttu-id="bc780-105">ルーティング サービスは、WCF コンポーネント、アプリケーションでコンテンツ ベースのルーターを含めるが簡単です。</span><span class="sxs-lookup"><span data-stu-id="bc780-105">The routing service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="bc780-106">このサンプルでは、ルーティング サービスを使用して通信するために標準の WCF 電卓のサンプルを適応します。</span><span class="sxs-lookup"><span data-stu-id="bc780-106">This sample adapts the standard WCF Calculator Sample to communicate using the routing service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bc780-107">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="bc780-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bc780-108">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bc780-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bc780-109">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="bc780-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bc780-110">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="bc780-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\ErrorHandlingAndBridging`  
  
## <a name="sample-details"></a><span data-ttu-id="bc780-111">サンプルの詳細</span><span class="sxs-lookup"><span data-stu-id="bc780-111">Sample Details</span></span>  
 <span data-ttu-id="bc780-112">このサンプルの電卓クライアントは、ルーターによって公開されるエンドポイントにメッセージを送信するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="bc780-112">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="bc780-113">ルーティング サービスは、送信されてきたすべてのメッセージを受け入れ、電卓サービスに対応するエンドポイントに転送するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="bc780-113">The routing service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="bc780-114">プライマリ電卓サービス、バックアップ電卓サービス、および電卓クライアントの構成と、ルーティング サービスによるクライアントとサービス間の通信の処理方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bc780-114">The following points describe the configuration of the primary Calculator service, the back-up Calculator service, and the Calculator client and how the communication between the client and the service happens using the routing service:</span></span>  
  
-   <span data-ttu-id="bc780-115">電卓クライアントは BasicHttpBinding を使用するように構成され、電卓サービスは NetTcpBinding を使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="bc780-115">The Calculator client is configured to use BasicHttpBinding while the Calculator service is configured to use NetTcpBinding.</span></span> <span data-ttu-id="bc780-116">ルーティング サービスは、電卓サービスに送信する前に、必要に応じて自動的にメッセージを変換します。また、電卓クライアントがアクセスできるように応答も変換します。</span><span class="sxs-lookup"><span data-stu-id="bc780-116">The routing service automatically converts the messages as necessary before sending them to the Calculator service and it also converts the responses so that the Calculator client can access them.</span></span>  
  
-   <span data-ttu-id="bc780-117">ルーティング サービスは、プライマリ電卓サービスとバックアップ電卓サービスの 2 つの電卓サービスを認識します。</span><span class="sxs-lookup"><span data-stu-id="bc780-117">The routing service knows about two Calculator services: the primary Calculator service and the back-up Calculator service.</span></span> <span data-ttu-id="bc780-118">まず、ルーティング サービスは、プライマリ電卓サービスのエンドポイントとの通信を試みます。</span><span class="sxs-lookup"><span data-stu-id="bc780-118">The routing service first attempts to communicate with the primary Calculator service endpoint.</span></span> <span data-ttu-id="bc780-119">エンドポイントがダウンしているためにこの試行が失敗すると、次に、バックアップ電卓サービスのエンドポイントとの通信を試みます。</span><span class="sxs-lookup"><span data-stu-id="bc780-119">If this attempt fails due to the endpoint being down, the routing service then tries to communicate with the back-up Calculator service endpoint.</span></span>  
  
 <span data-ttu-id="bc780-120">したがって、クライアントから送信されたメッセージはルーターで受信され、実際の電卓サービスに再ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="bc780-120">Thus messages sent from the client are received by the router and are rerouted to the actual Calculator service.</span></span> <span data-ttu-id="bc780-121">電卓サービスのエンドポイントがダウンしている場合、ルーティング サービスは、バックアップ電卓サービスのエンドポイントにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="bc780-121">If the Calculator service endpoint is down, the routing service routes the message to the back-up Calculator service endpoint.</span></span> <span data-ttu-id="bc780-122">バックアップ電卓サービスからのメッセージはサービス ルーターに送り返され、ルーターから電卓クライアントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="bc780-122">Messages from the back-up Calculator service are sent back to the service router, which in turn passes them back to the Calculator client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc780-123">バックアップのリストには、複数のエンドポイントを定義しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="bc780-123">A back-up list can have more than one endpoint defined.</span></span> <span data-ttu-id="bc780-124">その場合、バックアップ サービスのエンドポイントがダウンしていると、ルーティング サービスはリスト内の次のバックアップ エンドポイントへの接続を試み、接続が成功するまで試行を続けます。</span><span class="sxs-lookup"><span data-stu-id="bc780-124">In this case if the back-up service endpoint is down, the routing service attempts to connect to the next back-up endpoint in the list until a successful connection occurs.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="bc780-125">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="bc780-125">To use this sample</span></span>  
  
1.  <span data-ttu-id="bc780-126">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] を使用して、RouterBridgingAndErrorHandling.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="bc780-126">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open RouterBridgingAndErrorHandling.sln.</span></span>  
  
2.  <span data-ttu-id="bc780-127">Visual Studio で F5 キーを押すか、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bc780-127">Press F5 or CTRL+SHIFT+B in Visual Studio</span></span>  
  
    1.  <span data-ttu-id="bc780-128">F5 キーを押してに必要なプロジェクトを自動で起動する場合は、ソリューションを右クリックし、選択**プロパティ**、し、**スタートアップ プロジェクト**ノードの下**の共通プロパティ**を選択します**マルチ スタートアップ プロジェクト**、すべてのプロジェクトに設定し、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="bc780-128">If you would like to auto-launch the necessary projects when you press F5, right-click the solution, select **Properties**, and in the **Startup Project** node under **Common Properties**, select **Multiple Startup Projects**, and set all projects to **Start**.</span></span>  
  
    2.  <span data-ttu-id="bc780-129">Ctrl キーと Shift キーを押しながら B キーを押してプロジェクトをビルドすると、次のアプリケーションが開始します。</span><span class="sxs-lookup"><span data-stu-id="bc780-129">If you build the project with CTRL+SHIFT+B, start the following applications:</span></span>  
  
        1.  <span data-ttu-id="bc780-130">電卓クライアント (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="bc780-130">Calculator client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="bc780-131">電卓サービス (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="bc780-131">Calculator service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="bc780-132">ルーティング サービス (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="bc780-132">Routing Service (./RoutingService/bin/RoutingService.exe)</span></span>  
  
3.  <span data-ttu-id="bc780-133">電卓クライアントで、Enter キーを押してクライアントを起動します。</span><span class="sxs-lookup"><span data-stu-id="bc780-133">In the Calculator Client, press ENTER to start the client.</span></span>  
  
     <span data-ttu-id="bc780-134">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc780-134">You should see the following output:</span></span>  
  
    ```Output  
    Add(100,15.99) = 115.99  
    Subtract(145,76.54) = 68.46  
    Multiply(9,81.25) = 731.25  
    Divide(22,7) = 3.14285714285714  
    ```  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="bc780-135">コードまたは App.config で構成可能</span><span class="sxs-lookup"><span data-stu-id="bc780-135">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="bc780-136">サンプルは、提供された時点では、App.config ファイルを使用してルーターの動作を定義するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="bc780-136">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="bc780-137">App.config ファイルの名前を別の名前に変更して認識されないようにし、`ConfigureRouterViaCode()` に対するメソッド呼び出しのコメントを解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc780-137">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to `ConfigureRouterViaCode()`.</span></span> <span data-ttu-id="bc780-138">どちらの方法でも、ルーターの動作は同じになります。</span><span class="sxs-lookup"><span data-stu-id="bc780-138">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="bc780-139">シナリオ</span><span class="sxs-lookup"><span data-stu-id="bc780-139">Scenario</span></span>  
 <span data-ttu-id="bc780-140">このサンプルでは、プロトコル ブリッジおよびエラー ハンドラーとして機能するサービス ルーターを示します。</span><span class="sxs-lookup"><span data-stu-id="bc780-140">This sample demonstrates the service router acting as a protocol bridge and error handler.</span></span> <span data-ttu-id="bc780-141">このシナリオでは、コンテンツ ベースのルーティングは発生しません。ルーティング サービスは、構成済みの一連の送信先エンドポイントに直接メッセージを渡すように構成された透過的なプロキシ ノードとして機能します。</span><span class="sxs-lookup"><span data-stu-id="bc780-141">In this scenario, no content-based routing occurs; the routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span> <span data-ttu-id="bc780-142">さらに、通信するように構成されたエンドポイントへの送信の試行時にエラーが発生した場合に、そのエラーを透過的に処理する追加の手順も実行します。</span><span class="sxs-lookup"><span data-stu-id="bc780-142">The routing service also performs the additional steps of transparently handling errors that occur when it tries to send to the endpoints that it is configured to communicate with.</span></span> <span data-ttu-id="bc780-143">ルーティング サービスをプロトコル ブリッジとして使用することで、外部の通信と内部の通信に対して別々のプロトコルを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="bc780-143">By acting as a protocol bridge, the routing service enables the user to define one protocol for external communication and another for internal communication.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="bc780-144">実際のシナリオ</span><span class="sxs-lookup"><span data-stu-id="bc780-144">Real World Scenario</span></span>  
 <span data-ttu-id="bc780-145">Contoso では、外部には相互運用可能なサービスのエンドポイントを公開し、内部ではパフォーマンスを最適化したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="bc780-145">Contoso wants to provide an interoperable service endpoint to the world, while optimizing performance internally.</span></span> <span data-ttu-id="bc780-146">そのため、外部には BasicHttpBinding を使用するエンドポイントを通じてサービスを公開し、内部ではルーティング サービスを使用して、そのサービスの NetTcpBinding を使用するエンドポイントにその接続をブリッジしています。</span><span class="sxs-lookup"><span data-stu-id="bc780-146">Thus it exposes its services to the world through an endpoint using the BasicHttpBinding, while internally using the routing service to bridge that connection to the endpoint using NetTcpBinding, which its services use.</span></span> <span data-ttu-id="bc780-147">さらに、Contoso では、運用サービスのいずれかが一時的に停止した場合でも、サービスの提供を継続できるようにしたいと考えています。そのため、ルーター サービスの背後で複数のエンドポイントを仮想化し、必要に応じて、エラー処理機能を使用して自動的にバックアップ エンドポイントにフェールオーバーされるようにしています。</span><span class="sxs-lookup"><span data-stu-id="bc780-147">Furthermore, Contoso wants its service offering to be tolerant of temporary outages in any one of their production services and thus virtualizes multiple endpoints behind the router service using the ’s error handling capabilities to automatically failover to back-up endpoints when necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc780-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc780-148">See Also</span></span>  
 [<span data-ttu-id="bc780-149">AppFabric のホストおよび永続化のサンプル</span><span class="sxs-lookup"><span data-stu-id="bc780-149">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)

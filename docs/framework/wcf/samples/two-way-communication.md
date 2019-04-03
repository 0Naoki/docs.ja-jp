---
title: 双方向通信
ms.date: 03/30/2017
ms.assetid: fb64192d-b3ea-4e02-9fb3-46a508d26c60
ms.openlocfilehash: 3aa01140ef62bd3658696e889038e099ed76da20
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815432"
---
# <a name="two-way-communication"></a><span data-ttu-id="2197f-102">双方向通信</span><span class="sxs-lookup"><span data-stu-id="2197f-102">Two-Way Communication</span></span>
<span data-ttu-id="2197f-103">このサンプルでは、双方向のトランザクション化キューを MSMQ を介して実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2197f-103">This sample demonstrates how to perform transacted two-way queued communication over MSMQ.</span></span> <span data-ttu-id="2197f-104">このサンプルでは、`netMsmqBinding` バインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="2197f-104">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="2197f-105">このサンプルのサービスは自己ホスト型コンソール アプリケーションであるので、サンプルを実行すると、キューに置かれたメッセージをサービスが受信するようすを観察できます。</span><span class="sxs-lookup"><span data-stu-id="2197f-105">In this case, the service is a self-hosted console application that allows you to observe the service receiving queued messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2197f-106">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2197f-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="2197f-107">このサンプルがに基づいて、[トランザクション MSMQ バインディング](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)します。</span><span class="sxs-lookup"><span data-stu-id="2197f-107">This sample is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span></span>  
  
 <span data-ttu-id="2197f-108">キュー通信では、クライアントはサービスとの通信にキューを使用します。</span><span class="sxs-lookup"><span data-stu-id="2197f-108">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="2197f-109">クライアントはメッセージをキューに送信し、サービスはメッセージをキューから受信します。</span><span class="sxs-lookup"><span data-stu-id="2197f-109">The client sends messages to a queue, and the service receives messages from the queue.</span></span> <span data-ttu-id="2197f-110">したがって、キューを使用する通信では、サービスとクライアントが同時に実行されていなくてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="2197f-110">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="2197f-111">このサンプルでは、キューを使用する双方向通信の例を示します。</span><span class="sxs-lookup"><span data-stu-id="2197f-111">This sample demonstrates 2-way communication using queues.</span></span> <span data-ttu-id="2197f-112">クライアントは、トランザクションのスコープ内から発注書をキューに送信します。</span><span class="sxs-lookup"><span data-stu-id="2197f-112">The client sends purchase orders to the queue from within the scope of a transaction.</span></span> <span data-ttu-id="2197f-113">サービスは、注文を受信して処理し、注文ステータスをキューからクライアントに返信します。これらの処理を、トランザクションのスコープ内で実行します。</span><span class="sxs-lookup"><span data-stu-id="2197f-113">The service receives the orders, processes the order and then calls back the client with the status of the order from the queue within the scope of a transaction.</span></span> <span data-ttu-id="2197f-114">双方向通信を使用するには、クライアントとサービスの両方がキューを使用して、発注書や注文ステータスをキューに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2197f-114">To facilitate two-way communication the client and service both use queues to enqueue purchase orders and order status.</span></span>  
  
 <span data-ttu-id="2197f-115">サービス コントラクト `IOrderProcessor` は、キューの使用に合わせた一方向サービス操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="2197f-115">The service contract `IOrderProcessor` defines one-way service operations that suit the use of queuing.</span></span> <span data-ttu-id="2197f-116">サービス操作には、注文ステータスの送信に使用される応答エンドポイントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2197f-116">The service operation includes the reply endpoint to use to send the order statuses to.</span></span> <span data-ttu-id="2197f-117">応答エンドポイントは、注文ステータスをクライアントに返信するためのキューの URI です。</span><span class="sxs-lookup"><span data-stu-id="2197f-117">The reply endpoint is the URI of the queue to send the order status back to the client.</span></span> <span data-ttu-id="2197f-118">注文処理アプリケーションは、このコントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="2197f-118">The order processing application implements this contract.</span></span>  

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true)]  
    void SubmitPurchaseOrder(PurchaseOrder po, string   
                                  reportOrderStatusTo);  
}
```
  
 <span data-ttu-id="2197f-119">注文ステータスを送信する応答コントラクトは、クライアントが指定します。</span><span class="sxs-lookup"><span data-stu-id="2197f-119">The reply contract to send order status is specified by the client.</span></span> <span data-ttu-id="2197f-120">クライアントは注文ステータス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="2197f-120">The client implements the order status contract.</span></span> <span data-ttu-id="2197f-121">サービスは、このコントラクトについて生成されたプロキシを使用して、注文ステータスをクライアントに返信します。</span><span class="sxs-lookup"><span data-stu-id="2197f-121">The service uses the generated proxy of this contract to send order status back to the client.</span></span>  

```csharp
[ServiceContract]  
public interface IOrderStatus  
{  
    [OperationContract(IsOneWay = true)]  
    void OrderStatus(string poNumber, string status);  
}  
```

 <span data-ttu-id="2197f-122">サービス操作は、送信された発注書を処理します。</span><span class="sxs-lookup"><span data-stu-id="2197f-122">The service operation processes the submitted purchase order.</span></span> <span data-ttu-id="2197f-123">サービス操作に適用される <xref:System.ServiceModel.OperationBehaviorAttribute> では、キューからのメッセージ受信に使用されるトランザクションに自動的に帰属することと、サービス操作の完了時にトランザクションを自動的に完了させることが指定されています。</span><span class="sxs-lookup"><span data-stu-id="2197f-123">The <xref:System.ServiceModel.OperationBehaviorAttribute> is applied to the service operation to specify automatic enlistment in a transaction that is used to receive the message from the queue and automatic completion of transactions on completion of the service operation.</span></span> <span data-ttu-id="2197f-124">`Orders` クラスは、注文処理機能をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="2197f-124">The `Orders` class encapsulates order processing functionality.</span></span> <span data-ttu-id="2197f-125">この例では、発注書をディクショナリに追加します。</span><span class="sxs-lookup"><span data-stu-id="2197f-125">In this case, it adds the purchase order to a dictionary.</span></span> <span data-ttu-id="2197f-126">このサービス操作が帰属するしているトランザクションは、`Orders` クラス内の操作で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2197f-126">The transaction that the service operation enlisted in is available to the operations in the `Orders` class.</span></span>  
  
 <span data-ttu-id="2197f-127">サービス操作は、送信された発注書を処理するだけでなく、注文ステータスをクライアントに戻します。</span><span class="sxs-lookup"><span data-stu-id="2197f-127">The service operation, in addition to processing the submitted purchase order, replies back to the client on the status of the order.</span></span>  

```csharp
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)  
{  
    Orders.Add(po);  
    Console.WriteLine("Processing {0} ", po);  
    Console.WriteLine("Sending back order status information");  
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding("ClientCallbackBinding");  
    OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));  
  
    // Please note that the same transaction that is used to dequeue the purchase order is used  
    // to send back order status.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        client.OrderStatus(po.PONumber, po.Status);  
        scope.Complete();  
    }  
    //Close the client.  
    client.Close();  
}  
```

 <span data-ttu-id="2197f-128">MSMQ キュー名は、構成ファイルの appSettings セクションで指定されます。</span><span class="sxs-lookup"><span data-stu-id="2197f-128">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="2197f-129">サービスのエンドポイントは、構成ファイルの System.ServiceModel セクションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="2197f-129">The endpoint for the service is defined in the System.ServiceModel section of the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2197f-130">MSMQ のキュー名とエンドポイント アドレスでは、若干異なるアドレス表記が使用されています。</span><span class="sxs-lookup"><span data-stu-id="2197f-130">The MSMQ queue name and endpoint address use slightly different addressing conventions.</span></span> <span data-ttu-id="2197f-131">MSMQ のキュー名では、ドット (.) を使用してローカル コンピューターを表し、バックスラッシュを使用してパスを区切ります。</span><span class="sxs-lookup"><span data-stu-id="2197f-131">The MSMQ queue name uses a dot (.) for the local machine and backslash separators in its path.</span></span> <span data-ttu-id="2197f-132">Windows Communication Foundation (WCF) エンドポイントのアドレス指定、net.msmq: スキーム、"localhost"を使用して、ローカル コンピューターおよびそのパスにスラッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="2197f-132">The Windows Communication Foundation (WCF) endpoint address specifies a net.msmq: scheme, uses "localhost" for the local machine, and uses forward slashes in its path.</span></span> <span data-ttu-id="2197f-133">リモート コンピューターでホストされているキューからの読み出しを行うには、"." や "localhost" をリモート コンピューター名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2197f-133">To read from a queue that is hosted on the remote machine, replace the "." and "localhost" to the remote machine name.</span></span>  
  
 <span data-ttu-id="2197f-134">サービスは自己ホスト型です。</span><span class="sxs-lookup"><span data-stu-id="2197f-134">The service is self hosted.</span></span> <span data-ttu-id="2197f-135">MSMQ トランスポートを使用する場合、使用するキューをあらかじめ作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="2197f-135">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="2197f-136">手動で作成することもコードで作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2197f-136">This can be done manually or through code.</span></span> <span data-ttu-id="2197f-137">このサンプルでは、サービスがキューの存在を確認し、必要な場合はキューを作成します。</span><span class="sxs-lookup"><span data-stu-id="2197f-137">In this sample, the service checks for the existence of the queue and creates it, if necessary.</span></span> <span data-ttu-id="2197f-138">キュー名は構成ファイルから読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="2197f-138">The queue name is read from the configuration file.</span></span> <span data-ttu-id="2197f-139">ベース アドレスを使って、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)サービスにプロキシを生成します。</span><span class="sxs-lookup"><span data-stu-id="2197f-139">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy to the service.</span></span>  

```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from appSettings in configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the OrderProcessorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {  
        // Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
    }  
}  
```

 <span data-ttu-id="2197f-140">クライアントはトランザクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2197f-140">The client creates a transaction.</span></span> <span data-ttu-id="2197f-141">キューとの通信はトランザクションのスコープ内で実行されるので、全体が 1 つのアトミックな単位として扱われ、すべてのメッセージが成功するか、すべてのメッセージが失敗するかのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="2197f-141">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span>  

```csharp
// Create a ServiceHost for the OrderStatus service type.  
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))  
{  
  
    // Open the ServiceHostBase to create listeners and start listening for order status messages.  
    serviceHost.Open();  
  
    // Create the purchase order.  
    ...  
  
    // Create a client with given client endpoint configuration.  
    OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
    //Create a transaction scope.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        string hostName = Dns.GetHostName();  
  
        // Make a queued call to submit the purchase order.  
        client.SubmitPurchaseOrder(po, "net.msmq://" + hostName + "/private/ServiceModelSamplesTwo-way/OrderStatus");  
  
        // Complete the transaction.  
        scope.Complete();  
    }  
  
    //Close down the client.  
    client.Close();  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
  
    // Close the ServiceHost to shutdown the service.  
    serviceHost.Close();  
}  
```

 <span data-ttu-id="2197f-142">クライアント コードは `IOrderStatus` コントラクトを実装して、サービスからの注文ステータスを受信します。</span><span class="sxs-lookup"><span data-stu-id="2197f-142">The client code implements the `IOrderStatus` contract to receive order status from the service.</span></span> <span data-ttu-id="2197f-143">この場合は、注文ステータスを出力します。</span><span class="sxs-lookup"><span data-stu-id="2197f-143">In this case, it prints out the order status.</span></span>  

```csharp
[ServiceBehavior]  
public class OrderStatusService : IOrderStatus  
{  
    [OperationBehavior(TransactionAutoComplete = true,   
                        TransactionScopeRequired = true)]  
    public void OrderStatus(string poNumber, string status)  
    {  
        Console.WriteLine("Status of order {0}:{1} ", poNumber ,   
                                                           status);  
    }  
}  
```

 <span data-ttu-id="2197f-144">注文ステータス キューは `Main` メソッド内で作成します。</span><span class="sxs-lookup"><span data-stu-id="2197f-144">The order status queue is created in the `Main` method.</span></span> <span data-ttu-id="2197f-145">クライアント構成には、注文ステータス サービスをホストするための注文ステータス サービス構成が含まれています。次のサンプル構成を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2197f-145">The client configuration includes the order status service configuration to host the order status service, as shown in the following sample configuration.</span></span>  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
</appSettings>  
  
<system.serviceModel>  
  
  <services>  
    <service   
       name="Microsoft.ServiceModel.Samples.OrderStatusService">  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
    </service>  
  </services>  
  
  <client>  
    <!-- Define NetMsmqEndpoint -->  
    <endpoint name="OrderProcessorEndpoint"  
              address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"   
              binding="netMsmqBinding"   
              contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
  </client>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="2197f-146">サンプルを実行すると、クライアントとサービスのアクティビティがサービスとクライアントの両方のコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2197f-146">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="2197f-147">サービスがクライアントから受信したメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2197f-147">You can see the service receive messages from the client.</span></span> <span data-ttu-id="2197f-148">どちらかのコンソールで Enter キーを押すと、サービスとクライアントがどちらもシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="2197f-148">Press ENTER in each console window to shut down the service and client.</span></span>  
  
 <span data-ttu-id="2197f-149">サービスによって発注書の情報が表示され、注文ステータスがサービスから注文ステータス キューに返信されることも表示されます。</span><span class="sxs-lookup"><span data-stu-id="2197f-149">The service displays the purchase order information and indicates it is sending back the order status to the order status queue.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 124a1f69-3699-4b16-9bcc-43147a8756fc  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
  
Sending back order status information  
```  
  
 <span data-ttu-id="2197f-150">クライアントには、サービスから送信された注文ステータス情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2197f-150">The client displays the order status information sent by the service.</span></span>  
  
```  
Press <ENTER> to terminate client.  
Status of order 124a1f69-3699-4b16-9bcc-43147a8756fc:Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2197f-151">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="2197f-151">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2197f-152">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="2197f-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="2197f-153">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2197f-153">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="2197f-154">1 つまたは複数コンピュータ構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="2197f-154">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2197f-155">Svcutil.exe を使用してこのサンプルの構成を再生成した場合は、クライアント コードに一致するように、クライアント構成内のエンドポイント名を変更してください。</span><span class="sxs-lookup"><span data-stu-id="2197f-155">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint names in the client configuration to match the client code.</span></span>  
  
 <span data-ttu-id="2197f-156"><xref:System.ServiceModel.NetMsmqBinding> を使用する場合の既定では、トランスポート セキュリティが有効です。</span><span class="sxs-lookup"><span data-stu-id="2197f-156">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="2197f-157">MSMQ トランスポート セキュリティでは、2 つの関連するプロパティがある<xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>と<xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.`既定では、認証モードが設定されて`Windows`保護レベルに設定し、`Sign`します。</span><span class="sxs-lookup"><span data-stu-id="2197f-157">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="2197f-158">MSMQ の認証機能と署名機能を利用するには、ドメインに MSMQ があることと、MSMQ に関する Active Directory の統合オプションがインストールされていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="2197f-158">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="2197f-159">この条件を満たしていないコンピューターでこのサンプルを実行すると、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="2197f-159">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="2197f-160">ワークグループに属しているコンピューターまたは Active Directory 統合のないコンピューターでこのサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="2197f-160">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1.  <span data-ttu-id="2197f-161">ドメインに属していないコンピュータ、または Active Directory 統合がインストールされていないコンピュータを使用する場合は、トランスポート セキュリティをオフにします。オフにするには、認証モードと保護レベルを `None` にします。この構成の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2197f-161">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>  
  
    ```xml  
    <configuration>  
  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderProcessor" />  
      </appSettings>  
  
      <system.serviceModel>  
        <services>  
          <service   
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding"   
                      contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          </service>  
        </services>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
2.  <span data-ttu-id="2197f-162">クライアント構成のセキュリティをオフにすると、次のコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2197f-162">Turning off security for a client configuration generates the following:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
      </appSettings>  
  
      <system.serviceModel>  
  
        <services>  
          <service   
             name="Microsoft.ServiceModel.Samples.OrderStatusService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding" contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
          </service>  
        </services>  
  
        <client>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint name="OrderProcessorEndpoint"  
                    address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"   
                    binding="netMsmqBinding"   
                    bindingConfiguration="TransactedBinding"  
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
        </client>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
3.  <span data-ttu-id="2197f-163">このサンプルのサービスは、`OrderProcessorService` でバインディングを作成します。</span><span class="sxs-lookup"><span data-stu-id="2197f-163">The service for this sample creates a binding in the `OrderProcessorService`.</span></span> <span data-ttu-id="2197f-164">このバインディングをインスタンス化した後に、コード行を 1 行追加して、セキュリティ モードを `None` に設定します。</span><span class="sxs-lookup"><span data-stu-id="2197f-164">Add a line of code after the binding is instantiated to set the security mode to `None`.</span></span>  
  
    ```csharp
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();  
    msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;  
    ```  
  
4.  <span data-ttu-id="2197f-165">サーバーとクライアントの両方の構成を変更したことを確認してから、サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="2197f-165">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2197f-166">`security mode` を `None` に設定することは、<xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>、<xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>、または `Message` のセキュリティを `None` に設定することに相当します。</span><span class="sxs-lookup"><span data-stu-id="2197f-166">Setting `security mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> or `Message` security to `None`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2197f-167">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="2197f-167">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2197f-168">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2197f-168">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2197f-169">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="2197f-169">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2197f-170">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2197f-170">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\Net\MSMQ\Two-Way`  
  

---
title: "Windows Communication Foundation へのメッセージ キュー | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d718eb0-9f61-4653-8a75-d2dac8fb3520
caps.latest.revision: 34
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 34
---
# Windows Communication Foundation へのメッセージ キュー
このサンプルでは、メッセージ キュー \(MSMQ\) アプリケーションで MSMQ メッセージを [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] サービスに送信する方法について説明します。サービスは、自己ホスト型コンソール アプリケーションで、サービスがキュー内のメッセージを受信したかどうかを監視できます。  
  
 サービス コントラクトは `IOrderProcessor` です。これは、キューでの使用に適した一方向サービスを定義します。MSMQ メッセージには Action ヘッダーがないので、さまざまな MSMQ メッセージを操作コントラクトに自動的にマッピングすることはできません。したがって、存在する操作コントラクトは 1 つだけです。サービスに対して複数の操作コントラクトを定義する場合は、ディスパッチする操作コントラクトを決定するために使用できる、MSMQ メッセージ内のヘッダー \(ラベルや correlationID など\) に関する情報をアプリケーションで提供する必要があります。これについては、「[カスタム Demux](../../../../docs/framework/wcf/samples/custom-demux.md)」を参照してください。  
  
 MSMQ メッセージには、操作コントラクトの別のパラメータにマッピングされるヘッダーに関する情報は含まれません。パラメータは <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601> 型の `MsmqMessage<T>` です。これには、基になる MSMQ メッセージが含まれます。<xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601> \(`MsmqMessage<T>`\) クラスの型 "T" は、シリアル化されて MSMQ メッセージ本文に含まれているデータを表します。このサンプルでは、`PurchaseOrder` 型がシリアル化されて MSMQ メッセージ本文になっています。  
  
 発注書処理サービスのサービス コントラクトを次のサンプル コードに示します。  
  
```  
// Define a service contract.  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[ServiceKnownType(typeof(PurchaseOrder))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Action = "*")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
}  
  
```  
  
 サービスは自己ホスト型です。MSMQ を使用する場合、使用するキューをあらかじめ作成しておく必要があります。手動で作成することもコードで作成することもできます。このサンプルでは、サービスはキューの存在を確認し、必要な場合はキューを作成します。キュー名は構成ファイルから読み込まれます。  
  
```  
public static void Main()  
{  
    // Get the MSMQ queue name from the application settings in   
    // configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
    // Create the MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
    …  
}  
  
```  
  
 サービスは、`OrderProcessorService` の <xref:System.ServiceModel.ServiceHost> を作成して開きます。次のサンプル コードを参照してください。  
  
```  
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
{  
    serviceHost.Open();  
    Console.WriteLine("The service is ready.");  
    Console.WriteLine("Press <ENTER> to terminate service.");  
    Console.ReadLine();  
    serviceHost.Close();  
}  
  
```  
  
 MSMQ キュー名は、構成ファイルの appSettings セクションに指定されます。次のサンプル構成を参照してください。  
  
> [!NOTE]
>  キュー名では、ドット \(.\) を使用してローカル コンピューターを表し、バックスラッシュを使用してパスを区切ります。[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] エンドポイント アドレスでは msmq.formatname スキームが指定され、ローカル コンピューターを表す localhost が使用されます。それぞれの MSMQ 形式名のアドレス指定ガイドラインに対するキューのアドレスが msmq.formatname スキームの後に続きます。  
  
```  
<appSettings>  
    <add key="orderQueueName" value=".\private$\Orders" />  
</appSettings>  
  
```  
  
 クライアント アプリケーションは MSMQ アプリケーションです。このアプリケーションでは <xref:System.Messaging.MessageQueue.Send%2A> メソッドを使用して、非揮発性メッセージとトランザクション メッセージをキューに送信します。次のサンプル コードを参照してください。  
  
```  
//Connect to the queue.  
MessageQueue orderQueue = new MessageQueue(ConfigurationManager.AppSettings["orderQueueName"]);  
  
// Create the purchase order.  
PurchaseOrder po = new PurchaseOrder();  
po.CustomerId = "somecustomer.com";  
po.PONumber = Guid.NewGuid().ToString();  
  
PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
lineItem1.ProductId = "Blue Widget";  
lineItem1.Quantity = 54;  
lineItem1.UnitCost = 29.99F;  
  
PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();  
lineItem2.ProductId = "Red Widget";  
lineItem2.Quantity = 890;  
lineItem2.UnitCost = 45.89F;  
  
po.orderLineItems = new PurchaseOrderLineItem[2];  
po.orderLineItems[0] = lineItem1;  
po.orderLineItems[1] = lineItem2;  
  
// Submit the purchase order.  
Message msg = new Message();  
msg.Body = po;  
//Create a transaction scope.  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
  
    orderQueue.Send(msg, MessageQueueTransactionType.Automatic);  
    // Complete the transaction.  
    scope.Complete();  
  
}  
Console.WriteLine("Placed the order:{0}", po);  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
  
```  
  
 サンプルを実行すると、クライアントとサービスのアクティビティがサービスとクライアントの両方のコンソール ウィンドウに表示されます。サービスがクライアントからメッセージを受信するようすがわかります。どちらかのコンソールで Enter キーを押すと、サービスとクライアントがどちらもシャットダウンされます。キューが使用されているので、クライアントとサービスが同時に実行されている必要はありません。たとえば、クライアントを実行してシャットダウンした後にサービスを起動しても、サービスはメッセージを受信します。  
  
### サンプルをセットアップ、ビルド、および実行するには  
  
1.  「[Windows Communication Foundation サンプルの 1 回限りのセットアップの手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)」が実行済みであることを確認します。  
  
2.  サービスを最初に実行すると、サービスはキューが存在するかどうかを確認します。キューが存在しない場合、サービスによってキューが作成されます。最初にサービスを実行してキューを作成することも、MSMQ キュー マネージャーでキューを作成することもできます。Windows 2008 でキューを作成するには、次の手順に従います。  
  
    1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] でサーバー マネージャーを開きます。  
  
    2.  **\[機能\]** タブを展開します。  
  
    3.  **\[プライベート メッセージ キュー\]** を右クリックし、**\[新規作成\]**、**\[専用キュー\]** の順にクリックします。  
  
    4.  **\[トランザクション\]** ボックスをオンにします。  
  
    5.  新しいキューの名前として、「`ServiceModelSamplesTransacted`」と入力します。  
  
3.  ソリューションの C\# 版または Visual Basic .NET 版をビルドするには、「[Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。  
  
4.  単一コンピューター構成でサンプルを実行するには、「[Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)」の手順に従います。  
  
### サンプルを複数のコンピューターで実行するには  
  
1.  サービスのプログラム ファイルを、言語固有のフォルダーにある \\service\\bin\\ フォルダーからサービス コンピューターにコピーします。  
  
2.  クライアント プログラム ファイルを、言語固有のフォルダーにある \\client\\bin\\ フォルダーからクライアント コンピューターにコピーします。  
  
3.  Client.exe.config ファイルを開き、orderQueueName を変更して "." の代わりにサービス コンピューター名を指定します。  
  
4.  サービス コンピューターで、コマンド プロンプトから Service.exe を起動します。  
  
5.  クライアント コンピューターで、コマンド プロンプトから Client.exe を起動します。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。続行する前に、次の \(既定の\) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合は、「[.NET Framework 4 向けの Windows Communication Foundation \(WCF\) および Windows Workflow Foundation \(WF\) のサンプル](http://go.microsoft.com/fwlink/?LinkId=150780)」にアクセスして、[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] および [!INCLUDE[wf1](../../../../includes/wf1-md.md)] のサンプルをすべてダウンロードしてください。このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MsmqToWcf`  
  
## 参照  
 [WCF のキュー](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [方法 : WCF エンドポイントとメッセージ キュー アプリケーションを使用してメッセージを交換する](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)   
 [メッセージ キュー](http://go.microsoft.com/fwlink/?LinkId=94968)
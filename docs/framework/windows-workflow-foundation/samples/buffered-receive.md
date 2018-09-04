---
title: バッファーされた受信機能
ms.date: 03/30/2017
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
ms.openlocfilehash: b95577c71493275f30703b4366fab32a51097bd2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526805"
---
# <a name="buffered-receive"></a><span data-ttu-id="6e145-102">バッファーされた受信機能</span><span class="sxs-lookup"><span data-stu-id="6e145-102">Buffered Receive</span></span>
<span data-ttu-id="6e145-103">このサンプルを設定して、Windows Workflow Foundation (WF) のバッファーされた受信機能を構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6e145-103">This sample demonstrates how to set up and configure the buffered receive feature in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="6e145-104">バッファーされた受信機能を使用すると、ワークフロー作成者は、メッセージが受信される順序を考慮することなくワークフローを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6e145-104">Buffered receive allows the workflow author to create a workflow without having to worry about the order in which messages are received.</span></span> <span data-ttu-id="6e145-105">バッファーされた受信機能では、メッセージがローカルにバッファーされ、ワークフローで受信準備が整ったときにメッセージが配信されます。</span><span class="sxs-lookup"><span data-stu-id="6e145-105">The buffered receive feature buffers messages locally and delivers them when the workflow is ready to receive them.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="6e145-106">使用例</span><span class="sxs-lookup"><span data-stu-id="6e145-106">Demonstrates</span></span>  
 <span data-ttu-id="6e145-107">メッセージング アクティビティと共にバッファーされた受信機能を使用した、順番を無視したメッセージ処理。</span><span class="sxs-lookup"><span data-stu-id="6e145-107">Out-of-order message processing using buffered receive with messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6e145-108">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e145-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6e145-109">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6e145-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6e145-110">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="6e145-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6e145-111">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6e145-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## <a name="discussion"></a><span data-ttu-id="6e145-112">説明</span><span class="sxs-lookup"><span data-stu-id="6e145-112">Discussion</span></span>  
 <span data-ttu-id="6e145-113">使用してこのサンプルでは、Windows Communication Foundation (WCF) サービスが実装は[!INCLUDE[wf1](../../../../includes/wf1-md.md)]のシーケンスがあります<xref:System.ServiceModel.Activities.Receive>アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="6e145-113">In this sample, a Windows Communication Foundation (WCF) service is implemented using [!INCLUDE[wf1](../../../../includes/wf1-md.md)] and has a sequence of <xref:System.ServiceModel.Activities.Receive> activities.</span></span> <span data-ttu-id="6e145-114">このワークフローは、ローン承認のための 3 つの通知を受け取る単純なローン承認プロセスをモデル化しています。</span><span class="sxs-lookup"><span data-stu-id="6e145-114">This workflow models a simple loan approval process where the workflow expects three notifications for a loan to be approved.</span></span> <span data-ttu-id="6e145-115">Windows Communication Foundation (WCF) クライアント アプリケーションでは、サービスが要求の逆の順序で次の 3 つの関連付けられた通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="6e145-115">A Windows Communication Foundation (WCF) client application sends three correlated notifications in the reverse order of what the service expects.</span></span> <span data-ttu-id="6e145-116">サービスでバッファーされた受信機能が有効になっているので、順番を無視した各メッセージがサービスにバッファーされ、ワークフローで受信準備が整ったときに処理されます。</span><span class="sxs-lookup"><span data-stu-id="6e145-116">Because the buffered receive feature is turned on at the service, each out-of-order message is buffered at the service and processed as the workflow becomes ready to receive it.</span></span>  
  
 <span data-ttu-id="6e145-117">バッファーされた受信機能では、バインディングによる <xref:System.ServiceModel.Activities.ReceiveContent> のサポートが必要なので、サービスで <xref:System.ServiceModel.NetMsmqBinding> が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e145-117">The buffered receive feature requires <xref:System.ServiceModel.Activities.ReceiveContent> support from the binding, therefore the service uses <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="6e145-118">バインディングのための特別な構成は不要なので、既定の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e145-118">No special configuration is required for the binding, so the defaults are used.</span></span>  
  
```xml  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
```  
  
 <span data-ttu-id="6e145-119">また、サービスでは、<xref:System.ServiceModel.Description.ServiceMetadataBehavior> を使用してサービスのメタデータが公開されます。</span><span class="sxs-lookup"><span data-stu-id="6e145-119">The service also exposes metadata for the service using <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span></span>  
  
 <span data-ttu-id="6e145-120">同様に、<xref:System.ServiceModel.NetMsmqBinding> を使用してクライアント エンドポイントが構成されます。</span><span class="sxs-lookup"><span data-stu-id="6e145-120">Similarly, the client endpoint is configured using <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="6e145-121">クライアント コードと構成を使用して生成されて、**サービス参照の追加**Visual Studio の機能です。</span><span class="sxs-lookup"><span data-stu-id="6e145-121">The client code and configuration is generated by using the **Add Service Reference** feature of Visual Studio.</span></span> <span data-ttu-id="6e145-122">App.config ファイルで生成されたクライアント エンドポイントを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="6e145-122">The following example is the generated client endpoint in the App.config file.</span></span>  
  
```xml  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
```  
  
 <span data-ttu-id="6e145-123">このサンプルでは、次の Windows コンポーネントが有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e145-123">This sample requires that the following Windows components are enabled:</span></span>  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]<span data-ttu-id="6e145-124"> と互換性のある管理、IIS メタベースおよび IIS 6 構成との互換性</span><span class="sxs-lookup"><span data-stu-id="6e145-124"> Management Compatibility, Metabase, and Configuration Compatibility</span></span>  
  
3.  <span data-ttu-id="6e145-125">World Wide Web サービス、アプリケーション開発機能、および ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6e145-125">World Wide Web Services, Application Development Features, and ASP.NET</span></span>  
  
4.  <span data-ttu-id="6e145-126">Microsoft メッセージ キュー (MSMQ) サーバー</span><span class="sxs-lookup"><span data-stu-id="6e145-126">Microsoft Message Queues (MSMQ) Server</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="6e145-127">サンプルをセットアップしてビルドするには</span><span class="sxs-lookup"><span data-stu-id="6e145-127">To set up, and build the sample</span></span>  
  
1.  <span data-ttu-id="6e145-128">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] コマンド プロンプトで、「`aspnet_regiis –I`」と入力して ASP.NET を登録し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6e145-128">At a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by typing `aspnet_regiis –I` and press ENTER.</span></span>  
  
2.  <span data-ttu-id="6e145-129">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="6e145-129">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an Administrator.</span></span>  
  
3.  <span data-ttu-id="6e145-130">LoanService.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="6e145-130">Open LoanService.sln.</span></span>  
  
4.  <span data-ttu-id="6e145-131">LoanService プロジェクト用の仮想ディレクトリを作成する場合は、選択を求められたら**はい**します。</span><span class="sxs-lookup"><span data-stu-id="6e145-131">When asked if you would like to create the virtual directories for the LoanService project, select **Yes**.</span></span>  
  
#### <a name="to-set-up-the-service-queues"></a><span data-ttu-id="6e145-132">サービス キューを設定するには</span><span class="sxs-lookup"><span data-stu-id="6e145-132">To set up the service queues</span></span>  
  
1.  <span data-ttu-id="6e145-133">F5 キーを押して LoanClient アプリケーションを実行し、キューを作成して Service1.xamlx で定義されたサービスをアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="6e145-133">Press F5 to run the LoanClient application that creates the queues and activates the service defined in Service1.xamlx.</span></span>  
  
2.  <span data-ttu-id="6e145-134">開く、**コンピュータの管理**コンソールで、コマンド プロンプトから Compmgmt.msc を実行します。</span><span class="sxs-lookup"><span data-stu-id="6e145-134">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
3.  <span data-ttu-id="6e145-135">**コンピュータの管理**コンソールで、**サービス**、**アプリケーション**、**メッセージ キュー**、**専用キュー**.</span><span class="sxs-lookup"><span data-stu-id="6e145-135">In the **Computer Management** console, expand **Service**, **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
4.  <span data-ttu-id="6e145-136">Loanservice/service1.xamlx キューを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="6e145-136">Right-click the loanservice/service1.xamlx queue and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="6e145-137">選択、**セキュリティ**タブをクリックし、追加**のすべてのユーザーは受信メッセージ**、**メッセージのピーク**と**メッセージの送信**アクセス許可。</span><span class="sxs-lookup"><span data-stu-id="6e145-137">Select the **Security** tab, and add **Everyone Receives Message**, **Peek Message** and **Send Message** permissions.</span></span>  
  
6.  <span data-ttu-id="6e145-138">[!INCLUDE[iis60](../../../../includes/iis60-md.md)] マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e145-138">Open the [!INCLUDE[iis60](../../../../includes/iis60-md.md)] Manager.</span></span>  
  
7.  <span data-ttu-id="6e145-139">参照する**Server**、**サイト**、 **Default Web site**、**プライベート**、 **LoanService** を選択します。**高度なオプション**</span><span class="sxs-lookup"><span data-stu-id="6e145-139">Browse to **Server**, **Sites**, **Default Web site**, **Private**, **LoanService** and select **Advanced Options**</span></span>  
  
8.  <span data-ttu-id="6e145-140">変更、**有効なプロトコル**する**http**、 **net.msmq**します。</span><span class="sxs-lookup"><span data-stu-id="6e145-140">Change the **Enabled Protocols** to be **http**, **net.msmq**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="6e145-141">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="6e145-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="6e145-142">参照する http://localhost/private/loanservice/service1.xamlxにサービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e145-142">Browse to http://localhost/private/loanservice/service1.xamlx to ensure that the service is running.</span></span>  
  
2.  <span data-ttu-id="6e145-143">F5 キーを押して LoanClient アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e145-143">Press F5 to run the LoanClient application.</span></span> <span data-ttu-id="6e145-144">ワークフローが完了したら、メッセージ交換の結果を示す out.txt ファイルが C:\Inbox に保存されます。</span><span class="sxs-lookup"><span data-stu-id="6e145-144">Once the workflow is complete, an out.txt file should be saved to C:\Inbox that contains the result of the message exchange.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="6e145-145">クリーンアップするには</span><span class="sxs-lookup"><span data-stu-id="6e145-145">To clean up</span></span>  
  
1.  <span data-ttu-id="6e145-146">開く、**コンピュータの管理**コンソールで、コマンド プロンプトから Compmgmt.msc を実行します。</span><span class="sxs-lookup"><span data-stu-id="6e145-146">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
2.  <span data-ttu-id="6e145-147">展開**サービス**と**アプリケーション**、**メッセージ キュー**、**専用キュー**します。</span><span class="sxs-lookup"><span data-stu-id="6e145-147">Expand **Service** and **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
3.  <span data-ttu-id="6e145-148">loanservice/service1.xamlx キューを削除します。</span><span class="sxs-lookup"><span data-stu-id="6e145-148">Delete the loanservice/service1.xamlx queue.</span></span>  
  
4.  <span data-ttu-id="6e145-149">C:\Inbox ディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="6e145-149">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6e145-150">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e145-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6e145-151">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6e145-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6e145-152">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="6e145-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6e145-153">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6e145-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`

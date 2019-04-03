---
title: デザイン パターン:リストに基づく公開/定期受信
ms.date: 03/30/2017
ms.assetid: f4257abc-12df-4736-a03b-0731becf0fd4
ms.openlocfilehash: 59b56ce5b3be031a598c690976d5f9c23932fc66
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815031"
---
# <a name="design-patterns-list-based-publish-subscribe"></a><span data-ttu-id="f8722-102">デザイン パターン:リストに基づく公開/定期受信</span><span class="sxs-lookup"><span data-stu-id="f8722-102">Design Patterns: List-Based Publish-Subscribe</span></span>
<span data-ttu-id="f8722-103">このサンプルでは、Windows Communication Foundation (WCF) プログラムとして実装されたリストに基づく公開/定期受信パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="f8722-103">This sample illustrates the List-based Publish-Subscribe pattern implemented as a Windows Communication Foundation (WCF) program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8722-104">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8722-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="f8722-105">リストに基づく公開/定期受信デザイン パターンは、Microsoft Patterns & Practices の文書に記載されて[統合パターン](https://go.microsoft.com/fwlink/?LinkId=95894)します。</span><span class="sxs-lookup"><span data-stu-id="f8722-105">The List-based Publish-Subscribe design pattern is described in the Microsoft Patterns & Practices publication, [Integration Patterns](https://go.microsoft.com/fwlink/?LinkId=95894).</span></span> <span data-ttu-id="f8722-106">公開/定期受信パターンは、情報トピックを定期受信する受信者のコレクションに情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="f8722-106">The Publish-Subscribe pattern passes information to a collection of recipients who have subscribed to an information topic.</span></span> <span data-ttu-id="f8722-107">リストに基づく公開/定期受信では、サブスクライバのリストが保持されます。</span><span class="sxs-lookup"><span data-stu-id="f8722-107">List-based publish-subscribe maintains a list of subscribers.</span></span> <span data-ttu-id="f8722-108">共有情報が存在する場合は、コピーがリスト上の各サブスクライバに送信されます。</span><span class="sxs-lookup"><span data-stu-id="f8722-108">When there is information to share, a copy is sent to each subscriber on the list.</span></span> <span data-ttu-id="f8722-109">このサンプルでは、動的なリストに基づく公開/定期受信パターンを示します。これにより、クライアントは必要に応じて何度でも定期受信または定期受信の解除ができます。</span><span class="sxs-lookup"><span data-stu-id="f8722-109">This sample demonstrates a dynamic list-based publish-subscribe pattern, where clients can subscribe or unsubscribe as often as required.</span></span>  
  
 <span data-ttu-id="f8722-110">リストに基づく公開/定期受信のサンプルは、クライアント、サービス、およびデータ ソース プログラムで構成されています。</span><span class="sxs-lookup"><span data-stu-id="f8722-110">The List-based Publish-Subscribe sample consists of a client, a service, and a data source program.</span></span> <span data-ttu-id="f8722-111">クライアントとデータ ソース プログラムは、複数を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f8722-111">There can be more than one client and more than one data source program running.</span></span> <span data-ttu-id="f8722-112">クライアントはサービスを定期受信し、通知を受信して、定期受信を解除します。</span><span class="sxs-lookup"><span data-stu-id="f8722-112">Clients subscribe to the service, receive notifications, and unsubscribe.</span></span> <span data-ttu-id="f8722-113">データ ソース プログラムはサービスに情報を送信し、現在のすべてのサブスクライバでその情報が共有されるようにします。</span><span class="sxs-lookup"><span data-stu-id="f8722-113">Data source programs send information to the service to be shared with all current subscribers.</span></span>  
  
 <span data-ttu-id="f8722-114">このサンプルでは、クライアントとデータ ソースはコンソール プログラム (.exe ファイル) で、サービスはインターネット インフォメーション サービス (IIS) でホストされるライブラリ (.dll) です。</span><span class="sxs-lookup"><span data-stu-id="f8722-114">In this sample, the client and data source are console programs (.exe files) and the service is a library (.dll) hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="f8722-115">クライアントとデータ ソースのアクティビティは、デスクトップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8722-115">Client and data source activity are visible on the desktop.</span></span>  
  
 <span data-ttu-id="f8722-116">サービスは、双方向通信を使用します。</span><span class="sxs-lookup"><span data-stu-id="f8722-116">The service uses duplex communication.</span></span> <span data-ttu-id="f8722-117">`ISampleContract` サービス コントラクトは `ISampleClientCallback` コールバック コントラクトと対になっています。</span><span class="sxs-lookup"><span data-stu-id="f8722-117">The `ISampleContract` service contract is paired up with an `ISampleClientCallback` callback contract.</span></span> <span data-ttu-id="f8722-118">サービスは Subscribe および Unsubscribe サービス操作を実装します。クライアントはこれらのサービス操作を使用してサブスクライバのリストに参加またはリストへの参加を解除します。</span><span class="sxs-lookup"><span data-stu-id="f8722-118">The service implements Subscribe and Unsubscribe service operations, which clients use to join or leave the list of subscribers.</span></span> <span data-ttu-id="f8722-119">サービスは、さらに `PublishPriceChange` サービス操作も実装します。データ ソース プログラムはこれを呼び出して、新しい情報をサービスに提供します。</span><span class="sxs-lookup"><span data-stu-id="f8722-119">The service also implements the `PublishPriceChange` service operation, which the data source program calls to provide the service with new information.</span></span> <span data-ttu-id="f8722-120">クライアント プログラムは `PriceChange` サービス操作を実装します。サービスはこれを呼び出して、すべてのサブスクライバに価格の変更を通知します。</span><span class="sxs-lookup"><span data-stu-id="f8722-120">The client program implements the `PriceChange` service operation, which the service calls to notify all subscribers of a price change.</span></span>  
  
```  
// Create a service contract and define the service operations.  
// NOTE: The service operations must be declared explicitly.  
[ServiceContract(SessionMode=SessionMode.Required,  
      CallbackContract=typeof(ISampleClientContract))]  
public interface ISampleContract  
{  
    [OperationContract(IsOneWay = false, IsInitiating=true)]  
    void Subscribe();  
    [OperationContract(IsOneWay = false, IsTerminating=true)]  
    void Unsubscribe();  
    [OperationContract(IsOneWay = true)]  
    void PublishPriceChange(string item, double price,   
                                     double change);  
}  
  
public interface ISampleClientContract  
{  
    [OperationContract(IsOneWay = true)]  
    void PriceChange(string item, double price, double change);  
}  
```  
  
 <span data-ttu-id="f8722-121">サービスは、すべてのサブスクライバに新しい情報を通知する機構として、.NET Framework イベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f8722-121">The service uses a .NET Framework event as the mechanism to inform all subscribers about new information.</span></span> <span data-ttu-id="f8722-122">クライアントが Subscribe を呼び出してサービスに参加すると、イベント ハンドラが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f8722-122">When a client joins the service by calling Subscribe, it provides an event handler.</span></span> <span data-ttu-id="f8722-123">クライアントがサービスへの参加を解除すると、イベントからイベント ハンドラの定期受信が解除されます。</span><span class="sxs-lookup"><span data-stu-id="f8722-123">When a client leaves, it unsubscribes its event handler from the event.</span></span> <span data-ttu-id="f8722-124">データ ソースが価格の変更を報告するサービスを呼び出すと、サービスはイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="f8722-124">When a data source calls the service to report a price change, the service raises the event.</span></span> <span data-ttu-id="f8722-125">これにより、サービスの各インスタンスが呼び出されます。このサービスは定期受信した各クライアントのサービスで、この呼び出しによって各インスタンスのイベント ハンドラが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f8722-125">This calls each instance of the service, one for each client that has subscribed, and causes their event handlers to execute.</span></span> <span data-ttu-id="f8722-126">各イベント ハンドラは、コールバック関数を使用してクライアントに情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="f8722-126">Each event handler passes the information to its client through its callback function.</span></span>  
  
```  
public class PriceChangeEventArgs : EventArgs  
    {  
        public string Item;  
        public double Price;  
        public double Change;  
    }  
  
    // The Service implementation implements your service contract.  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    public class SampleService : ISampleContract  
    {  
        public static event PriceChangeEventHandler PriceChangeEvent;  
        public delegate void PriceChangeEventHandler(object sender, PriceChangeEventArgs e);  
  
        ISampleClientContract callback = null;  
  
        PriceChangeEventHandler priceChangeHandler = null;  
  
        //Clients call this service operation to subscribe.  
        //A price change event handler is registered for this client instance.  
  
        public void Subscribe()  
        {  
            callback = OperationContext.Current.GetCallbackChannel<ISampleClientContract>();  
            priceChangeHandler = new PriceChangeEventHandler(PriceChangeHandler);  
            PriceChangeEvent += priceChangeHandler;  
        }  
  
        //Clients call this service operation to unsubscribe.  
        //The previous price change event handler is unregistered.  
  
        public void Unsubscribe()  
        {  
            PriceChangeEvent -= priceChangeHandler;  
        }  
  
        //Information source clients call this service operation to report a price change.  
        //A price change event is raised. The price change event handlers for each subscriber will execute.  
  
        public void PublishPriceChange(string item, double price, double change)  
        {  
            PriceChangeEventArgs e = new PriceChangeEventArgs();  
            e.Item = item;  
            e.Price = price;  
            e.Change = change;  
            PriceChangeEvent(this, e);  
        }  
  
        //This event handler runs when a PriceChange event is raised.  
        //The client's PriceChange service operation is invoked to provide notification about the price change.  
  
        public void PriceChangeHandler(object sender, PriceChangeEventArgs e)  
        {  
            callback.PriceChange(e.Item, e.Price, e.Change);  
        }  
  
    }  
```  
  
 <span data-ttu-id="f8722-127">このサンプルを実行すると、複数のクライアントが起動されます。</span><span class="sxs-lookup"><span data-stu-id="f8722-127">When you run the sample, launch several clients.</span></span> <span data-ttu-id="f8722-128">クライアントはサービスを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="f8722-128">The clients subscribe to the service.</span></span> <span data-ttu-id="f8722-129">次にデータ ソース プログラムが実行され、サービスに情報が送信されます。</span><span class="sxs-lookup"><span data-stu-id="f8722-129">Then run the data source program, which sends information to the service.</span></span> <span data-ttu-id="f8722-130">サービスは、すべてのサブスクライバに情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="f8722-130">The service passes on the information to all subscribers.</span></span> <span data-ttu-id="f8722-131">各クライアント コンソールでアクティビティを表示し、情報が受信されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f8722-131">You can see activity on each client console confirming that the information has been received.</span></span> <span data-ttu-id="f8722-132">クライアントをシャットダウンするには、クライアント ウィンドウで Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f8722-132">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="f8722-133">サンプルをセットアップしてビルドするには</span><span class="sxs-lookup"><span data-stu-id="f8722-133">To set up and build the sample</span></span>  
  
1.  <span data-ttu-id="f8722-134">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="f8722-134">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="f8722-135">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f8722-135">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="f8722-136">サンプルを同じコンピューターで実行するには</span><span class="sxs-lookup"><span data-stu-id="f8722-136">To run the sample on the same machine</span></span>  
  
1.  <span data-ttu-id="f8722-137">次のアドレスを入力して、ブラウザーを使用して、サービスにアクセスできることのテスト:`http://localhost/servicemodelsamples/service.svc`します。</span><span class="sxs-lookup"><span data-stu-id="f8722-137">Test that you can access the service using a browser by entering the following address: `http://localhost/servicemodelsamples/service.svc`.</span></span> <span data-ttu-id="f8722-138">これに応答して、確認ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8722-138">A confirmation page should be displayed in response.</span></span>  
  
2.  <span data-ttu-id="f8722-139">Client.exe を \client\bin 実行\\、言語固有のフォルダーの下。</span><span class="sxs-lookup"><span data-stu-id="f8722-139">Run Client.exe from \client\bin\\, from under the language-specific folder.</span></span> <span data-ttu-id="f8722-140">クライアント アクティビティがクライアント コンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8722-140">Client activity is displayed on the client console window.</span></span> <span data-ttu-id="f8722-141">複数のクライアントを起動します。</span><span class="sxs-lookup"><span data-stu-id="f8722-141">Launch several clients.</span></span>  
  
3.  <span data-ttu-id="f8722-142">\Datasource\bin から Datasource.exe を実行\\、言語固有のフォルダーの下。</span><span class="sxs-lookup"><span data-stu-id="f8722-142">Run Datasource.exe from \datasource\bin\\, from under the language-specific folder.</span></span> <span data-ttu-id="f8722-143">データ ソース アクティビティがコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8722-143">Data source activity is displayed on the console window.</span></span> <span data-ttu-id="f8722-144">データ ソースがサービスに情報を送信すると、その情報は各クライアントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="f8722-144">Once the data source sends information to the service, it should be passed on to each client.</span></span>  
  
4.  <span data-ttu-id="f8722-145">クライアント、データ ソース、およびサービス プログラムが通信できるようにされていない場合[WCF サンプルのトラブルシューティングのヒント](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))します。</span><span class="sxs-lookup"><span data-stu-id="f8722-145">If the client, data source, and service programs are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="f8722-146">サンプルを複数コンピューターで実行するには</span><span class="sxs-lookup"><span data-stu-id="f8722-146">To run the sample across machines</span></span>  
  
1.  <span data-ttu-id="f8722-147">サービス コンピュータを設定します。</span><span class="sxs-lookup"><span data-stu-id="f8722-147">Set up the service machine:</span></span>  
  
    1.  <span data-ttu-id="f8722-148">サービス コンピューターで、ServiceModelSamples という仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f8722-148">On the service machine, create a virtual directory named ServiceModelSamples.</span></span> <span data-ttu-id="f8722-149">バッチ ファイル Setupvroot.bat ファイル、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ディスク ディレクトリと仮想ディレクトリを作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="f8722-149">The batch file Setupvroot.bat from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) can be used to create the disk directory and virtual directory.</span></span>  
  
    2.  <span data-ttu-id="f8722-150">サービス プログラム ファイルを %SystemDrive%\Inetpub\wwwroot\servicemodelsamples からサービス コンピューターの ServiceModelSamples 仮想ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f8722-150">Copy the service program files from %SystemDrive%\Inetpub\wwwroot\servicemodelsamples to the ServiceModelSamples virtual directory on the service machine.</span></span> <span data-ttu-id="f8722-151">\bin ディレクトリのファイルが含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f8722-151">Be sure to include the files in the \bin directory.</span></span>  
  
    3.  <span data-ttu-id="f8722-152">ブラウザーを使用して、サービスにクライアント コンピューターからアクセスできるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="f8722-152">Test that you can access the service from the client machine using a browser.</span></span>  
  
2.  <span data-ttu-id="f8722-153">クライアント コンピュータを設定します。</span><span class="sxs-lookup"><span data-stu-id="f8722-153">Set up the client machines:</span></span>  
  
    1.  <span data-ttu-id="f8722-154">クライアント プログラム ファイルを、言語固有のフォルダにある \client\bin\ フォルダーからクライアント コンピュータにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f8722-154">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client machines.</span></span>  
  
    2.  <span data-ttu-id="f8722-155">各クライアントの構成ファイルで、エンドポイント定義のアドレス値をサービスの新しいアドレスに合わせて変更します。</span><span class="sxs-lookup"><span data-stu-id="f8722-155">In each client configuration file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="f8722-156">アドレスの "localhost" への参照をすべて完全修飾ドメイン名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f8722-156">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
3.  <span data-ttu-id="f8722-157">データ ソース コンピュータを設定します。</span><span class="sxs-lookup"><span data-stu-id="f8722-157">Set up the data source machine:</span></span>  
  
    1.  <span data-ttu-id="f8722-158">データ ソース プログラム ファイルを、言語固有のフォルダーにある \datasource\bin\ フォルダーからデータ ソース コンピュータにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f8722-158">Copy the data source program files from the \datasource\bin\ folder, under the language-specific folder, to the data source machine.</span></span>  
  
    2.  <span data-ttu-id="f8722-159">データ ソースの構成ファイルで、エンドポイント定義のアドレス値をサービスの新しいアドレスに合わせて変更します。</span><span class="sxs-lookup"><span data-stu-id="f8722-159">In the data source configuration file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="f8722-160">アドレスの "localhost" への参照をすべて完全修飾ドメイン名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f8722-160">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
4.  <span data-ttu-id="f8722-161">クライアント コンピュータで、コマンド プロンプトから Client.exe を起動します。</span><span class="sxs-lookup"><span data-stu-id="f8722-161">On the client machines, launch Client.exe from a command prompt.</span></span>  
  
5.  <span data-ttu-id="f8722-162">データ ソース コンピューターで、コマンド プロンプトから Datasource.exe を起動します。</span><span class="sxs-lookup"><span data-stu-id="f8722-162">On the data source machine, launch Datasource.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f8722-163">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f8722-163">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f8722-164">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f8722-164">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f8722-165">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="f8722-165">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f8722-166">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="f8722-166">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DesignPatterns/ListBasedPublishSubscribe`  
  

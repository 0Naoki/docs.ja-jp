---
title: XAMLX における永続的な遅延
ms.date: 03/30/2017
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
ms.openlocfilehash: 1eef9211c67d190ecb5f329c481fa2e3d1763353
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "45521454"
---
# <a name="durable-delay-in-xamlx"></a><span data-ttu-id="82e95-102">XAMLX における永続的な遅延</span><span class="sxs-lookup"><span data-stu-id="82e95-102">Durable Delay in XAMLX</span></span>
<span data-ttu-id="82e95-103">このサンプルでは、永続的な遅延を使用する方法を示します。これは、遅延の間、ワークフローを永続的なデバイスに永続化する遅延のことです。</span><span class="sxs-lookup"><span data-stu-id="82e95-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="82e95-104">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="82e95-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="82e95-105">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="82e95-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="82e95-106">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="82e95-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="82e95-107">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="82e95-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a><span data-ttu-id="82e95-108">説明</span><span class="sxs-lookup"><span data-stu-id="82e95-108">Discussion</span></span>  
 <span data-ttu-id="82e95-109">このサンプル ワークフローには、遅延によって分割された 2 つのローカル ファイルへのメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="82e95-109">The sample workflow contains two messages to a local file that are separated by a delay.</span></span> <span data-ttu-id="82e95-110">遅延が発生すると、ワークフローがアンロードされ、ワークフローはメモリに再読み込みされるまでワークフロー インスタンス ストアで 5 秒間待機します。</span><span class="sxs-lookup"><span data-stu-id="82e95-110">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
 <span data-ttu-id="82e95-111">.Xamlx ファイルは、Visual Studio でホストされるワークフロー サービスです。</span><span class="sxs-lookup"><span data-stu-id="82e95-111">The .xamlx file is a workflow service that is hosted in Visual Studio.</span></span> <span data-ttu-id="82e95-112">Visual Studio では、ワークフロー ホストにワークフロー サービスを使用する Cassini を使用します。</span><span class="sxs-lookup"><span data-stu-id="82e95-112">Visual Studio uses Cassini that uses a workflow service host to host the workflow.</span></span>  
  
 <span data-ttu-id="82e95-113">ワークフロー サービス ホストは、ワークフローをホストするだけでなく、読み込みとアンロードを行うことによってワークフロー インスタンスを管理します。</span><span class="sxs-lookup"><span data-stu-id="82e95-113">In addition to hosting the workflow, the workflow service host manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="82e95-114">Windows Workflow Foundation (WF) の定義 (ワークフロー サービス ホスト) 上のインスタンスを開始する設定へのメッセージを送信するクライアントを<xref:System.ServiceModel.Activities.Receive>ワークフロー内のアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="82e95-114">To start an instance of the Windows Workflow Foundation (WF) definition (on the workflow service host), set a client that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="82e95-115">この <xref:System.ServiceModel.Activities.Receive> は、<xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> プロパティが `true` に設定されているため、メッセージを受信した後にワークフローの新しいインスタンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="82e95-115">This <xref:System.ServiceModel.Activities.Receive> has its <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="82e95-116">初期化中に、ワークフロー サービス ホストに対してインスタンスを永続化ストア (データベース) にアンロードするように指定する、インスタンスのアンロード動作が構成ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="82e95-116">During initialization, an unload instance behavior is added to the configuration file that specifies to the workflow service host under which it should unload an instance to the persistence store (database).</span></span> <span data-ttu-id="82e95-117">このサンプルでは、(遅延が発生して) ワークフローがアイドル状態になった直後にインスタンスがアンロードされます。</span><span class="sxs-lookup"><span data-stu-id="82e95-117">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="82e95-118">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="82e95-118">To use this sample</span></span>  
  
1.  <span data-ttu-id="82e95-119">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] のコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="82e95-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="82e95-120">DurableDelayXamlx\CS フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="82e95-120">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="82e95-121">Setup.cmd を実行します。</span><span class="sxs-lookup"><span data-stu-id="82e95-121">Run Setup.cmd.</span></span>  
  
4.  <span data-ttu-id="82e95-122">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="82e95-122">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an administrator.</span></span>  
  
5.  <span data-ttu-id="82e95-123">DurableDelayXamlx.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="82e95-123">Open the DurableDelayXamlx.sln solution file.</span></span>  
  
6.  <span data-ttu-id="82e95-124">**ソリューション エクスプ ローラー**ソリューションを右クリックし、選択、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="82e95-124">In **Solution Explorer**, right-click the solution and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="82e95-125">選択**マルチ スタートアップ プロジェクト**に両方のプロジェクトを設定および**開始**します。</span><span class="sxs-lookup"><span data-stu-id="82e95-125">Select **Multiple startup projects** and set both projects to **Start**.</span></span>  
  
8.  <span data-ttu-id="82e95-126">ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="82e95-126">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
9. <span data-ttu-id="82e95-127">ソリューションを実行するには、Ctrl キーを押しながら F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="82e95-127">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="82e95-128">このサンプルをアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="82e95-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="82e95-129">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] のコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="82e95-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="82e95-130">DurableDelayXamlx\CS フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="82e95-130">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="82e95-131">Cleanup.cmd を実行します。</span><span class="sxs-lookup"><span data-stu-id="82e95-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="82e95-132">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="82e95-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="82e95-133">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="82e95-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="82e95-134">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="82e95-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="82e95-135">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="82e95-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`

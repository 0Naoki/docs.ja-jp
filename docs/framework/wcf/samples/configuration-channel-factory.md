---
title: 構成チャネル ファクトリ
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 5bee4c7cc2c2e64c6e0d8d0ec2634f9500cd9d51
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328076"
---
# <a name="configuration-channel-factory"></a><span data-ttu-id="32a33-102">構成チャネル ファクトリ</span><span class="sxs-lookup"><span data-stu-id="32a33-102">Configuration Channel Factory</span></span>
<span data-ttu-id="32a33-103">このサンプルでは、<xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="32a33-103">This sample covers the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span> <span data-ttu-id="32a33-104"><xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> WCF クライアントの構成サーバーの全体を管理できます。</span><span class="sxs-lookup"><span data-stu-id="32a33-104">The <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows central management of WCF client configuration.</span></span> <span data-ttu-id="32a33-105">これは、アプリケーション ドメインによる読み込みの後に構成が選択または変更される場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="32a33-105">This can also be useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="32a33-106">使用例</span><span class="sxs-lookup"><span data-stu-id="32a33-106">Demonstrates</span></span>
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a><span data-ttu-id="32a33-107">説明</span><span class="sxs-lookup"><span data-stu-id="32a33-107">Discussion</span></span>
 <span data-ttu-id="32a33-108">このサンプルでは、既定のアプリケーション構成ファイルを使用することなく、<xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> を使用して、クライアント アプリケーションに特定の構成ファイルを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="32a33-108">This sample shows how to use <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> to add a particular configuration file to a client application, without having to use the default application configuration file.</span></span>

 <span data-ttu-id="32a33-109">このサンプルは、2 つのプロジェクトで構成されます。</span><span class="sxs-lookup"><span data-stu-id="32a33-109">The sample consists of two projects.</span></span> <span data-ttu-id="32a33-110">最初のプロジェクトは、クライアントから送信されるメッセージに応答するために実行される単純なサービスです。</span><span class="sxs-lookup"><span data-stu-id="32a33-110">The first project is a simple service that runs to reply to messages coming from the clients.</span></span> <span data-ttu-id="32a33-111">2 番目のプロジェクトは、Test.config 構成ファイルの <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> を使用して、2 つの <xref:System.Configuration.ExeConfigurationFileMap> オブジェクトを作成し、サービスとの通信にそれらのオブジェクトを使用するクライアント アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="32a33-111">The second project is a client application that builds two <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> objects using a <xref:System.Configuration.ExeConfigurationFileMap> for the Test.config configuration file and uses them to communicate with the service.</span></span> <span data-ttu-id="32a33-112">どちらのクライアントも Test.config で指定された構成を使用してサービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="32a33-112">Both clients communicate with the service using the configuration specified in Test.config.</span></span>

 <span data-ttu-id="32a33-113">次のコードでは、カスタム構成ファイルをクライアント アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="32a33-113">The following code adds a custom configuration file to a client application.</span></span>

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="32a33-114">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="32a33-114">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="32a33-115">管理者特権で Visual Studio 2012 を開きます。</span><span class="sxs-lookup"><span data-stu-id="32a33-115">Open Visual Studio 2012 with administrator privileges.</span></span>

2. <span data-ttu-id="32a33-116">ConfigurationChannelFactory ソリューション (2 プロジェクト) を右クリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="32a33-116">Right-click the ConfigurationChannelFactory solution (2 projects) and then select **Properties**.</span></span>

3. <span data-ttu-id="32a33-117">**共通プロパティ**を選択します**スタートアップ プロジェクト**、 をクリックし、**マルチ スタートアップ プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="32a33-117">In **Common Properties**, select **Startup Project**, and then click **Multiple startup projects**.</span></span>

4. <span data-ttu-id="32a33-118">移動、**サービス**でプロジェクトは、リストの先頭を**アクション 'Start'**、し、移動、**クライアント**プロジェクトの後に、**サービス**プロジェクトでも、**アクション 'Start'** であり、**クライアント**プロジェクトを実行した後、**サービス**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="32a33-118">Move the **Service** project to the beginning of the list, with the **Action ‘Start’**, and then move the **Client** project after the **Service** project, also with the **Action ‘Start’**, so the **Client** project is executed after the **Service** project.</span></span>

5. <span data-ttu-id="32a33-119">をクリックして**OK**、し、f5 キーを押して (または ctrl キーを押しながら f5 キー)、サンプルを実行するキーを押します。</span><span class="sxs-lookup"><span data-stu-id="32a33-119">Click **OK**, and then press F5 (or CTRL+F5) to run the sample.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="32a33-120">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="32a33-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="32a33-121">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="32a33-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="32a33-122">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="32a33-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="32a33-123">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="32a33-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`

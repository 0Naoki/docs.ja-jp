---
title: サービス デバッグ動作
ms.date: 03/30/2017
ms.assetid: 9d8fd3fb-dc39-427a-8235-336a7e7162ba
ms.openlocfilehash: b87911426b6d4edf8a6f9b0172f4872fac7b9b6f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858887"
---
# <a name="service-debug-behavior"></a><span data-ttu-id="dd354-102">サービス デバッグ動作</span><span class="sxs-lookup"><span data-stu-id="dd354-102">Service Debug Behavior</span></span>
<span data-ttu-id="dd354-103">このサンプルでは、サービス デバッグ動作の設定を構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dd354-103">This sample demonstrates how service debug behavior settings can be configured.</span></span> <span data-ttu-id="dd354-104">サンプルがに基づいて、 [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)、実装、`ICalculator`サービス コントラクト。</span><span class="sxs-lookup"><span data-stu-id="dd354-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="dd354-105">このサンプルは、サービス デバッグ動作を構成ファイルで明示的に定義します。</span><span class="sxs-lookup"><span data-stu-id="dd354-105">This sample explicitly defines service debug behavior in the configuration file.</span></span> <span data-ttu-id="dd354-106">コードで強制的に定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd354-106">It can also be done imperatively in code.</span></span>  
  
 <span data-ttu-id="dd354-107">この例では、クライアントはコンソール アプリケーション (.exe) であり、サービスはインターネット インフォメーション サービス (IIS) によってホストされます。</span><span class="sxs-lookup"><span data-stu-id="dd354-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd354-108">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd354-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="dd354-109">サーバーの Web.config ファイルでは、次のサンプルに示すように、ヘルプ ページと例外処理を有効にするサービス デバッグ動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="dd354-109">The Web.config file for the server defines the service debug behavior to enable the help page and exception handling as shown in the following sample.</span></span>  
  
```xml  
<behaviors>  
     <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
         <!-- WARNING: Setting includeExceptionDetailInFaults = "True" could result in leaking secured server information to the client.-->  
         <!-- Please set this to false when deploying -->  
             <serviceDebug includeExceptionDetailInFaults="True" httpHelpPageEnabled="True"/>  
         </behavior>  
     </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="dd354-110">[\<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)サービス デバッグ動作プロパティの変更を許可する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="dd354-110">[\<serviceDebug>](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) is the configuration element that allows changing the service debug behavior properties.</span></span> <span data-ttu-id="dd354-111">ユーザーはこの動作を変更して、次を実現することができます。</span><span class="sxs-lookup"><span data-stu-id="dd354-111">The user can modify this behavior to achieve the following:</span></span>  
  
-   <span data-ttu-id="dd354-112">例外が <xref:System.ServiceModel.FaultContractAttribute> を使用して宣言されていない場合でも、サービスでは、アプリケーション コードによってスローされる例外を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="dd354-112">This allows the service to return any exception that is thrown by the application code even if the exception is not declared using the <xref:System.ServiceModel.FaultContractAttribute>.</span></span> <span data-ttu-id="dd354-113">これを行うには、`includeExceptionDetailInFaults` を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="dd354-113">It is done by setting `includeExceptionDetailInFaults` to `true`.</span></span> <span data-ttu-id="dd354-114">この設定は、サーバーが予期しない例外をスローしている場合のデバッグ時に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dd354-114">This setting is useful when debugging cases where the server is throwing an unexpected exception.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="dd354-115">この設定を本運用環境で有効にすると、セキュリティが不十分になります。</span><span class="sxs-lookup"><span data-stu-id="dd354-115">It is not secure to turn this setting on in a production environment.</span></span> <span data-ttu-id="dd354-116">サーバーの予期しない例外には、クライアントを対象としていない情報が含まれる場合があるため、`includeExceptionDetailsInFaults` を `true` に設定すると、情報の漏えいが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dd354-116">An unexpected server exception may have some information that is not intended for the client and so setting `includeExceptionDetailsInFaults` to `true` might result in an information leak.</span></span>  
  
-   <span data-ttu-id="dd354-117">[ \<ServiceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)ユーザーを有効にするか、ヘルプ ページを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dd354-117">The [\<serviceDebug>](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) also allows a user to enable or disable the help page.</span></span> <span data-ttu-id="dd354-118">各サービスは、サービスの WSDL を取得するエンドポイントなど、サービスに関する情報が含まれるヘルプ ページをオプションで公開できます。</span><span class="sxs-lookup"><span data-stu-id="dd354-118">Each service can optionally expose a help page that contains information about the service including the endpoint to get WSDL for the service.</span></span> <span data-ttu-id="dd354-119">これを有効にするには、`httpHelpPageEnabled` プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="dd354-119">This can be enabled by setting `httpHelpPageEnabled` to `true`.</span></span> <span data-ttu-id="dd354-120">これにより、サービスのベース アドレスへの GET 要求に対して、ヘルプ ページを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="dd354-120">This enables the help page to be returned to a GET request to the base address of the service.</span></span> <span data-ttu-id="dd354-121">このアドレスは、別の属性 `httpHelpPageUrl` を設定して変更できます。</span><span class="sxs-lookup"><span data-stu-id="dd354-121">You can change this address by setting another attribute `httpHelpPageUrl`.</span></span> <span data-ttu-id="dd354-122">HTTP の代わりに HTTPS を使用すると、このアドレスをセキュリティ保護できます。</span><span class="sxs-lookup"><span data-stu-id="dd354-122">You can make this secure by using HTTPS instead of HTTP.</span></span> <span data-ttu-id="dd354-123">これを行うには、`httpsHelpPageEnabled` と `httpsHelpPageUrl` を設定します。</span><span class="sxs-lookup"><span data-stu-id="dd354-123">This can be done by setting `httpsHelpPageEnabled` and `httpsHelpPageUrl`.</span></span>  
  
 <span data-ttu-id="dd354-124">このサンプルを実行すると、操作要求および応答がクライアントのコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd354-124">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="dd354-125">最初の 3 つの操作 (加算、減算、乗算) が正常に行われる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd354-125">The first three operations (Add, Subtract and Multiply) must succeed.</span></span> <span data-ttu-id="dd354-126">最後の操作 (除算) は、0 による除算の例外によってエラーとなります。</span><span class="sxs-lookup"><span data-stu-id="dd354-126">The last operation ("divide") fails with a division by zero exception.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dd354-127">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="dd354-127">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="dd354-128">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="dd354-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="dd354-129">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="dd354-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="dd354-130">1 つまたは複数コンピュータ構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="dd354-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dd354-131">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd354-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dd354-132">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dd354-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dd354-133">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="dd354-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dd354-134">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="dd354-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\ServiceDebug`  
  
## <a name="see-also"></a><span data-ttu-id="dd354-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd354-135">See Also</span></span>

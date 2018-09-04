---
title: WS 信頼できるセッション
ms.date: 03/30/2017
helpviewer_keywords:
- Reliable session
ms.assetid: 86e914f2-060b-432b-bd17-333695317745
ms.openlocfilehash: ec9163eded7f77053b94b7cb0ff0995dca575612
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526416"
---
# <a name="ws-reliable-session"></a><span data-ttu-id="0981c-102">WS 信頼できるセッション</span><span class="sxs-lookup"><span data-stu-id="0981c-102">WS Reliable Session</span></span>
<span data-ttu-id="0981c-103">このサンプルでは、信頼できるセッションの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0981c-103">This sample demonstrates the use of reliable sessions.</span></span> <span data-ttu-id="0981c-104">信頼できるセッションは、信頼できるメッセージとセッションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0981c-104">Reliable sessions provide support for reliable messaging and sessions.</span></span> <span data-ttu-id="0981c-105">信頼できるメッセージは、エラー時に通信を再試行するほか、メッセージの順次到着などの配信の保証を指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0981c-105">Reliable messaging retries communication on failure and allows delivery assurances to be specified, such as in-order arrival of messages.</span></span> <span data-ttu-id="0981c-106">セッションでは、呼び出し間でクライアントの状態が保持されます。</span><span class="sxs-lookup"><span data-stu-id="0981c-106">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="0981c-107">サンプルでは、クライアントの状態を保持するセッションを実装し、配信順序を保証することを指定します。</span><span class="sxs-lookup"><span data-stu-id="0981c-107">The sample implements sessions for maintaining client state and specifies in-order delivery assurances.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0981c-108">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="0981c-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0981c-109">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0981c-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0981c-110">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="0981c-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0981c-111">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="0981c-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsReliableSession`  
  
 <span data-ttu-id="0981c-112">このサンプルがに基づいて、 [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)電卓サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="0981c-112">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="0981c-113">信頼できるセッション機能は、クライアントとサービスのアプリケーション構成ファイルで有効化され、構成されています。</span><span class="sxs-lookup"><span data-stu-id="0981c-113">The reliable session features are enabled and configured in the application configuration files for the client and service.</span></span>  
  
 <span data-ttu-id="0981c-114">このサンプルでは、サービスはインターネット インフォメーション サービス (IIS) によってホストされており、クライアントはコンソール アプリケーション (.exe) です。</span><span class="sxs-lookup"><span data-stu-id="0981c-114">In this sample, the service is hosted in Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0981c-115">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0981c-115">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="0981c-116">このサンプルでは、`wsHttpBinding` を使用しています。</span><span class="sxs-lookup"><span data-stu-id="0981c-116">The sample uses the `wsHttpBinding`.</span></span> <span data-ttu-id="0981c-117">バインディングは、クライアントとサービスの両方の構成ファイルに指定されます。</span><span class="sxs-lookup"><span data-stu-id="0981c-117">The binding is specified in the configuration files for both the client and service.</span></span> <span data-ttu-id="0981c-118">バインディングの種類はエンドポイント要素の `binding` 属性に指定します。次のサンプル構成を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0981c-118">The binding type is specified in the endpoint element’s `binding` attribute as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address=""  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"   
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="0981c-119">エンドポイントには、"Binding1" という名前のバインディング構成を参照する `bindingConfiguration` 属性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0981c-119">The endpoint contains a `bindingConfiguration` attribute that references a binding configuration named "Binding1."</span></span> <span data-ttu-id="0981c-120">バインドの構成では、信頼できるセッションをにより設定によって、`enabled`の属性、 [ \<reliableSession >](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md)に`true`します。</span><span class="sxs-lookup"><span data-stu-id="0981c-120">The binding configuration enables reliable sessions by setting the `enabled` attribute of the [\<reliableSession>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) to `true`.</span></span> <span data-ttu-id="0981c-121">順序付きセッションの配信の保証は、ordered 属性を `true` または `false` に設定することによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="0981c-121">Delivery assurances for ordered sessions are controlled by setting the ordered attribute to `true` or `false`.</span></span> <span data-ttu-id="0981c-122">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="0981c-122">The default is `true`.</span></span>  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding name="Binding1">  
            <reliableSession enabled="true" />  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="0981c-123">サービス実装クラスは、クライアントごとに個別のクラスのインスタンスをインスタンス化して保持する <xref:System.ServiceModel.InstanceContextMode.PerSession> を実装します。次のサンプル コードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0981c-123">The service implementation class implements <xref:System.ServiceModel.InstanceContextMode.PerSession> instancing to maintain a separate class instance for each client, as shown in the following sample code.</span></span>  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)] public class CalculatorService : ICalculator  
{  
    ...  
}  
```
  
 <span data-ttu-id="0981c-124">このサンプルを実行すると、操作要求および応答がクライアントのコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0981c-124">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="0981c-125">クライアントをシャットダウンするには、クライアント ウィンドウで Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0981c-125">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0981c-126">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="0981c-126">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0981c-127">次のコマンドを使用して、[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0981c-127">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="0981c-128">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="0981c-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="0981c-129">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0981c-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="0981c-130">1 つまたは複数コンピュータ構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="0981c-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0981c-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="0981c-131">See Also</span></span>

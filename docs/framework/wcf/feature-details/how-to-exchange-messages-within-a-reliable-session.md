---
title: '方法 : 信頼されたセッション内のメッセージを変換する'
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 53e5661bf140540cd0fc7a9fcb739b67488b8491
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374522"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a><span data-ttu-id="fe01c-102">方法 : 信頼されたセッション内のメッセージを変換する</span><span class="sxs-lookup"><span data-stu-id="fe01c-102">How to: Exchange Messages Within a Reliable Session</span></span>

<span data-ttu-id="fe01c-103">このトピックでは、信頼できるセッションを有効にするために必要な手順について説明します。ここでは、信頼できるセッションを (既定ではなく) オプションでサポートするシステム指定のバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-103">This topic outlines the steps required to enable a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="fe01c-104">命令型コードを使用して、信頼できるセッションを有効にするか、構成ファイルで宣言します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-104">You enable a reliable session imperatively using code or declaratively in your configuration file.</span></span> <span data-ttu-id="fe01c-105">この手順は、信頼できるセッションを有効にして、メッセージが送信された順序で到着したかを規定するために、クライアントとサービス構成ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-105">This procedure uses the client and service configuration files to enable the reliable session and to stipulate that the messages arrive in the same order in which they were sent.</span></span>

<span data-ttu-id="fe01c-106">この手順の重要な部分は、エンドポイント構成要素を含む、`bindingConfiguration`という名前のバインド構成を参照する属性`Binding1`します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-106">The key part of this procedure is that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="fe01c-107">[ **\<バインド >** ](../../../../docs/framework/misc/binding.md)構成要素を設定して、信頼できるセッションを有効にするには、この名前の参照、`enabled`の属性、 [ **\<reliableSession >** ](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)要素`true`します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-107">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) element to `true`.</span></span> <span data-ttu-id="fe01c-108">信頼できるセッションで順序付き配信の保証を指定するには、`ordered` 属性を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-108">You specify the ordered delivery assurances for the reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="fe01c-109">この例のソースのコピーを次を参照してください。 [WS 信頼できるセッション](../../../../docs/framework/wcf/samples/ws-reliable-session.md)します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-109">For the source copy of this example, see [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="fe01c-110">信頼できるセッションを使用する WSHttpBinding 使用サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-110">Configure the service with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="fe01c-111">サービスの種類にサービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. <span data-ttu-id="fe01c-112">サービス クラスにサービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="fe01c-113">サービスの実装の内部アドレスやバインディングの情報が指定されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fe01c-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="fe01c-114">構成ファイルからのアドレスやバインディングの情報を取得するコードを記述するために必要ないです。</span><span class="sxs-lookup"><span data-stu-id="fe01c-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. <span data-ttu-id="fe01c-115">作成、 *Web.config*のエンドポイントを構成するファイル、`CalculatorService`を使用して、<xref:System.ServiceModel.WSHttpBinding>信頼できるセッションが有効になっており、必要なメッセージの配信の順序で。</span><span class="sxs-lookup"><span data-stu-id="fe01c-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding> with reliable session enabled and ordered delivery of messages required.</span></span>

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. <span data-ttu-id="fe01c-116">作成、 *Service.svc*行を含むファイル。</span><span class="sxs-lookup"><span data-stu-id="fe01c-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1.  <span data-ttu-id="fe01c-117">場所、 *Service.svc*インターネット インフォメーション サービス (IIS) 仮想ディレクトリのファイル。</span><span class="sxs-lookup"><span data-stu-id="fe01c-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="fe01c-118">信頼できるセッションを使用して、WSHttpBinding でクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-118">Configure the client with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="fe01c-119">使用して、 [ServiceModel メタデータ ユーティリティ ツール (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)サービス メタデータからコードを生成するためのコマンドラインから。</span><span class="sxs-lookup"><span data-stu-id="fe01c-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata:</span></span>

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="fe01c-120">生成されたクライアントが含まれています、`ICalculator`クライアント実装が満たす必要があるサービス コントラクトを定義するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="fe01c-120">The generated client contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. <span data-ttu-id="fe01c-121">生成されたクライアント アプリケーションは `ClientCalculator` も実装します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="fe01c-122">サービスの実装内部アドレスとバインディング情報をどこでも指定されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fe01c-122">Note that the address and binding information isn't specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="fe01c-123">構成ファイルからのアドレスやバインディングの情報を取得するコードを記述するために必要ないです。</span><span class="sxs-lookup"><span data-stu-id="fe01c-123">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. <span data-ttu-id="fe01c-124">*Svcutil.exe*も使用するクライアントの構成を生成、<xref:System.ServiceModel.WSHttpBinding>クラス。</span><span class="sxs-lookup"><span data-stu-id="fe01c-124">*Svcutil.exe* also generates the configuration for the client that uses the <xref:System.ServiceModel.WSHttpBinding> class.</span></span> <span data-ttu-id="fe01c-125">構成ファイルの名前を付けます*App.config* Visual Studio を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="fe01c-125">Name the configuration file *App.config* when using Visual Studio.</span></span>

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. <span data-ttu-id="fe01c-126">インスタンスを作成、`ClientCalculator`アプリケーションでサービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-126">Create an instance of the `ClientCalculator` in an application and call the service operations.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. <span data-ttu-id="fe01c-127">クライアントをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-127">Compile and run the client.</span></span>

## <a name="example"></a><span data-ttu-id="fe01c-128">例</span><span class="sxs-lookup"><span data-stu-id="fe01c-128">Example</span></span>

<span data-ttu-id="fe01c-129">システム指定のバインディングの中には、信頼できるセッションを既定でサポートするものがあります。</span><span class="sxs-lookup"><span data-stu-id="fe01c-129">Several of the system-provided bindings support reliable sessions by default.</span></span> <span data-ttu-id="fe01c-130">次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="fe01c-130">These include:</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

<span data-ttu-id="fe01c-131">信頼できるセッションをサポートするカスタム バインドを作成する方法の例は、次を参照してください。[方法: HTTPS でカスタムの信頼できるセッション バインドを作成する](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)します。</span><span class="sxs-lookup"><span data-stu-id="fe01c-131">For an example of how to create a custom binding that supports reliable sessions, see [How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fe01c-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe01c-132">See also</span></span>

[<span data-ttu-id="fe01c-133">信頼できるセッション</span><span class="sxs-lookup"><span data-stu-id="fe01c-133">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)

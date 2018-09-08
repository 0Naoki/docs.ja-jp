---
title: セキュリティで保護されていないイントラネットのクライアントとサービス
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e44b7af6581e6c5abdcb2f82b02d152dd22d0b3b
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44131352"
---
# <a name="intranet-unsecured-client-and-service"></a><span data-ttu-id="7852e-102">セキュリティで保護されていないイントラネットのクライアントとサービス</span><span class="sxs-lookup"><span data-stu-id="7852e-102">Intranet Unsecured Client and Service</span></span>
<span data-ttu-id="7852e-103">次の図は、WCF アプリケーションをセキュリティで保護されたプライベート ネットワークに関する情報を提供するために開発の単純な Windows Communication Foundation (WCF) サービスを示しています。</span><span class="sxs-lookup"><span data-stu-id="7852e-103">The following illustration depicts a simple Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span> <span data-ttu-id="7852e-104">重要度の低いデータは、ネットワークの本質的にセキュリティで保護されたことが必要ですか、WCF インフラストラクチャの下のレイヤーによってセキュリティが提供されるため、セキュリティは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7852e-104">Security is not required because the data is of low importance, the network is expected to be inherently secure, or security is provided by a layer below the WCF infrastructure.</span></span>  
  
 <span data-ttu-id="7852e-105">![イントラネットのセキュリティ保護されていないクライアントとサービスのシナリオ](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span><span class="sxs-lookup"><span data-stu-id="7852e-105">![Intranet unsecured client and service scenario](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span></span>  
  
|<span data-ttu-id="7852e-106">特徴</span><span class="sxs-lookup"><span data-stu-id="7852e-106">Characteristic</span></span>|<span data-ttu-id="7852e-107">説明</span><span class="sxs-lookup"><span data-stu-id="7852e-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7852e-108">セキュリティ モード</span><span class="sxs-lookup"><span data-stu-id="7852e-108">Security Mode</span></span>|<span data-ttu-id="7852e-109">なし</span><span class="sxs-lookup"><span data-stu-id="7852e-109">None</span></span>|  
|<span data-ttu-id="7852e-110">Transport</span><span class="sxs-lookup"><span data-stu-id="7852e-110">Transport</span></span>|<span data-ttu-id="7852e-111">TCP</span><span class="sxs-lookup"><span data-stu-id="7852e-111">TCP</span></span>|  
|<span data-ttu-id="7852e-112">バインディング</span><span class="sxs-lookup"><span data-stu-id="7852e-112">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
|<span data-ttu-id="7852e-113">相互運用性</span><span class="sxs-lookup"><span data-stu-id="7852e-113">Interoperability</span></span>|<span data-ttu-id="7852e-114">WCF のみ</span><span class="sxs-lookup"><span data-stu-id="7852e-114">WCF only</span></span>|  
|<span data-ttu-id="7852e-115">認証</span><span class="sxs-lookup"><span data-stu-id="7852e-115">Authentication</span></span>|<span data-ttu-id="7852e-116">なし</span><span class="sxs-lookup"><span data-stu-id="7852e-116">None</span></span>|  
|<span data-ttu-id="7852e-117">整合性</span><span class="sxs-lookup"><span data-stu-id="7852e-117">Integrity</span></span>|<span data-ttu-id="7852e-118">なし</span><span class="sxs-lookup"><span data-stu-id="7852e-118">None</span></span>|  
|<span data-ttu-id="7852e-119">機密性</span><span class="sxs-lookup"><span data-stu-id="7852e-119">Confidentiality</span></span>|<span data-ttu-id="7852e-120">なし</span><span class="sxs-lookup"><span data-stu-id="7852e-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="7852e-121">サービス</span><span class="sxs-lookup"><span data-stu-id="7852e-121">Service</span></span>  
 <span data-ttu-id="7852e-122">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="7852e-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="7852e-123">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7852e-123">Do one of the following:</span></span>  
  
-   <span data-ttu-id="7852e-124">構成を使用せずに、コードを使用してスタンドアロン サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="7852e-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="7852e-125">提供された構成を使用してサービスを作成しますが、エンドポイントを定義しません。</span><span class="sxs-lookup"><span data-stu-id="7852e-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7852e-126">コード</span><span class="sxs-lookup"><span data-stu-id="7852e-126">Code</span></span>  
 <span data-ttu-id="7852e-127">次のコードは、セキュリティで保護されないエンドポイントを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7852e-127">The following code shows how to create an endpoint with no security:</span></span>  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="7852e-128">構成</span><span class="sxs-lookup"><span data-stu-id="7852e-128">Configuration</span></span>  
 <span data-ttu-id="7852e-129">次のコードは、次に示す構成を使用して同一のエンドポイントをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="7852e-129">The following code sets up the same endpoint using configuration:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration=""   
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"   
                  binding="netTcpBinding"  
                  bindingConfiguration="tcp_Unsecured"   
                  name="netTcp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="tcp_Unsecured">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="7852e-130">Client</span><span class="sxs-lookup"><span data-stu-id="7852e-130">Client</span></span>  
 <span data-ttu-id="7852e-131">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="7852e-131">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="7852e-132">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7852e-132">Do one of the following:</span></span>  
  
-   <span data-ttu-id="7852e-133">コード (およびクライアント コード) を使用してスタンドアロン クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="7852e-133">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="7852e-134">エンドポイント アドレスを定義しないクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="7852e-134">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="7852e-135">代わりに、引数として構成名を受け取るクライアント コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7852e-135">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="7852e-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7852e-136">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="7852e-137">コード</span><span class="sxs-lookup"><span data-stu-id="7852e-137">Code</span></span>  
 <span data-ttu-id="7852e-138">次のコードでは、TCP プロトコルを使用してセキュリティ保護されていないエンドポイントにアクセスする基本的な WCF クライアントを示します。</span><span class="sxs-lookup"><span data-stu-id="7852e-138">The following code shows a basic WCF client that accesses an unsecured endpoint using the TCP protocol.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="7852e-139">構成</span><span class="sxs-lookup"><span data-stu-id="7852e-139">Configuration</span></span>  
 <span data-ttu-id="7852e-140">次の構成コードは、クライアントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7852e-140">The following configuration code applies to the client:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator "  
                binding="netTcpBinding"   
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"   
                name="NetTcpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7852e-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="7852e-141">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpBinding>  
 [<span data-ttu-id="7852e-142">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="7852e-142">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="7852e-143">Windows Server App Fabric のセキュリティ モデル</span><span class="sxs-lookup"><span data-stu-id="7852e-143">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)

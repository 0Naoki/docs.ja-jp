---
title: メッセージ セキュリティと匿名クライアント
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cad53e1a-b7c9-4064-bc87-508c3d1dce49
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: d3e8269fc05caf70f4329ce8f13a3633a8982c0b
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2018
ms.locfileid: "44365096"
---
# <a name="message-security-with-an-anonymous-client"></a><span data-ttu-id="d5196-102">メッセージ セキュリティと匿名クライアント</span><span class="sxs-lookup"><span data-stu-id="d5196-102">Message Security with an Anonymous Client</span></span>
<span data-ttu-id="d5196-103">次のシナリオでは、クライアントと Windows Communication Foundation (WCF) メッセージ セキュリティで保護されたサービスを説明します。</span><span class="sxs-lookup"><span data-stu-id="d5196-103">The following scenario shows a client and service secured by Windows Communication Foundation (WCF) message security.</span></span> <span data-ttu-id="d5196-104">設計目標は、トランスポート セキュリティではなくメッセージ セキュリティを使用することです。これによって将来、多様なクレームに基づくモデルをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="d5196-104">A design goal is to use message security rather than transport security, so that in the future it can support a richer claims-based model.</span></span> <span data-ttu-id="d5196-105">承認に多様なクレームの使用に関する詳細については、次を参照してください。[管理クレームと Id モデルでの承認](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="d5196-105">For more information about using rich claims for authorization, see [Managing Claims and Authorization with the Identity Model](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>  
  
 <span data-ttu-id="d5196-106">サンプル アプリケーションでは、次を参照してください。[メッセージ セキュリティ匿名](../../../../docs/framework/wcf/samples/message-security-anonymous.md)します。</span><span class="sxs-lookup"><span data-stu-id="d5196-106">For a sample application, see [Message Security Anonymous](../../../../docs/framework/wcf/samples/message-security-anonymous.md).</span></span>  
  
 <span data-ttu-id="d5196-107">![メッセージ セキュリティと匿名クライアント](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span><span class="sxs-lookup"><span data-stu-id="d5196-107">![Message security with an anynymous client](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span></span>  
  
|<span data-ttu-id="d5196-108">特徴</span><span class="sxs-lookup"><span data-stu-id="d5196-108">Characteristic</span></span>|<span data-ttu-id="d5196-109">説明</span><span class="sxs-lookup"><span data-stu-id="d5196-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d5196-110">セキュリティ モード</span><span class="sxs-lookup"><span data-stu-id="d5196-110">Security Mode</span></span>|<span data-ttu-id="d5196-111">メッセージ</span><span class="sxs-lookup"><span data-stu-id="d5196-111">Message</span></span>|  
|<span data-ttu-id="d5196-112">相互運用性</span><span class="sxs-lookup"><span data-stu-id="d5196-112">Interoperability</span></span>|<span data-ttu-id="d5196-113">WCF のみ</span><span class="sxs-lookup"><span data-stu-id="d5196-113">WCF only</span></span>|  
|<span data-ttu-id="d5196-114">認証 (サーバー)</span><span class="sxs-lookup"><span data-stu-id="d5196-114">Authentication (Server)</span></span>|<span data-ttu-id="d5196-115">初期ネゴシエーションには、サーバー認証が必要ですが、クライアント認証は不要です</span><span class="sxs-lookup"><span data-stu-id="d5196-115">Initial negotiation requires server authentication, but not client authentication</span></span>|  
|<span data-ttu-id="d5196-116">認証 (クライアント)</span><span class="sxs-lookup"><span data-stu-id="d5196-116">Authentication (Client)</span></span>|<span data-ttu-id="d5196-117">なし</span><span class="sxs-lookup"><span data-stu-id="d5196-117">None</span></span>|  
|<span data-ttu-id="d5196-118">整合性</span><span class="sxs-lookup"><span data-stu-id="d5196-118">Integrity</span></span>|<span data-ttu-id="d5196-119">はい、共有のセキュリティ コンテキストを使用します</span><span class="sxs-lookup"><span data-stu-id="d5196-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="d5196-120">機密性</span><span class="sxs-lookup"><span data-stu-id="d5196-120">Confidentiality</span></span>|<span data-ttu-id="d5196-121">はい、共有のセキュリティ コンテキストを使用します</span><span class="sxs-lookup"><span data-stu-id="d5196-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="d5196-122">Transport</span><span class="sxs-lookup"><span data-stu-id="d5196-122">Transport</span></span>|<span data-ttu-id="d5196-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="d5196-123">HTTP</span></span>|  
  
## <a name="service"></a><span data-ttu-id="d5196-124">サービス</span><span class="sxs-lookup"><span data-stu-id="d5196-124">Service</span></span>  
 <span data-ttu-id="d5196-125">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="d5196-125">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="d5196-126">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d5196-126">Do one of the following:</span></span>  
  
-   <span data-ttu-id="d5196-127">構成を使用せずに、コードを使用してスタンドアロン サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5196-127">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="d5196-128">提供された構成を使用してサービスを作成しますが、エンドポイントを定義しません。</span><span class="sxs-lookup"><span data-stu-id="d5196-128">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d5196-129">コード</span><span class="sxs-lookup"><span data-stu-id="d5196-129">Code</span></span>  
 <span data-ttu-id="d5196-130">次のコードは、メッセージ セキュリティを使用するサービス エンドポイントの作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d5196-130">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#8)]
 [!code-vb[C_SecurityScenarios#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#8)]  
  
### <a name="configuration"></a><span data-ttu-id="d5196-131">構成</span><span class="sxs-lookup"><span data-stu-id="d5196-131">Configuration</span></span>  
 <span data-ttu-id="d5196-132">コードの代わりに次の構成を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5196-132">The following configuration can be used instead of the code.</span></span> <span data-ttu-id="d5196-133">サービス動作要素を使用して、クライアントに対するサービスの認証に使用する証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5196-133">The service behavior element is used to specify a certificate that is used to authenticate the service to the client.</span></span> <span data-ttu-id="d5196-134">サービス要素は、`behaviorConfiguration` 属性を使用して動作を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5196-134">The service element must specify the behavior using the `behaviorConfiguration` attribute.</span></span> <span data-ttu-id="d5196-135">バインド要素で、クライアント資格情報の種類が `None` であることを指定します。この資格情報の種類では、匿名クライアントがサービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5196-135">The binding element specifies that the client credential type is `None`, allowing anonymous clients to use the service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="WSHttpBinding_ICalculator"   
                  name="CalculatorService"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="d5196-136">Client</span><span class="sxs-lookup"><span data-stu-id="d5196-136">Client</span></span>  
 <span data-ttu-id="d5196-137">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="d5196-137">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="d5196-138">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d5196-138">Do one of the following:</span></span>  
  
-   <span data-ttu-id="d5196-139">コード (およびクライアント コード) を使用してスタンドアロン クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5196-139">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="d5196-140">エンドポイント アドレスを定義しないクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5196-140">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="d5196-141">代わりに、引数として構成名を受け取るクライアント コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5196-141">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="d5196-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d5196-142">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="d5196-143">コード</span><span class="sxs-lookup"><span data-stu-id="d5196-143">Code</span></span>  
 <span data-ttu-id="d5196-144">クライアントのインスタンスを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d5196-144">The following code creates an instance of the client.</span></span> <span data-ttu-id="d5196-145">バインディングはメッセージ モード セキュリティを使用し、クライアント資格情報の種類は None に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d5196-145">The binding uses message mode security, and the client credential type is set to none.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#15)]
 [!code-vb[C_SecurityScenarios#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#15)]  
  
### <a name="configuration"></a><span data-ttu-id="d5196-146">構成</span><span class="sxs-lookup"><span data-stu-id="d5196-146">Configuration</span></span>  
 <span data-ttu-id="d5196-147">クライアントを構成する場合のコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d5196-147">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"  
        binding="wsHttpBinding"  
        bindingConfiguration="WSHttpBinding_ICalculator"   
        contract="ICalculator"  
        name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5196-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5196-148">See Also</span></span>  
 [<span data-ttu-id="d5196-149">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="d5196-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="d5196-150">分散アプリケーションのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="d5196-150">Distributed Application Security</span></span>](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [<span data-ttu-id="d5196-151">メッセージ セキュリティ匿名</span><span class="sxs-lookup"><span data-stu-id="d5196-151">Message Security Anonymous</span></span>](../../../../docs/framework/wcf/samples/message-security-anonymous.md)  
 [<span data-ttu-id="d5196-152">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="d5196-152">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="d5196-153">Windows Server App Fabric のセキュリティ モデル</span><span class="sxs-lookup"><span data-stu-id="d5196-153">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)

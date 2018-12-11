---
title: ユーザー名クライアントを使用したメッセージ セキュリティ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
ms.openlocfilehash: 76accbccc1f65bb44b7e710f3f24dc2bae17eeda
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155000"
---
# <a name="message-security-with-a-user-name-client"></a><span data-ttu-id="7f916-102">ユーザー名クライアントを使用したメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="7f916-102">Message Security with a User Name Client</span></span>
<span data-ttu-id="7f916-103">次の図は、Windows Communication Foundation (WCF) サービスとクライアントのメッセージ レベルのセキュリティを使用して保護します。</span><span class="sxs-lookup"><span data-stu-id="7f916-103">The following illustration shows an Windows Communication Foundation (WCF) service and client secured using message-level security.</span></span> <span data-ttu-id="7f916-104">サービスは X.509 証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="7f916-104">The service is authenticated with an X.509 certificate.</span></span> <span data-ttu-id="7f916-105">クライアントはユーザー名とパスワードを使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="7f916-105">The client authenticates using a user name and password.</span></span>  
  
 <span data-ttu-id="7f916-106">サンプル アプリケーションでは、次を参照してください。[メッセージ セキュリティ ユーザー名](../../../../docs/framework/wcf/samples/message-security-user-name.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f916-106">For a sample application, see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span></span>  
  
 <span data-ttu-id="7f916-107">![ユーザー名認証を使用して、メッセージ セキュリティ](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span><span class="sxs-lookup"><span data-stu-id="7f916-107">![Message security using username authentication](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span></span>  
  
|<span data-ttu-id="7f916-108">特徴</span><span class="sxs-lookup"><span data-stu-id="7f916-108">Characteristic</span></span>|<span data-ttu-id="7f916-109">説明</span><span class="sxs-lookup"><span data-stu-id="7f916-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7f916-110">セキュリティ モード</span><span class="sxs-lookup"><span data-stu-id="7f916-110">Security Mode</span></span>|<span data-ttu-id="7f916-111">メッセージ</span><span class="sxs-lookup"><span data-stu-id="7f916-111">Message</span></span>|  
|<span data-ttu-id="7f916-112">相互運用性</span><span class="sxs-lookup"><span data-stu-id="7f916-112">Interoperability</span></span>|<span data-ttu-id="7f916-113">Windows Communication Foundation (WCF) のみ</span><span class="sxs-lookup"><span data-stu-id="7f916-113">Windows Communication Foundation (WCF) only</span></span>|  
|<span data-ttu-id="7f916-114">認証 (サーバー)</span><span class="sxs-lookup"><span data-stu-id="7f916-114">Authentication (Server)</span></span>|<span data-ttu-id="7f916-115">初期ネゴシエーションにはサーバー認証が必要</span><span class="sxs-lookup"><span data-stu-id="7f916-115">Initial negotiation requires server authentication</span></span>|  
|<span data-ttu-id="7f916-116">認証 (クライアント)</span><span class="sxs-lookup"><span data-stu-id="7f916-116">Authentication (Client)</span></span>|<span data-ttu-id="7f916-117">ユーザー名/パスワード</span><span class="sxs-lookup"><span data-stu-id="7f916-117">User name/password</span></span>|  
|<span data-ttu-id="7f916-118">整合性</span><span class="sxs-lookup"><span data-stu-id="7f916-118">Integrity</span></span>|<span data-ttu-id="7f916-119">はい、共有のセキュリティ コンテキストを使用します</span><span class="sxs-lookup"><span data-stu-id="7f916-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="7f916-120">機密性</span><span class="sxs-lookup"><span data-stu-id="7f916-120">Confidentiality</span></span>|<span data-ttu-id="7f916-121">はい、共有のセキュリティ コンテキストを使用します</span><span class="sxs-lookup"><span data-stu-id="7f916-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="7f916-122">Transport</span><span class="sxs-lookup"><span data-stu-id="7f916-122">Transport</span></span>|<span data-ttu-id="7f916-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="7f916-123">HTTP</span></span>|  
|<span data-ttu-id="7f916-124">バインディング</span><span class="sxs-lookup"><span data-stu-id="7f916-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="7f916-125">サービス</span><span class="sxs-lookup"><span data-stu-id="7f916-125">Service</span></span>  
 <span data-ttu-id="7f916-126">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="7f916-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="7f916-127">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7f916-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="7f916-128">構成を使用せずに、コードを使用してスタンドアロン サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f916-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="7f916-129">提供された構成を使用してサービスを作成しますが、エンドポイントを定義しません。</span><span class="sxs-lookup"><span data-stu-id="7f916-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7f916-130">コード</span><span class="sxs-lookup"><span data-stu-id="7f916-130">Code</span></span>  
 <span data-ttu-id="7f916-131">次のコードは、メッセージ セキュリティを使用するサービス エンドポイントの作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7f916-131">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a><span data-ttu-id="7f916-132">構成</span><span class="sxs-lookup"><span data-stu-id="7f916-132">Configuration</span></span>  
 <span data-ttu-id="7f916-133">コードの代わりに次の構成を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f916-133">The following configuration can be used instead of the code:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My"     
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"  
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">              
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="7f916-134">クライアント</span><span class="sxs-lookup"><span data-stu-id="7f916-134">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="7f916-135">コード</span><span class="sxs-lookup"><span data-stu-id="7f916-135">Code</span></span>  
 <span data-ttu-id="7f916-136">クライアントを作成する場合のコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7f916-136">The following code creates the client.</span></span> <span data-ttu-id="7f916-137">バインディングではメッセージ モード セキュリティを使用し、クライアント資格情報の種類は `UserName` に設定します。</span><span class="sxs-lookup"><span data-stu-id="7f916-137">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="7f916-138">ユーザー名とパスワードの指定はコードを使用する場合に限られます (構成可能ではありません)。</span><span class="sxs-lookup"><span data-stu-id="7f916-138">The user name and password can only be specified using code (it is not configurable).</span></span> <span data-ttu-id="7f916-139">ユーザー名とパスワードを返すコードは、アプリケーション レベルで実行される必要があるため、ここには示しません。</span><span class="sxs-lookup"><span data-stu-id="7f916-139">The code to return the user name and password is not shown here because it must be done at the application level.</span></span> <span data-ttu-id="7f916-140">たとえば、Windows フォーム ダイアログ ボックスを使用してユーザーにデータを照会します。</span><span class="sxs-lookup"><span data-stu-id="7f916-140">For example, use a Windows Forms dialog box to query the user for the data.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a><span data-ttu-id="7f916-141">構成</span><span class="sxs-lookup"><span data-stu-id="7f916-141">Configuration</span></span>  
 <span data-ttu-id="7f916-142">クライアントを構成する場合のコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7f916-142">The following code configures the client.</span></span> <span data-ttu-id="7f916-143">バインディングではメッセージ モード セキュリティを使用し、クライアント資格情報の種類は `UserName` に設定します。</span><span class="sxs-lookup"><span data-stu-id="7f916-143">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="7f916-144">ユーザー名とパスワードの指定はコードを使用する場合に限られます (構成可能ではありません)。</span><span class="sxs-lookup"><span data-stu-id="7f916-144">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
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
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f916-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f916-145">See Also</span></span>  
 [<span data-ttu-id="7f916-146">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="7f916-146">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="7f916-147">メッセージ セキュリティ ユーザー名</span><span class="sxs-lookup"><span data-stu-id="7f916-147">Message Security User Name</span></span>](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
 [<span data-ttu-id="7f916-148">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="7f916-148">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="7f916-149">\<identity></span><span class="sxs-lookup"><span data-stu-id="7f916-149">\<identity></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)  
 [<span data-ttu-id="7f916-150">Windows Server App Fabric のセキュリティ モデル</span><span class="sxs-lookup"><span data-stu-id="7f916-150">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)

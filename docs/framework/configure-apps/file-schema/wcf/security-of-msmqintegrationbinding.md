---
title: '&lt;msmqIntegrationBinding&gt; の &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6419c2157281d00cf79de16d4f494fc52bcee598
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2018
ms.locfileid: "44353841"
---
# <a name="ltsecuritygt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="04c3e-102">&lt;msmqIntegrationBinding&gt; の &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="04c3e-102">&lt;security&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="04c3e-103">メッセージ キュー (MSMQ) 統合チャネルのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="04c3e-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="04c3e-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="04c3e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="04c3e-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="04c3e-105">\<bindings></span></span>  
<span data-ttu-id="04c3e-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="04c3e-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="04c3e-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="04c3e-107">\<binding></span></span>  
<span data-ttu-id="04c3e-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="04c3e-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c3e-109">構文</span><span class="sxs-lookup"><span data-stu-id="04c3e-109">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>  
   <binding>   
       <security mode="None/Transport">  
         <transport msmqAuthenticationMode="None/Windows/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
          <message  algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"  
                        clientCredentialType="None/Windows/UserName/Certificate/CardSpace"  
            defaultProtectionLevel="None/Sign/EncryptAndSign" />  
       </security>  
   </binding>  
</msmqIntegrationBinding>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04c3e-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="04c3e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="04c3e-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="04c3e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04c3e-112">属性</span><span class="sxs-lookup"><span data-stu-id="04c3e-112">Attributes</span></span>  
  
|<span data-ttu-id="04c3e-113">属性</span><span class="sxs-lookup"><span data-stu-id="04c3e-113">Attribute</span></span>|<span data-ttu-id="04c3e-114">説明</span><span class="sxs-lookup"><span data-stu-id="04c3e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04c3e-115">モード</span><span class="sxs-lookup"><span data-stu-id="04c3e-115">mode</span></span>|<span data-ttu-id="04c3e-116">メッセージ キュー統合チャネルの整合性、機密性、および認証を制御するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="04c3e-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="04c3e-117">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="04c3e-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="04c3e-118">-None。 こうとセキュリティ。</span><span class="sxs-lookup"><span data-stu-id="04c3e-118">-   None: This disables security.</span></span><br /><span data-ttu-id="04c3e-119">-トランスポート: 保護と認証は、トランスポートによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="04c3e-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="04c3e-120">これは、2 つのキュー マネージャー間のメッセージ セキュリティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="04c3e-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="04c3e-121">アプリケーションとキュー マネージャーとの間にセキュリティは提供されません。</span><span class="sxs-lookup"><span data-stu-id="04c3e-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="04c3e-122">既存の Msmq アプリケーションは、この種類のセキュリティ モードと機能的に等価です。</span><span class="sxs-lookup"><span data-stu-id="04c3e-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="04c3e-123">既定値は `Transport` です。</span><span class="sxs-lookup"><span data-stu-id="04c3e-123">The default value is `Transport`.</span></span> <span data-ttu-id="04c3e-124">この属性は <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="04c3e-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04c3e-125">子要素</span><span class="sxs-lookup"><span data-stu-id="04c3e-125">Child Elements</span></span>  
  
|<span data-ttu-id="04c3e-126">要素</span><span class="sxs-lookup"><span data-stu-id="04c3e-126">Element</span></span>|<span data-ttu-id="04c3e-127">説明</span><span class="sxs-lookup"><span data-stu-id="04c3e-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04c3e-128">\<transport></span><span class="sxs-lookup"><span data-stu-id="04c3e-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="04c3e-129">メッセージ キュー統合トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="04c3e-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="04c3e-130">この要素は <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="04c3e-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04c3e-131">親要素</span><span class="sxs-lookup"><span data-stu-id="04c3e-131">Parent Elements</span></span>  
  
|<span data-ttu-id="04c3e-132">要素</span><span class="sxs-lookup"><span data-stu-id="04c3e-132">Element</span></span>|<span data-ttu-id="04c3e-133">説明</span><span class="sxs-lookup"><span data-stu-id="04c3e-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04c3e-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="04c3e-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="04c3e-135">バインド要素、 [ \<msmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="04c3e-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04c3e-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="04c3e-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 [<span data-ttu-id="04c3e-137">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="04c3e-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="04c3e-138">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="04c3e-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="04c3e-139">バインディング</span><span class="sxs-lookup"><span data-stu-id="04c3e-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="04c3e-140">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="04c3e-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="04c3e-141">バインドを使用して、Windows Communication Foundation サービスとクライアントを構成するには</span><span class="sxs-lookup"><span data-stu-id="04c3e-141">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="04c3e-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="04c3e-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="04c3e-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="04c3e-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)

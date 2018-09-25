---
title: '&lt;wsFederationHttpBinding&gt; の &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
author: BrucePerlerMS
ms.openlocfilehash: 7c7868561ea4d41b308d3bcd963e10e9b81df314
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078241"
---
# <a name="ltsecuritygt-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="78bcc-102">&lt;wsFederationHttpBinding&gt; の &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="78bcc-102">&lt;security&gt; of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="78bcc-103">セキュリティ設定を定義、 [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="78bcc-103">Defines the security settings of the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="78bcc-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="78bcc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="78bcc-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="78bcc-105">\<bindings></span></span>  
<span data-ttu-id="78bcc-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="78bcc-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="78bcc-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="78bcc-107">\<binding></span></span>  
<span data-ttu-id="78bcc-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="78bcc-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78bcc-109">構文</span><span class="sxs-lookup"><span data-stu-id="78bcc-109">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
    <binding >  
       <security mode="None/Message/TransportWithMessageCredential">  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
                        <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
                          </headers>  
                              <identity>  
                                 <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
                        </issuerMetadata>  
            <tokenRequestParameters>  
               <xmlElement>  
               </xmlElement>  
            </tokenRequestParameters>  
         </message>  
       </security>  
    </binding>  
</wsFederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78bcc-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="78bcc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="78bcc-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="78bcc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78bcc-112">属性</span><span class="sxs-lookup"><span data-stu-id="78bcc-112">Attributes</span></span>  
  
|<span data-ttu-id="78bcc-113">属性</span><span class="sxs-lookup"><span data-stu-id="78bcc-113">Attribute</span></span>|<span data-ttu-id="78bcc-114">説明</span><span class="sxs-lookup"><span data-stu-id="78bcc-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78bcc-115">モード</span><span class="sxs-lookup"><span data-stu-id="78bcc-115">Mode</span></span>|<span data-ttu-id="78bcc-116">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="78bcc-116">Optional.</span></span> <span data-ttu-id="78bcc-117">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="78bcc-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="78bcc-118">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="78bcc-118">The default value is `Message`.</span></span> <span data-ttu-id="78bcc-119">この属性は <xref:System.ServiceModel.WSFederationHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="78bcc-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="78bcc-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="78bcc-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="78bcc-121">値</span><span class="sxs-lookup"><span data-stu-id="78bcc-121">Value</span></span>|<span data-ttu-id="78bcc-122">説明</span><span class="sxs-lookup"><span data-stu-id="78bcc-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="78bcc-123">なし</span><span class="sxs-lookup"><span data-stu-id="78bcc-123">None</span></span>|<span data-ttu-id="78bcc-124">SOAP メッセージは、転送中はセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="78bcc-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="78bcc-125">メッセージ</span><span class="sxs-lookup"><span data-stu-id="78bcc-125">Message</span></span>|<span data-ttu-id="78bcc-126">SOAP メッセージ セキュリティを使用して、整合性、機密性、サーバー認証、およびクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="78bcc-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="78bcc-127">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="78bcc-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="78bcc-128">このサービスは、証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78bcc-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="78bcc-129">クライアント認証は、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="78bcc-129">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="78bcc-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="78bcc-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="78bcc-131">整合性、機密性、およびサーバー認証は、HTTPS によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="78bcc-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="78bcc-132">このサービスは、証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78bcc-132">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="78bcc-133">クライアント認証は、SOAP メッセージ セキュリティによって提供され、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="78bcc-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78bcc-134">子要素</span><span class="sxs-lookup"><span data-stu-id="78bcc-134">Child Elements</span></span>  
  
|<span data-ttu-id="78bcc-135">要素</span><span class="sxs-lookup"><span data-stu-id="78bcc-135">Element</span></span>|<span data-ttu-id="78bcc-136">説明</span><span class="sxs-lookup"><span data-stu-id="78bcc-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78bcc-137">\<message></span><span class="sxs-lookup"><span data-stu-id="78bcc-137">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="78bcc-138">メッセージ レベル セキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="78bcc-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="78bcc-139">この要素は <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="78bcc-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="78bcc-140">親要素</span><span class="sxs-lookup"><span data-stu-id="78bcc-140">Parent Elements</span></span>  
  
|<span data-ttu-id="78bcc-141">要素</span><span class="sxs-lookup"><span data-stu-id="78bcc-141">Element</span></span>|<span data-ttu-id="78bcc-142">説明</span><span class="sxs-lookup"><span data-stu-id="78bcc-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78bcc-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="78bcc-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="78bcc-144">すべてのバインド機能を定義、 [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="78bcc-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78bcc-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="78bcc-145">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="78bcc-146">方法 : WSFederationHttpBinding を作成する</span><span class="sxs-lookup"><span data-stu-id="78bcc-146">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="78bcc-147">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="78bcc-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="78bcc-148">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="78bcc-148">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="78bcc-149">バインディング</span><span class="sxs-lookup"><span data-stu-id="78bcc-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="78bcc-150">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="78bcc-150">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="78bcc-151">バインドを使用して、Windows Communication Foundation サービスとクライアントを構成するには</span><span class="sxs-lookup"><span data-stu-id="78bcc-151">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="78bcc-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="78bcc-152">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

---
title: <add> <scopedCertificates>要素
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 06a624d0146745581dfe907d044d1f7d3b857902
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119679"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="7d2d5-102">\<追加 > の\<scopedCertificates > 要素</span><span class="sxs-lookup"><span data-stu-id="7d2d5-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="7d2d5-103">範囲指定された証明書のコレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
 <span data-ttu-id="7d2d5-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7d2d5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7d2d5-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="7d2d5-105">\<behaviors></span></span>  
<span data-ttu-id="7d2d5-106">endpointBehaviors セクション</span><span class="sxs-lookup"><span data-stu-id="7d2d5-106">endpointBehaviors section</span></span>  
<span data-ttu-id="7d2d5-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7d2d5-107">\<behavior></span></span>  
<span data-ttu-id="7d2d5-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="7d2d5-108">\<clientCredentials></span></span>  
<span data-ttu-id="7d2d5-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="7d2d5-109">\<serviceCertificate></span></span>  
<span data-ttu-id="7d2d5-110">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="7d2d5-110">\<scopedCertificates></span></span>  
<span data-ttu-id="7d2d5-111">\<追加 > 要素の\<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="7d2d5-111">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d2d5-112">構文</span><span class="sxs-lookup"><span data-stu-id="7d2d5-112">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d2d5-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7d2d5-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7d2d5-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d2d5-115">属性</span><span class="sxs-lookup"><span data-stu-id="7d2d5-115">Attributes</span></span>  
  
|<span data-ttu-id="7d2d5-116">属性</span><span class="sxs-lookup"><span data-stu-id="7d2d5-116">Attribute</span></span>|<span data-ttu-id="7d2d5-117">説明</span><span class="sxs-lookup"><span data-stu-id="7d2d5-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d2d5-118">targetUri</span><span class="sxs-lookup"><span data-stu-id="7d2d5-118">targetUri</span></span>|<span data-ttu-id="7d2d5-119">文字列。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-119">String.</span></span> <span data-ttu-id="7d2d5-120">証明書に関連付けられているサービスの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-120">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="7d2d5-121">findValue</span><span class="sxs-lookup"><span data-stu-id="7d2d5-121">findValue</span></span>|<span data-ttu-id="7d2d5-122">文字列。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-122">String.</span></span> <span data-ttu-id="7d2d5-123">検索対象の値。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-123">The value to search for.</span></span>|  
|<span data-ttu-id="7d2d5-124">x509FindType</span><span class="sxs-lookup"><span data-stu-id="7d2d5-124">x509FindType</span></span>|<span data-ttu-id="7d2d5-125">列挙値。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-125">Enumeration.</span></span> <span data-ttu-id="7d2d5-126">検索する証明書フィールドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-126">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="7d2d5-127">storeLocation</span><span class="sxs-lookup"><span data-stu-id="7d2d5-127">storeLocation</span></span>|<span data-ttu-id="7d2d5-128">列挙値。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-128">Enumeration.</span></span> <span data-ttu-id="7d2d5-129">検索する 2 つの格納場所のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-129">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="7d2d5-130">storeName</span><span class="sxs-lookup"><span data-stu-id="7d2d5-130">storeName</span></span>|<span data-ttu-id="7d2d5-131">列挙値。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-131">Enumeration.</span></span> <span data-ttu-id="7d2d5-132">検索するシステム ストアのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-132">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="7d2d5-133">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="7d2d5-133">findValue Attribute</span></span>  
  
|<span data-ttu-id="7d2d5-134">値</span><span class="sxs-lookup"><span data-stu-id="7d2d5-134">Value</span></span>|<span data-ttu-id="7d2d5-135">説明</span><span class="sxs-lookup"><span data-stu-id="7d2d5-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d2d5-136">String</span><span class="sxs-lookup"><span data-stu-id="7d2d5-136">String</span></span>|<span data-ttu-id="7d2d5-137">値は、検索されるフィールド (X509FindType 属性により指定される) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-137">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="7d2d5-138">たとえば、サムプリント検索する場合、値は 16 進数の文字列にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-138">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="7d2d5-139">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="7d2d5-139">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="7d2d5-140">値</span><span class="sxs-lookup"><span data-stu-id="7d2d5-140">Value</span></span>|<span data-ttu-id="7d2d5-141">説明</span><span class="sxs-lookup"><span data-stu-id="7d2d5-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d2d5-142">列挙</span><span class="sxs-lookup"><span data-stu-id="7d2d5-142">Enumeration</span></span>|<span data-ttu-id="7d2d5-143">次の値が含まれます。FindByThumbprint、FindBySubjectName、FindBySubjectDistinguishedName、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName、FindByApplicationPolicy、FindByCertificatePolicy、FindByExtension、FindByKeyUsage、findbysubjectkeyidentifier です。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-143">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="7d2d5-144">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="7d2d5-144">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="7d2d5-145">値</span><span class="sxs-lookup"><span data-stu-id="7d2d5-145">Value</span></span>|<span data-ttu-id="7d2d5-146">説明</span><span class="sxs-lookup"><span data-stu-id="7d2d5-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d2d5-147">列挙型</span><span class="sxs-lookup"><span data-stu-id="7d2d5-147">Enumeration</span></span>|<span data-ttu-id="7d2d5-148">CurrentUser または LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-148">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="7d2d5-149">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="7d2d5-149">storeName Attribute</span></span>  
  
|<span data-ttu-id="7d2d5-150">値</span><span class="sxs-lookup"><span data-stu-id="7d2d5-150">Value</span></span>|<span data-ttu-id="7d2d5-151">説明</span><span class="sxs-lookup"><span data-stu-id="7d2d5-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d2d5-152">列挙</span><span class="sxs-lookup"><span data-stu-id="7d2d5-152">Enumeration</span></span>|<span data-ttu-id="7d2d5-153">次の値が含まれます。AddressBook、AuthRoot、CertificateAuthority、Disallowed、My、Root、TrustedPeople、および TrustedPublisher です。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-153">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d2d5-154">子要素</span><span class="sxs-lookup"><span data-stu-id="7d2d5-154">Child Elements</span></span>  
 <span data-ttu-id="7d2d5-155">なし。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d2d5-156">親要素</span><span class="sxs-lookup"><span data-stu-id="7d2d5-156">Parent Elements</span></span>  
  
|<span data-ttu-id="7d2d5-157">要素</span><span class="sxs-lookup"><span data-stu-id="7d2d5-157">Element</span></span>|<span data-ttu-id="7d2d5-158">説明</span><span class="sxs-lookup"><span data-stu-id="7d2d5-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d2d5-159">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="7d2d5-159">\<scopedCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|<span data-ttu-id="7d2d5-160">認証用の (範囲指定された) 特定のサービスにより提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-160">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d2d5-161">Remarks</span><span class="sxs-lookup"><span data-stu-id="7d2d5-161">Remarks</span></span>  
 <span data-ttu-id="7d2d5-162">この要素を使用すると、クライアントは、通信するサービスの URL に基づいて、使用するサービス証明書を構成できます。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-162">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="7d2d5-163">これは、クライアントが複数のサービス (エンド サービスと中間セキュリティ トークン サービス) と通信している可能性がある発行済みトークンのシナリオで特に便利です。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-163">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="7d2d5-164">証明書に基づくメッセージ セキュリティを使用したバインドにおいて、この証明書を使用してサービスへのメッセージを暗号化します。サービスがクライアントへの応答に署名する際には、この証明書を使用することが要求されます。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-164">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="7d2d5-165">バインディングにサービスの証明書が必要で、サービスの URL に対する特定の証明書が ScopedCertificates 内に存在しない場合は、既定の証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-165">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="7d2d5-166">詳細については、の スコープの証明書"セクションを参照してください。[方法。フェデレーション クライアントを作成](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)です。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-166">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d2d5-167">例</span><span class="sxs-lookup"><span data-stu-id="7d2d5-167">Example</span></span>  
 <span data-ttu-id="7d2d5-168">次の例は、コレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-168">The following example adds an X.509 certificate the collection.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <serviceCertificate>
          <scopedCertificates>
            <add targetUri="http://www.contoso.com"
                 findValue="www.Contoso.com"
                 storeLocation="LocalMachine"
                 storeName="Root"
                 x509FindType="FindByIssuerName" />
          </scopedCertificates>
        </serviceCertificate>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="7d2d5-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d2d5-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="7d2d5-170">方法: フェデレーション クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="7d2d5-170">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="7d2d5-171">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="7d2d5-171">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="7d2d5-172">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="7d2d5-172">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="7d2d5-173">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="7d2d5-173">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

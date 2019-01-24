---
title: '&lt;clientCertificate&gt; 要素の &lt;certificate&gt;'
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: 37eef7a435447d22b56e865ac72ef5d4c1ff0674
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708897"
---
# <a name="ltcertificategt-of-ltclientcertificategt-element"></a><span data-ttu-id="9f4cc-102">&lt;clientCertificate&gt; 要素の &lt;certificate&gt;</span><span class="sxs-lookup"><span data-stu-id="9f4cc-102">&lt;certificate&gt; of &lt;clientCertificate&gt; Element</span></span>
<span data-ttu-id="9f4cc-103">メッセージの署名と暗号化に使用される X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
 <span data-ttu-id="9f4cc-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9f4cc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9f4cc-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="9f4cc-105">\<behaviors></span></span>  
<span data-ttu-id="9f4cc-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9f4cc-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="9f4cc-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9f4cc-107">\<behavior></span></span>  
<span data-ttu-id="9f4cc-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="9f4cc-108">\<serviceCredentials></span></span>  
<span data-ttu-id="9f4cc-109">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="9f4cc-109">\<clientCertificate></span></span>  
<span data-ttu-id="9f4cc-110">\<証明書 ></span><span class="sxs-lookup"><span data-stu-id="9f4cc-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f4cc-111">構文</span><span class="sxs-lookup"><span data-stu-id="9f4cc-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f4cc-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9f4cc-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9f4cc-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f4cc-114">属性</span><span class="sxs-lookup"><span data-stu-id="9f4cc-114">Attributes</span></span>  
  
|<span data-ttu-id="9f4cc-115">属性</span><span class="sxs-lookup"><span data-stu-id="9f4cc-115">Attribute</span></span>|<span data-ttu-id="9f4cc-116">説明</span><span class="sxs-lookup"><span data-stu-id="9f4cc-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="9f4cc-117">X.509 証明書ストアで検索する値を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="9f4cc-118">属性に含まれている型は、指定された X509FindType の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-118">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="9f4cc-119">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="9f4cc-120">クライアントがサーバーの証明書の検証に使用する X.509 証明書ストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-120">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="9f4cc-121">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9f4cc-122">-LocalMachine: ローカル マシンに割り当てられている証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="9f4cc-123">-CurrentUser: 現在のユーザーに割り当てられている証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="9f4cc-124">既定は LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="9f4cc-125">開く X.509 証明書ストアの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="9f4cc-126">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9f4cc-127">-AddressBook:他のユーザーの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="9f4cc-128">-   AuthRoot:サード パーティ証明機関 (Ca) 証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="9f4cc-129">-証明機関:中間証明機関 (Ca) 証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-129">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="9f4cc-130">-許可されていません。失効した証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="9f4cc-131">-My:個人用証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="9f4cc-132">ルート:信頼されたルート証明機関 (Ca) 証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="9f4cc-133">-TrustedPeople:直接信頼されたユーザーとリソースの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-133">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="9f4cc-134">-TrustedPublisher:直接信頼された発行者の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-134">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="9f4cc-135">既定値は My です。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="9f4cc-136">実行する X.509 検索の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="9f4cc-137">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9f4cc-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="9f4cc-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="9f4cc-139">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="9f4cc-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="9f4cc-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="9f4cc-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="9f4cc-141">-   FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="9f4cc-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="9f4cc-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="9f4cc-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="9f4cc-143">-   FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="9f4cc-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="9f4cc-144">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="9f4cc-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="9f4cc-145">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="9f4cc-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="9f4cc-146">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="9f4cc-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="9f4cc-147">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="9f4cc-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="9f4cc-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="9f4cc-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="9f4cc-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="9f4cc-149">-   FindByExtension</span></span><br /><span data-ttu-id="9f4cc-150">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="9f4cc-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="9f4cc-151">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="9f4cc-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="9f4cc-152">`findValue` 属性に含まれている型は、指定された X509FindType の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="9f4cc-153">既定値は FindBySubjectDistinguishedName です。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f4cc-154">子要素</span><span class="sxs-lookup"><span data-stu-id="9f4cc-154">Child Elements</span></span>  
 <span data-ttu-id="9f4cc-155">なし。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9f4cc-156">親要素</span><span class="sxs-lookup"><span data-stu-id="9f4cc-156">Parent Elements</span></span>  
  
|<span data-ttu-id="9f4cc-157">要素</span><span class="sxs-lookup"><span data-stu-id="9f4cc-157">Element</span></span>|<span data-ttu-id="9f4cc-158">説明</span><span class="sxs-lookup"><span data-stu-id="9f4cc-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f4cc-159">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="9f4cc-159">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="9f4cc-160">Remarks</span><span class="sxs-lookup"><span data-stu-id="9f4cc-160">Remarks</span></span>  
 <span data-ttu-id="9f4cc-161">`<certificate>` 要素は、サービスがクライアントと安全に通信するために、サービスが前もってクライアントの証明書を持っている必要がある場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-161">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="9f4cc-162">このような状況は、双方向通信パターンを使用する場合に生じます。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-162">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="9f4cc-163">より一般的な要求/応答パターンでは、クライアントは自身の証明書を要求に含め、サービスはそれを使用してクライアントへの応答を暗号化し、署名します。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-163">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="9f4cc-164">一方、双方向通信パターンでは、サービスにはクライアントからの要求が来ないので、クライアントの証明書をあらかじめ取得することで、クライアント宛のメッセージのセキュリティを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-164">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="9f4cc-165">このため、クライアントの証明書を帯域外のネゴシエーションで取得し、この要素を使用して証明書を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-165">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="9f4cc-166">双方向サービスの詳細については、次を参照してください。[方法。双方向コントラクトを作成する](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)します。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-166">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f4cc-167">例</span><span class="sxs-lookup"><span data-stu-id="9f4cc-167">Example</span></span>  
 <span data-ttu-id="9f4cc-168">次のコードは、`<authentication>` 要素の適切な X.509 証明書とカスタム検証タイプの検索方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-168">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="9f4cc-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f4cc-169">See also</span></span>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="9f4cc-170">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="9f4cc-170">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9f4cc-171">方法: カスタム証明書の検証を使用するサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9f4cc-171">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="9f4cc-172">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="9f4cc-172">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)

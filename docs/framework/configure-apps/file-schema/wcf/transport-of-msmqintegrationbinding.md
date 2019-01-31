---
title: <transport> の <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: c266d751ff3e89f653763ed83c78041d89e22517
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55290148"
---
# <a name="transport-of-msmqintegrationbinding"></a><span data-ttu-id="ec8f5-102">\<トランスポート > の\<msmqIntegrationBinding ></span><span class="sxs-lookup"><span data-stu-id="ec8f5-102">\<transport> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="ec8f5-103">メッセージ キュー統合トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
 <span data-ttu-id="ec8f5-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ec8f5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ec8f5-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ec8f5-105">\<bindings></span></span>  
<span data-ttu-id="ec8f5-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="ec8f5-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="ec8f5-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="ec8f5-107">\<binding></span></span>  
<span data-ttu-id="ec8f5-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="ec8f5-108">\<security></span></span>  
<span data-ttu-id="ec8f5-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="ec8f5-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec8f5-110">構文</span><span class="sxs-lookup"><span data-stu-id="ec8f5-110">Syntax</span></span>  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec8f5-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ec8f5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ec8f5-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec8f5-113">属性</span><span class="sxs-lookup"><span data-stu-id="ec8f5-113">Attributes</span></span>  
  
|<span data-ttu-id="ec8f5-114">属性</span><span class="sxs-lookup"><span data-stu-id="ec8f5-114">Attribute</span></span>|<span data-ttu-id="ec8f5-115">説明</span><span class="sxs-lookup"><span data-stu-id="ec8f5-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="ec8f5-116">MSMQ トランスポートによるメッセージの認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="ec8f5-117">これが `None` に設定されている場合、`msmqProtectionLevel` 属性の値も `None` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="ec8f5-118">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ec8f5-119">-None。認証はありません。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-119">-   None: No authentication.</span></span><br /><span data-ttu-id="ec8f5-120">-   WindowsDomain:認証メカニズムでは、Active Directory を使用して、メッセージに関連付けられている SID の X.509 証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-120">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="ec8f5-121">次に、これを使用してキューの ACL がチェックされ、ユーザーがキューに書き込む権限を持っていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="ec8f5-122">-証明書:チャネルは、証明書ストアから証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="ec8f5-123">既定値は WindowsDomain です。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-123">The default value is WindowsDomain.</span></span> <span data-ttu-id="ec8f5-124">この属性は <xref:System.ServiceModel.MsmqAuthenticationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="ec8f5-125">メッセージ キュー マネージャー間でメッセージを転送するときに、ネットワーク上でメッセージの暗号化に使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="ec8f5-126">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ec8f5-127">-[Rc4stream]</span><span class="sxs-lookup"><span data-stu-id="ec8f5-127">-   RC4Stream</span></span><br /><span data-ttu-id="ec8f5-128">-AES</span><span class="sxs-lookup"><span data-stu-id="ec8f5-128">-   AES</span></span><br /><br /> <span data-ttu-id="ec8f5-129">既定値は RC4Stream です。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-129">The default value is RC4Stream.</span></span> <span data-ttu-id="ec8f5-130">この属性は <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="ec8f5-131">MSMQ トランスポートのレベルでメッセージをセキュリティで保護する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="ec8f5-132">暗号化を行うとメッセージの整合性が確保されますが、EncryptAndSign を使用するとメッセージの整合性と否認防止の両方が確保されます。つまり、メッセージは本当にその送信者から送信されていることになり、記載されている送信者が実際の送信者になります。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span><br /><br /> <span data-ttu-id="ec8f5-133">-有効な値を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-133">-   Valid values include the following:</span></span><br /><span data-ttu-id="ec8f5-134">-None。保護されません。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-134">-   None: No protection.</span></span><br /><span data-ttu-id="ec8f5-135">署名:メッセージは署名されます。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="ec8f5-136">-EncryptAndSign:メッセージは暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="ec8f5-137">既定値は Sign です。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-137">The default value is Sign.</span></span> <span data-ttu-id="ec8f5-138">この属性は、ProtectionLevel 型です。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-138">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="ec8f5-139">-署名の一部としてダイジェストを計算で使用するアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-139">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="ec8f5-140">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-140">Valid values include the following:</span></span><br /><span data-ttu-id="ec8f5-141">-   MD5</span><span class="sxs-lookup"><span data-stu-id="ec8f5-141">-   MD5</span></span><br /><span data-ttu-id="ec8f5-142">-SHA1</span><span class="sxs-lookup"><span data-stu-id="ec8f5-142">-   SHA1</span></span><br /><span data-ttu-id="ec8f5-143">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="ec8f5-143">-   SHA256</span></span><br /><span data-ttu-id="ec8f5-144">-SHA512</span><span class="sxs-lookup"><span data-stu-id="ec8f5-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="ec8f5-145">既定値は SHA1 です。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-145">The default value is SHA1.</span></span> <span data-ttu-id="ec8f5-146">この属性は <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec8f5-147">子要素</span><span class="sxs-lookup"><span data-stu-id="ec8f5-147">Child Elements</span></span>  
 <span data-ttu-id="ec8f5-148">なし</span><span class="sxs-lookup"><span data-stu-id="ec8f5-148">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec8f5-149">親要素</span><span class="sxs-lookup"><span data-stu-id="ec8f5-149">Parent Elements</span></span>  
  
|<span data-ttu-id="ec8f5-150">要素</span><span class="sxs-lookup"><span data-stu-id="ec8f5-150">Element</span></span>|<span data-ttu-id="ec8f5-151">説明</span><span class="sxs-lookup"><span data-stu-id="ec8f5-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec8f5-152">\<security></span><span class="sxs-lookup"><span data-stu-id="ec8f5-152">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="ec8f5-153">MSMQ バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-153">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec8f5-154">Remarks</span><span class="sxs-lookup"><span data-stu-id="ec8f5-154">Remarks</span></span>  
 <span data-ttu-id="ec8f5-155">この要素は、メッセージ キュー統合トランスポートのセキュリティ設定をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-155">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="ec8f5-156">設定は、メッセージ キュー統合トランスポートとキューに置かれているトランスポートの両方で同じです。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-156">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="ec8f5-157">この設定を使用すると、認証モード、暗号化アルゴリズム、セキュア ハッシュ アルゴリズム、および保護レベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="ec8f5-157">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec8f5-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec8f5-158">See also</span></span>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="ec8f5-159">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="ec8f5-159">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ec8f5-160">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="ec8f5-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ec8f5-161">バインディング</span><span class="sxs-lookup"><span data-stu-id="ec8f5-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ec8f5-162">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="ec8f5-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ec8f5-163">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="ec8f5-163">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ec8f5-164">\<binding></span><span class="sxs-lookup"><span data-stu-id="ec8f5-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

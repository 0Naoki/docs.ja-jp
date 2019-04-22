---
title: <issuerChannelBehaviors> 要素
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 7cbd50daa82b0ca937a1bba93786545898b03c8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58890476"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="815c9-102">\<issuerChannelBehaviors > 要素</span><span class="sxs-lookup"><span data-stu-id="815c9-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="815c9-103">指定されたサービス トークン サービスと通信するときに使用するには、Windows Communication Foundation (WCF) クライアント エンドポイントの動作 (構成で定義されている) のコレクションを含みます。</span><span class="sxs-lookup"><span data-stu-id="815c9-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="815c9-104">定義された動作は、いずれかを含めることはできません[ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)要素。</span><span class="sxs-lookup"><span data-stu-id="815c9-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

## <a name="syntax"></a><span data-ttu-id="815c9-105">構文</span><span class="sxs-lookup"><span data-stu-id="815c9-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="815c9-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="815c9-106">Attributes and Elements</span></span>

<span data-ttu-id="815c9-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="815c9-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="815c9-108">属性</span><span class="sxs-lookup"><span data-stu-id="815c9-108">Attributes</span></span>

<span data-ttu-id="815c9-109">なし。</span><span class="sxs-lookup"><span data-stu-id="815c9-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="815c9-110">子要素</span><span class="sxs-lookup"><span data-stu-id="815c9-110">Child Elements</span></span>

|<span data-ttu-id="815c9-111">要素</span><span class="sxs-lookup"><span data-stu-id="815c9-111">Element</span></span>|<span data-ttu-id="815c9-112">説明</span><span class="sxs-lookup"><span data-stu-id="815c9-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="815c9-113">\<add></span><span class="sxs-lookup"><span data-stu-id="815c9-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="815c9-114">コレクションに動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="815c9-114">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="815c9-115">親要素</span><span class="sxs-lookup"><span data-stu-id="815c9-115">Parent Elements</span></span>

|<span data-ttu-id="815c9-116">要素</span><span class="sxs-lookup"><span data-stu-id="815c9-116">Element</span></span>|<span data-ttu-id="815c9-117">説明</span><span class="sxs-lookup"><span data-stu-id="815c9-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="815c9-118">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="815c9-118">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="815c9-119">サービスに対するクライアントの認証に使用されるカスタム トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="815c9-119">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="815c9-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="815c9-120">Remarks</span></span>

<span data-ttu-id="815c9-121">この要素を使用するのは、なんらかの動作 (`<clientCredentials>` 要素を含む動作以外) を使用してサービスと通信する必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="815c9-121">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="815c9-122">たとえば場合、 [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)動作要素を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="815c9-122">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="815c9-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="815c9-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="815c9-124">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="815c9-124">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="815c9-125">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="815c9-125">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="815c9-126">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="815c9-126">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="815c9-127">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="815c9-127">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="815c9-128">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="815c9-128">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="815c9-129">方法: フェデレーション クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="815c9-129">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="815c9-130">方法: ローカル発行者を構成します。</span><span class="sxs-lookup"><span data-stu-id="815c9-130">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="815c9-131">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="815c9-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)

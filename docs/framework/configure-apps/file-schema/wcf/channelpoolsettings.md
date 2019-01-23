---
title: '&lt;channelPoolSettings&gt;'
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 666602bde75cd21b5b3d16bd4d5e6cf63c12d593
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554960"
---
# <a name="ltchannelpoolsettingsgt"></a><span data-ttu-id="58252-102">&lt;channelPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="58252-102">&lt;channelPoolSettings&gt;</span></span>
<span data-ttu-id="58252-103">カスタム バインドのチャネル プール設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="58252-103">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="58252-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="58252-104">\<system.serviceModel></span></span>  
<span data-ttu-id="58252-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="58252-105">\<bindings></span></span>  
<span data-ttu-id="58252-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="58252-106">\<customBinding></span></span>  
<span data-ttu-id="58252-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="58252-107">\<binding></span></span>  
<span data-ttu-id="58252-108">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="58252-108">\<oneWay></span></span>  
<span data-ttu-id="58252-109">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="58252-109">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58252-110">構文</span><span class="sxs-lookup"><span data-stu-id="58252-110">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58252-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="58252-111">Attributes and Elements</span></span>  
 <span data-ttu-id="58252-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="58252-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58252-113">属性</span><span class="sxs-lookup"><span data-stu-id="58252-113">Attributes</span></span>  
  
|<span data-ttu-id="58252-114">属性</span><span class="sxs-lookup"><span data-stu-id="58252-114">Attribute</span></span>|<span data-ttu-id="58252-115">説明</span><span class="sxs-lookup"><span data-stu-id="58252-115">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="58252-116">プール内のチャネルの接続が切断されるまでの最大アイドル時間を指定する正の <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="58252-116">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="58252-117">既定値は 00:02:00 です。</span><span class="sxs-lookup"><span data-stu-id="58252-117">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="58252-118">プールに返されたチャネルが閉じられるまでの時間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="58252-118">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="58252-119">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="58252-119">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="58252-120">各リモート エンドポイントのプール内に格納できるチャネルの最大数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="58252-120">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="58252-121">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="58252-121">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58252-122">子要素</span><span class="sxs-lookup"><span data-stu-id="58252-122">Child Elements</span></span>  
 <span data-ttu-id="58252-123">なし。</span><span class="sxs-lookup"><span data-stu-id="58252-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58252-124">親要素</span><span class="sxs-lookup"><span data-stu-id="58252-124">Parent Elements</span></span>  
  
|<span data-ttu-id="58252-125">要素</span><span class="sxs-lookup"><span data-stu-id="58252-125">Element</span></span>|<span data-ttu-id="58252-126">説明</span><span class="sxs-lookup"><span data-stu-id="58252-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58252-127">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="58252-127">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|<span data-ttu-id="58252-128">カスタム バインドでパケット ルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="58252-128">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58252-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="58252-129">Remarks</span></span>  
 <span data-ttu-id="58252-130">クォータは、リソースの過剰な消費を防ぐためのポリシー メカニズムとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="58252-130">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="58252-131">クォータは、悪質な、または意図的でないサービス拒否 (DOS) 攻撃を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="58252-131">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="58252-132">カスタム チャネルにチャネル クォータを設定するには、この要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="58252-132">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="58252-133">`ChannelPoolSettings` では、次の 3 つのクォータを指定します。</span><span class="sxs-lookup"><span data-stu-id="58252-133">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
-   <span data-ttu-id="58252-134">`idleTimeout` クォータは、サーバーでは、長時間リソースを停滞させることによるサービス拒否 (DOS) 攻撃を軽減するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="58252-134">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="58252-135">クライアントでは、適切な値を設定することで、サービスとの接続の信頼性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="58252-135">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="58252-136">既定値では、リソースが控えめに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="58252-136">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="58252-137">開発環境、および小規模のインストール シナリオに適しています。</span><span class="sxs-lookup"><span data-stu-id="58252-137">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="58252-138">インストールでリソースが不足している場合、または追加リソースが使用可能であるにもかかわらず接続が制限されている場合、サービス管理者は値を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58252-138">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="58252-139">`leaseTimeout` クォータは、負荷分散機能との統合、および信頼性の向上のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="58252-139">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="58252-140">既定値では、リソースが控えめに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="58252-140">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="58252-141">開発環境、および小規模のインストール シナリオに適しています。</span><span class="sxs-lookup"><span data-stu-id="58252-141">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="58252-142">インストールでリソースが不足している場合、または追加リソースが使用可能であるにもかかわらず接続が制限されている場合、サービス管理者は値を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58252-142">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="58252-143">`maxOutboundChannelsPerEndpoint` クォータは、サーバーとクライアントの両方に対するキャッシュ制限を設定し、信頼性向上のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="58252-143">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="58252-144">既定値ではリソースが控えめに割り当てられており、開発環境および小規模なインストール シナリオに適しています。</span><span class="sxs-lookup"><span data-stu-id="58252-144">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="58252-145">インストールでリソースが不足している場合、または追加リソースが使用可能であるにもかかわらず接続が制限されている場合、サービス管理者は値をレビューする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58252-145">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58252-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="58252-146">See also</span></span>
- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="58252-147">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="58252-147">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)
- [<span data-ttu-id="58252-148">バインディング</span><span class="sxs-lookup"><span data-stu-id="58252-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="58252-149">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="58252-149">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="58252-150">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="58252-150">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="58252-151">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="58252-151">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

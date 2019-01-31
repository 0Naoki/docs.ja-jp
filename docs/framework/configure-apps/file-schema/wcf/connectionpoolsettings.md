---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 76b8a0feaf51b39c9c988d853db7e3bf96244905
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284584"
---
# <a name="connectionpoolsettings"></a><span data-ttu-id="663f0-101">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="663f0-101">\<connectionPoolSettings></span></span>
<span data-ttu-id="663f0-102">名前付きパイプ バインディングの追加の接続プール設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="663f0-102">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
 <span data-ttu-id="663f0-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="663f0-103">\<system.serviceModel></span></span>  
<span data-ttu-id="663f0-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="663f0-104">\<bindings></span></span>  
<span data-ttu-id="663f0-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="663f0-105">\<customBinding></span></span>  
<span data-ttu-id="663f0-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="663f0-106">\<binding></span></span>  
<span data-ttu-id="663f0-107">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="663f0-107">\<namePipeTransport></span></span>  
<span data-ttu-id="663f0-108">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="663f0-108">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="663f0-109">構文</span><span class="sxs-lookup"><span data-stu-id="663f0-109">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="663f0-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="663f0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="663f0-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="663f0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="663f0-112">属性</span><span class="sxs-lookup"><span data-stu-id="663f0-112">Attributes</span></span>  
  
|<span data-ttu-id="663f0-113">属性</span><span class="sxs-lookup"><span data-stu-id="663f0-113">Attribute</span></span>|<span data-ttu-id="663f0-114">説明</span><span class="sxs-lookup"><span data-stu-id="663f0-114">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="663f0-115">送信チャネルに使用される接続プールの名前を定義する文字列です。</span><span class="sxs-lookup"><span data-stu-id="663f0-115">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="663f0-116">ストリーム配信モードでは、接続が共有されません。したがって、接続プールは無効です。</span><span class="sxs-lookup"><span data-stu-id="663f0-116">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="663f0-117">既定は、"default" 文字列です。</span><span class="sxs-lookup"><span data-stu-id="663f0-117">The default is a "default" string.</span></span> <span data-ttu-id="663f0-118">この値を変更して、特定のクライアントの接続を、個別のグループに分離できます。</span><span class="sxs-lookup"><span data-stu-id="663f0-118">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="663f0-119">接続が切断されるまでの最大アイドル時間を指定する正の <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="663f0-119">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="663f0-120">既定値は 00:02:00 です。</span><span class="sxs-lookup"><span data-stu-id="663f0-120">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="663f0-121">そのサービスによって開始されるリモート エンドポイントへの接続の最大数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="663f0-121">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="663f0-122">制限を超えた接続は、制限内に空きができるまでキューに置かれます。</span><span class="sxs-lookup"><span data-stu-id="663f0-122">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="663f0-123">`idleTimeout` は、例外がスローされるまでに接続をキューに入れたままにする期間を制限します。</span><span class="sxs-lookup"><span data-stu-id="663f0-123">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="663f0-124">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="663f0-124">The default is 10.</span></span><br /><br /> <span data-ttu-id="663f0-125">この属性は、クライアントから特定のサービス エンドポイントへの接続で、同時にアクティブできる接続数を制限します。</span><span class="sxs-lookup"><span data-stu-id="663f0-125">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="663f0-126">この値よりも多くのアクティブなクライアント接続がある場合、サービスは、クライアントに応答しないように見える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="663f0-126">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="663f0-127">この場合は、この値を調整して、予想される特定のエンドポイントへの同時クライアント接続の最大数より大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="663f0-127">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="663f0-128">子要素</span><span class="sxs-lookup"><span data-stu-id="663f0-128">Child Elements</span></span>  
 <span data-ttu-id="663f0-129">なし。</span><span class="sxs-lookup"><span data-stu-id="663f0-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="663f0-130">親要素</span><span class="sxs-lookup"><span data-stu-id="663f0-130">Parent Elements</span></span>  
  
|<span data-ttu-id="663f0-131">要素</span><span class="sxs-lookup"><span data-stu-id="663f0-131">Element</span></span>|<span data-ttu-id="663f0-132">説明</span><span class="sxs-lookup"><span data-stu-id="663f0-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="663f0-133">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="663f0-133">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="663f0-134">チャネルで名前付きパイプを使用してメッセージを転送するトランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="663f0-134">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="663f0-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="663f0-135">See also</span></span>
- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="663f0-136">トランスポート</span><span class="sxs-lookup"><span data-stu-id="663f0-136">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="663f0-137">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="663f0-137">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="663f0-138">バインディング</span><span class="sxs-lookup"><span data-stu-id="663f0-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="663f0-139">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="663f0-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="663f0-140">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="663f0-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="663f0-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="663f0-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

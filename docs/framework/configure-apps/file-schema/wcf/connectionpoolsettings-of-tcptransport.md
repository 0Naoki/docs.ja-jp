---
title: <connectionPoolSettings> の <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: 93363c5ff1753ff02956404da7697780078c9839
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129975"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="406c9-102">\<connectionPoolSettings > の\<tcpTransport ></span><span class="sxs-lookup"><span data-stu-id="406c9-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="406c9-103">TCP トランスポートの追加の接続プール設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="406c9-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
 <span data-ttu-id="406c9-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="406c9-104">\<system.serviceModel></span></span>  
<span data-ttu-id="406c9-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="406c9-105">\<bindings></span></span>  
<span data-ttu-id="406c9-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="406c9-106">\<customBinding></span></span>  
<span data-ttu-id="406c9-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="406c9-107">\<binding></span></span>  
<span data-ttu-id="406c9-108">\<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="406c9-108">\<tcpTransport></span></span>  
<span data-ttu-id="406c9-109">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="406c9-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="406c9-110">構文</span><span class="sxs-lookup"><span data-stu-id="406c9-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="406c9-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="406c9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="406c9-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="406c9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="406c9-113">属性</span><span class="sxs-lookup"><span data-stu-id="406c9-113">Attributes</span></span>  
  
|<span data-ttu-id="406c9-114">属性</span><span class="sxs-lookup"><span data-stu-id="406c9-114">Attribute</span></span>|<span data-ttu-id="406c9-115">説明</span><span class="sxs-lookup"><span data-stu-id="406c9-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="406c9-116">送信チャネルに使用される接続プールの名前を定義する文字列です。</span><span class="sxs-lookup"><span data-stu-id="406c9-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="406c9-117">ストリーム配信モードでは、接続が共有されません。したがって、接続プールは無効です。</span><span class="sxs-lookup"><span data-stu-id="406c9-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="406c9-118">既定は、"default" 文字列です。</span><span class="sxs-lookup"><span data-stu-id="406c9-118">The default is a "default" string.</span></span> <span data-ttu-id="406c9-119">この値を変更して、特定のクライアントの接続を、個別のグループに分離できます。</span><span class="sxs-lookup"><span data-stu-id="406c9-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="406c9-120">接続が切断されるまでの最大アイドル時間を指定する正の <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="406c9-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="406c9-121">既定値は 00:02:00 です。</span><span class="sxs-lookup"><span data-stu-id="406c9-121">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="406c9-122">アクティブな接続が終了されるまでの時間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="406c9-122">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="406c9-123">既定値は 00:05:00 です。</span><span class="sxs-lookup"><span data-stu-id="406c9-123">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="406c9-124">接続は、接続キャッシュに返された後、アクティブに転送中ではないときに終了します。</span><span class="sxs-lookup"><span data-stu-id="406c9-124">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="406c9-125">TCP トランスポートによって使用される接続キャッシュは、各エンドポイントの必要に応じて、`maxOutboundConnectionsPerEndpoint.` で設定されているキャッシュ制限内で新しい接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="406c9-125">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="406c9-126">そのサービスによって開始されるリモート エンドポイントへの接続の最大数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="406c9-126">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="406c9-127">制限を超えた接続は、制限内に空きができるまでキューに置かれます。</span><span class="sxs-lookup"><span data-stu-id="406c9-127">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="406c9-128">`idleTimeout` は、例外がスローされるまでに接続をキューに入れたままにする期間を制限します。</span><span class="sxs-lookup"><span data-stu-id="406c9-128">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="406c9-129">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="406c9-129">The default is 10.</span></span><br /><br /> <span data-ttu-id="406c9-130">この属性は、クライアントから特定のサービス エンドポイントへの接続で、同時にアクティブできる接続数を制限します。</span><span class="sxs-lookup"><span data-stu-id="406c9-130">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="406c9-131">この値よりも多くのアクティブなクライアント接続がある場合、サービスは、クライアントに応答しないように見える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="406c9-131">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="406c9-132">この場合は、この値を調整して、予想される特定のエンドポイントへの同時クライアント接続の最大数より大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="406c9-132">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="406c9-133">子要素</span><span class="sxs-lookup"><span data-stu-id="406c9-133">Child Elements</span></span>  
 <span data-ttu-id="406c9-134">なし。</span><span class="sxs-lookup"><span data-stu-id="406c9-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="406c9-135">親要素</span><span class="sxs-lookup"><span data-stu-id="406c9-135">Parent Elements</span></span>  
  
|<span data-ttu-id="406c9-136">要素</span><span class="sxs-lookup"><span data-stu-id="406c9-136">Element</span></span>|<span data-ttu-id="406c9-137">説明</span><span class="sxs-lookup"><span data-stu-id="406c9-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="406c9-138">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="406c9-138">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="406c9-139">チャネルで名前付きパイプを使用してメッセージを転送するトランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="406c9-139">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="406c9-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="406c9-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="406c9-141">トランスポート</span><span class="sxs-lookup"><span data-stu-id="406c9-141">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="406c9-142">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="406c9-142">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="406c9-143">バインディング</span><span class="sxs-lookup"><span data-stu-id="406c9-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="406c9-144">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="406c9-144">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="406c9-145">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="406c9-145">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="406c9-146">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="406c9-146">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

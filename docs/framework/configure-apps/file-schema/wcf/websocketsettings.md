---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 298bf27b171772bb039b11b5e5de70e7d45b061d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258448"
---
# <a name="websocketsettings"></a><span data-ttu-id="018f8-101">\<webSocketSettings ></span><span class="sxs-lookup"><span data-stu-id="018f8-101">\<webSocketSettings></span></span>
<span data-ttu-id="018f8-102">Web ソケット設定を指定するために使用される構成要素。</span><span class="sxs-lookup"><span data-stu-id="018f8-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="018f8-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="018f8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="018f8-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="018f8-104">\<bindings></span></span>  
<span data-ttu-id="018f8-105">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="018f8-105">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="018f8-106">構文</span><span class="sxs-lookup"><span data-stu-id="018f8-106">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="018f8-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="018f8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="018f8-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="018f8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="018f8-109">属性</span><span class="sxs-lookup"><span data-stu-id="018f8-109">Attributes</span></span>  
  
|<span data-ttu-id="018f8-110">属性</span><span class="sxs-lookup"><span data-stu-id="018f8-110">Attribute</span></span>|<span data-ttu-id="018f8-111">説明</span><span class="sxs-lookup"><span data-stu-id="018f8-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="018f8-112">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="018f8-112">createNotificationOnConnection</span></span>|<span data-ttu-id="018f8-113">通知を接続時に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="018f8-113">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="018f8-114">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="018f8-114">disablePayloadMasking</span></span>|<span data-ttu-id="018f8-115">Web ソケットのマスクが無効であるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="018f8-115">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="018f8-116">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="018f8-116">keepAliveInterval</span></span>|<span data-ttu-id="018f8-117">接続維持の間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="018f8-117">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="018f8-118">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="018f8-118">maxPendingConnections</span></span>|<span data-ttu-id="018f8-119">サービスでのディスパッチを待機している接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="018f8-119">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="018f8-120">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="018f8-120">receiveBufferSize</span></span>|<span data-ttu-id="018f8-121">受信バッファーのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="018f8-121">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="018f8-122">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="018f8-122">sendBufferSize</span></span>|<span data-ttu-id="018f8-123">送信バッファーのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="018f8-123">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="018f8-124">subProtocol</span><span class="sxs-lookup"><span data-stu-id="018f8-124">subProtocol</span></span>|<span data-ttu-id="018f8-125">Web ソケットのサブプロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="018f8-125">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="018f8-126">transportUsage</span><span class="sxs-lookup"><span data-stu-id="018f8-126">transportUsage</span></span>|<span data-ttu-id="018f8-127">Web ソケットを使用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="018f8-127">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="018f8-128">transportUsage 属性</span><span class="sxs-lookup"><span data-stu-id="018f8-128">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="018f8-129">値</span><span class="sxs-lookup"><span data-stu-id="018f8-129">Value</span></span>|<span data-ttu-id="018f8-130">説明</span><span class="sxs-lookup"><span data-stu-id="018f8-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="018f8-131">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="018f8-131">WhenDuplex</span></span>|<span data-ttu-id="018f8-132">コントラクトが双方向の場合に、Web ソケット プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="018f8-132">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="018f8-133">Always</span><span class="sxs-lookup"><span data-stu-id="018f8-133">Always</span></span>|<span data-ttu-id="018f8-134">コントラクトにかかわらず、常にWeb ソケット プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="018f8-134">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="018f8-135">Never</span><span class="sxs-lookup"><span data-stu-id="018f8-135">Never</span></span>|<span data-ttu-id="018f8-136">Web ソケット プロトコルを使用しません。</span><span class="sxs-lookup"><span data-stu-id="018f8-136">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="018f8-137">子要素</span><span class="sxs-lookup"><span data-stu-id="018f8-137">Child Elements</span></span>  
 <span data-ttu-id="018f8-138">なし</span><span class="sxs-lookup"><span data-stu-id="018f8-138">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="018f8-139">親要素</span><span class="sxs-lookup"><span data-stu-id="018f8-139">Parent Elements</span></span>  
  
|<span data-ttu-id="018f8-140">要素</span><span class="sxs-lookup"><span data-stu-id="018f8-140">Element</span></span>|<span data-ttu-id="018f8-141">説明</span><span class="sxs-lookup"><span data-stu-id="018f8-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="018f8-142">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="018f8-142">\<netHttpBinding></span></span>|<span data-ttu-id="018f8-143">NetHttpBinding を指定します。</span><span class="sxs-lookup"><span data-stu-id="018f8-143">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="018f8-144">例</span><span class="sxs-lookup"><span data-stu-id="018f8-144">Example</span></span>  
 <span data-ttu-id="018f8-145">次の例は、使用する方法を示します、 \<webSocketSettings > 要素。</span><span class="sxs-lookup"><span data-stu-id="018f8-145">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="018f8-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="018f8-146">See also</span></span>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="018f8-147">バインディング</span><span class="sxs-lookup"><span data-stu-id="018f8-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="018f8-148">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="018f8-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="018f8-149">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="018f8-149">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="018f8-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="018f8-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

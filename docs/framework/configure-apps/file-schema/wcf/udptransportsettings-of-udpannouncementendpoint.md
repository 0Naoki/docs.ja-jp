---
title: <udpTransportSettings> の <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: a7ddff1a-5eed-4bbc-8580-b95ef8890e1f
ms.openlocfilehash: 901b7e1429c3afc19e9b609026dc632730c35024
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788168"
---
# <a name="udptransportsettings-of-udpannouncementendpoint"></a><span data-ttu-id="ccb4f-102">\<udpTransportSettings > の\<udpAnnouncementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="ccb4f-102">\<udpTransportSettings> of \<udpAnnouncementEndpoint></span></span>
<span data-ttu-id="ccb4f-103">この構成要素の UDP トランスポート設定を公開する[ \<udpAnnouncementEndpoint >](udpannouncementendpoint.md)します。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-103">This configuration element exposes UDP transport settings for [\<udpAnnouncementEndpoint>](udpannouncementendpoint.md).</span></span>  
  
<span data-ttu-id="ccb4f-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ccb4f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ccb4f-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="ccb4f-105">\<standardEndpoints></span></span>  
<span data-ttu-id="ccb4f-106">\<udpAnnouncementEndpoint></span><span class="sxs-lookup"><span data-stu-id="ccb4f-106">\<udpAnnouncementEndpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb4f-107">構文</span><span class="sxs-lookup"><span data-stu-id="ccb4f-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <udpAnnouncementEndpoint>
      <standardEndpoint>
        <updTransportSettings duplicateMessageHistoryLength="Integer"
                              maxBufferPoolSize="Integer"
                              maxMulticastRetransmitCount="Integer"
                              maxPendingMessageCount="Integer"
                              maxReceivedMessageSize="Integer"
                              maxUnicastRetransmitCount="Integer"
                              multicastInterfaceId="String"
                              socketReceiveBufferSize="Integer"
                              timeToLive="Integer" />
      </standardEndpoint>
    </udpAnnouncementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccb4f-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ccb4f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ccb4f-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccb4f-110">属性</span><span class="sxs-lookup"><span data-stu-id="ccb4f-110">Attributes</span></span>  
  
|<span data-ttu-id="ccb4f-111">属性</span><span class="sxs-lookup"><span data-stu-id="ccb4f-111">Attribute</span></span>|<span data-ttu-id="ccb4f-112">説明</span><span class="sxs-lookup"><span data-stu-id="ccb4f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ccb4f-113">duplicateMessageHistoryLength</span><span class="sxs-lookup"><span data-stu-id="ccb4f-113">duplicateMessageHistoryLength</span></span>|<span data-ttu-id="ccb4f-114">重複するメッセージを特定するためにトランスポートによって使用されるメッセージ ハッシュの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-114">An integer that specifies the maximum number of message hashes used by the transport for identifying duplicate messages.</span></span>  <span data-ttu-id="ccb4f-115">重複の検出は、TransportManager レベルで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-115">Duplicate detection will be done at the TransportManager level.</span></span> <span data-ttu-id="ccb4f-116">このプロパティを 0 に設定すると、重複の検出は無効になります。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-116">Setting this property to 0 disables duplicate detection.</span></span><br /><br /> <span data-ttu-id="ccb4f-117">この属性を使用して、システムの管理者や開発者は重複するメッセージの検出アルゴリズムをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-117">This attribute allows system administrators or developers to turn off duplicate message detection algorithms.</span></span> <span data-ttu-id="ccb4f-118">これは、独自の重複検出アルゴリズムを実行する場合に望ましいことがあります。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-118">This may be desirable if you want to implement your own duplicate detection algorithm.</span></span><br /><br /> <span data-ttu-id="ccb4f-119">既定値は 4112 です。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-119">The default is 4112.</span></span>|  
|<span data-ttu-id="ccb4f-120">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="ccb4f-120">maxBufferPoolSize</span></span>|<span data-ttu-id="ccb4f-121">トランスポートによって使用されるバッファー プールの最大サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-121">An integer that specifies the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="ccb4f-122">maxMulticastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="ccb4f-122">maxMulticastRetransmitCount</span></span>|<span data-ttu-id="ccb4f-123">メッセージを (最初に送信した後に) 再送信する最大回数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-123">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span><br /><br /> <span data-ttu-id="ccb4f-124">既定値は 2 です。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-124">The default is 2.</span></span>|  
|<span data-ttu-id="ccb4f-125">maxPendingMessageCount</span><span class="sxs-lookup"><span data-stu-id="ccb4f-125">maxPendingMessageCount</span></span>|<span data-ttu-id="ccb4f-126">受信して、各チャネル インスタンスの InputQueue からまだ削除していないメッセージの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-126">An integer that specifies the maximum number of messages that have been received but not yet removed from the InputQueue for an individual channel instance.</span></span>  <span data-ttu-id="ccb4f-127">InputQueue が保留メッセージ数の上限に達すると、メッセージは削除されます。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-127">If the InputQueue has hit its pending message count limit, the message will be dropped.</span></span><br /><br /> <span data-ttu-id="ccb4f-128">既定値は 32 です。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-128">The default is 32.</span></span>|  
|<span data-ttu-id="ccb4f-129">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="ccb4f-129">maxReceivedMessageSize</span></span>|<span data-ttu-id="ccb4f-130">バインディングで処理できるメッセージの最大サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-130">An integer that specifies the maximum size for a message that can be processed by the binding.</span></span><br /><br /> <span data-ttu-id="ccb4f-131">既定値は 65507 です。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-131">The default value is 65507.</span></span>|  
|<span data-ttu-id="ccb4f-132">maxUnicastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="ccb4f-132">maxUnicastRetransmitCount</span></span>|<span data-ttu-id="ccb4f-133">メッセージを (最初に送信した後に) 再送信する最大回数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-133">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span>  <span data-ttu-id="ccb4f-134">メッセージをユニキャスト アドレスに送信し、対応する RelatesTo ヘッダーの付いた応答メッセージを受信すると、再送信は早期に (再送信の回数が構成された回数に到達する前に) 終了することがあります。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-134">If the message is sent to a unicast address and a response message is received with a corresponding RelatesTo header, then retransmission may terminate early (before retransmitting the configured number of times).</span></span><br /><br /> <span data-ttu-id="ccb4f-135">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-135">The default value is 1.</span></span>|  
|<span data-ttu-id="ccb4f-136">multicastInterfaceId</span><span class="sxs-lookup"><span data-stu-id="ccb4f-136">multicastInterfaceId</span></span>|<span data-ttu-id="ccb4f-137">マルチホーム コンピューター上でマルチキャスト トラフィックを送受信するときに使用するネットワーク アダプターを一意に識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-137">A string that uniquely identifies the network adapter that should be used when sending and receiving multicast traffic on multi-homed machines.</span></span> <span data-ttu-id="ccb4f-138">実行時には、トランスポートは、この属性値を使用してインターフェイスのインデックスを参照します。このインデックスは、その後、`IP_MULTICAST_IF` および `IPV6_MULTICAST_IF` のソケット オプションの設定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-138">At runtime, the transport will use this attribute value to lookup the interface index, which is then used to set the `IP_MULTICAST_IF` and `IPV6_MULTICAST_IF` socket options.</span></span>  <span data-ttu-id="ccb4f-139">マルチキャスト グループに参加するときには、同じインターフェイス インデックスが使用されます (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-139">The same interface index will be used when joining a multicast group, if applicable.</span></span><br /><br /> <span data-ttu-id="ccb4f-140">既定値は `null` です。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-140">The default value is `null`.</span></span>|  
|<span data-ttu-id="ccb4f-141">socketReceiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="ccb4f-141">socketReceiveBufferSize</span></span>|<span data-ttu-id="ccb4f-142">基になる WinSock ソケットの受信バッファー サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-142">An integer that specifies the receive buffer size on the underlying WinSock socket.</span></span><br /><br /> <span data-ttu-id="ccb4f-143">受信チャネルのユーザーは、バインディング上のこの属性を使用して、データ受信時のシステム動作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-143">A user of a receiving channel can use this attribute on the Binding to control how the system behaves when it receives data.</span></span>  <span data-ttu-id="ccb4f-144">たとえば、受信 WCF メッセージを最大しきい値で利用するアプリケーションがある場合、この属性値よりも大きい値を使用すると、アプリケーションが処理できるようになるまで待機している間、メッセージを WinSock バッファーにスタックできます。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-144">For example, given an application that is consuming inbound WCF messages at the maximum threshold, using a higher value for this attribute would allow messages to stack up in the WinSock buffer while waiting for the application to be able to process them.</span></span>  <span data-ttu-id="ccb4f-145">同じ状況で属性値よりも小さい値を使用すると、メッセージは削除されることになります。この属性は、基になる WinSock `SO_RCVBUF` ソケット オプションを公開します。この属性値には、`maxReceivedMessageSize` のサイズ以上の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-145">Using a lower value in the same situation would result in messages getting dropped.This attribute exposes the underlying WinSock `SO_RCVBUF` socket option.This attribute value must be at least the size of `maxReceivedMessageSize`.</span></span>   <span data-ttu-id="ccb4f-146">この値を `maxReceivedMessageSize` よりも小さい値に設定すると、ランタイム例外が発生する原因になります。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-146">Setting it to a value smaller than the `maxReceivedMessageSize` will result in runtime exception.</span></span><br /><br /> <span data-ttu-id="ccb4f-147">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-147">The default value is 65536.</span></span>|  
|<span data-ttu-id="ccb4f-148">timeToLive</span><span class="sxs-lookup"><span data-stu-id="ccb4f-148">timeToLive</span></span>|<span data-ttu-id="ccb4f-149">マルチキャスト パケットが走査できるネットワーク セグメント ホップの数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-149">An integer that specifies the number of network segment hops that a multicast packet can traverse.</span></span>  <span data-ttu-id="ccb4f-150">この属性は、`IP_MULTICAST_TTL` および `IP_TTL` ソケット オプションに関連付けられている機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-150">This attribute exposes the functionality associated with the `IP_MULTICAST_TTL` and `IP_TTL` socket options.</span></span><br /><br /> <span data-ttu-id="ccb4f-151">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-151">The default value is 1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ccb4f-152">子要素</span><span class="sxs-lookup"><span data-stu-id="ccb4f-152">Child Elements</span></span>  
 <span data-ttu-id="ccb4f-153">なし。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ccb4f-154">親要素</span><span class="sxs-lookup"><span data-stu-id="ccb4f-154">Parent Elements</span></span>  
  
|<span data-ttu-id="ccb4f-155">要素</span><span class="sxs-lookup"><span data-stu-id="ccb4f-155">Element</span></span>|<span data-ttu-id="ccb4f-156">説明</span><span class="sxs-lookup"><span data-stu-id="ccb4f-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccb4f-157">\<udpAnnouncementEndpoint></span><span class="sxs-lookup"><span data-stu-id="ccb4f-157">\<udpAnnouncementEndpoint></span></span>](udpannouncementendpoint.md)|<span data-ttu-id="ccb4f-158">固定アナウンス コントラクトと UDP トランスポート バインディングを持つ標準エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="ccb4f-158">A standard endpoint that has fixed announcement contract and UDP transport binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccb4f-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccb4f-159">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpTransportSettings>

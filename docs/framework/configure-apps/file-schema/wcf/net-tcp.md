---
title: '&lt;net.tcp&gt;'
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 2a75a33eac61d85a0dab4732cb3b0de7f4703fa7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145784"
---
# <a name="ltnettcpgt"></a><span data-ttu-id="a8a77-102">&lt;net.tcp&gt;</span><span class="sxs-lookup"><span data-stu-id="a8a77-102">&lt;net.tcp&gt;</span></span>
<span data-ttu-id="a8a77-103">複数のプロセスが同じ TCP ポートを共有できる NET.TCP ポート共有サービスの構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8a77-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="a8a77-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="a8a77-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="a8a77-105">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="a8a77-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8a77-106">構文</span><span class="sxs-lookup"><span data-stu-id="a8a77-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="Integer"
             maxPendingAccepts="Integer"
             maxPendingConnections="Integer"
             receiveTimeout="TimeSpan"
             teredoEnabled="Boolean">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only)-->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="a8a77-107">型</span><span class="sxs-lookup"><span data-stu-id="a8a77-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8a77-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a8a77-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a8a77-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8a77-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8a77-110">属性</span><span class="sxs-lookup"><span data-stu-id="a8a77-110">Attributes</span></span>  
  
|<span data-ttu-id="a8a77-111">属性</span><span class="sxs-lookup"><span data-stu-id="a8a77-111">Attribute</span></span>|<span data-ttu-id="a8a77-112">説明</span><span class="sxs-lookup"><span data-stu-id="a8a77-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="a8a77-113">共有接続から受け入れられたが、Windows Communication Foundation (WCF) サービスにまだディスパッチされていない最大の未処理の接続を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="a8a77-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="a8a77-114">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="a8a77-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="a8a77-115">整数は、共有サービスの待機エンドポイントで同時に受け入れる未処理のスレッドの最大数を示しています。</span><span class="sxs-lookup"><span data-stu-id="a8a77-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="a8a77-116">既定値は 2 です。</span><span class="sxs-lookup"><span data-stu-id="a8a77-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="a8a77-117">アプリケーションによる受け入れをリスナーで待機できる最大接続数。</span><span class="sxs-lookup"><span data-stu-id="a8a77-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="a8a77-118">このクォータ値を超過すると、新規の受信接続は受け入れられるのを待機せずに切断されます。</span><span class="sxs-lookup"><span data-stu-id="a8a77-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="a8a77-119">メッセージ セキュリティのような接続機能では、クライアントは複数の接続を開くことがあります。</span><span class="sxs-lookup"><span data-stu-id="a8a77-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="a8a77-120">このクォータ値を設定する場合、サービス管理者はこのような追加の接続も考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8a77-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="a8a77-121">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="a8a77-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="a8a77-122">フレーム データを読み取り、基礎となる接続から接続ディスパッチを実行するタイムアウトを指定する `TimeSpan` です。</span><span class="sxs-lookup"><span data-stu-id="a8a77-122">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="a8a77-123">既定値は "00:00:10" です。</span><span class="sxs-lookup"><span data-stu-id="a8a77-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="a8a77-124">ポート共有サービスが Microsoft Teredo サービスを使用して WCF サービスに代わって TCP ポートでリッスンするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="a8a77-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="a8a77-125">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="a8a77-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8a77-126">子要素</span><span class="sxs-lookup"><span data-stu-id="a8a77-126">Child Elements</span></span>  
  
|<span data-ttu-id="a8a77-127">要素</span><span class="sxs-lookup"><span data-stu-id="a8a77-127">Element</span></span>|<span data-ttu-id="a8a77-128">説明</span><span class="sxs-lookup"><span data-stu-id="a8a77-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8a77-129">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="a8a77-129">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="a8a77-130">格納する構成要素のコレクションを`securityIdentifier`属性を WCF サービスをホストし、共有サービスへの接続アクセスが許可されるプロセスのユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8a77-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8a77-131">親要素</span><span class="sxs-lookup"><span data-stu-id="a8a77-131">Parent Elements</span></span>  
  
|<span data-ttu-id="a8a77-132">要素</span><span class="sxs-lookup"><span data-stu-id="a8a77-132">Element</span></span>|<span data-ttu-id="a8a77-133">説明</span><span class="sxs-lookup"><span data-stu-id="a8a77-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8a77-134">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="a8a77-134">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="a8a77-135">リスナー プロセス SMSvcHost.exe の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8a77-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8a77-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="a8a77-136">Remarks</span></span>  
 <span data-ttu-id="a8a77-137">ポート共有の詳細については、次を参照してください。 [Net.TCP ポート共有](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)します。</span><span class="sxs-lookup"><span data-stu-id="a8a77-137">For more information on port sharing, see [Net.TCP Port Sharing](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="a8a77-138">ポート共有サービスを構成する方法については、次を参照してください。 [Net.TCP ポート共有サービスを構成する](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="a8a77-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8a77-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8a77-139">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [<span data-ttu-id="a8a77-140">Net.TCP ポート共有</span><span class="sxs-lookup"><span data-stu-id="a8a77-140">Net.TCP Port Sharing</span></span>](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [<span data-ttu-id="a8a77-141">Net.TCP ポート共有サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="a8a77-141">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)

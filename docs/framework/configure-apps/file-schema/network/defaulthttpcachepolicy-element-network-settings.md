---
title: '&lt;defaultHttpCachePolicy&gt;要素 (ネットワーク設定)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: def7f8a4a7961f403a108c116bae590d69e70d17
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50037877"
---
# <a name="ltdefaulthttpcachepolicygt-element-network-settings"></a><span data-ttu-id="99c2d-102">&lt;defaultHttpCachePolicy&gt;要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="99c2d-102">&lt;defaultHttpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="99c2d-103">HTTP キャッシュがアクティブでかどうかし、既定のキャッシュ ポリシーの記述について説明します。</span><span class="sxs-lookup"><span data-stu-id="99c2d-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="99c2d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="99c2d-104">\<configuration></span></span>  
<span data-ttu-id="99c2d-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="99c2d-105">\<system.net></span></span>  
<span data-ttu-id="99c2d-106">\<requestCaching ></span><span class="sxs-lookup"><span data-stu-id="99c2d-106">\<requestCaching></span></span>  
<span data-ttu-id="99c2d-107">\<defaultHttpCachePolicy ></span><span class="sxs-lookup"><span data-stu-id="99c2d-107">\<defaultHttpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99c2d-108">構文</span><span class="sxs-lookup"><span data-stu-id="99c2d-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99c2d-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="99c2d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="99c2d-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="99c2d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99c2d-111">属性</span><span class="sxs-lookup"><span data-stu-id="99c2d-111">Attributes</span></span>  
  
|<span data-ttu-id="99c2d-112">属性</span><span class="sxs-lookup"><span data-stu-id="99c2d-112">Attribute</span></span>|<span data-ttu-id="99c2d-113">説明</span><span class="sxs-lookup"><span data-stu-id="99c2d-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="99c2d-114">キャッシュされたオブジェクトが期限切れとしてマークされている前に、最大時間間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="99c2d-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="99c2d-115">過去の鮮度の計算時間前に、キャッシュされたオブジェクトが期限切れとしてマークされている最大の時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="99c2d-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="99c2d-116">フレッシュと見なすには、キャッシュされたオブジェクトの時間の最小値を指定します。</span><span class="sxs-lookup"><span data-stu-id="99c2d-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="99c2d-117">キャッシュ ポリシーは自動にするかどうか、またはキャッシュをバイパスするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="99c2d-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="99c2d-118">既定値は `BypassCache` です。</span><span class="sxs-lookup"><span data-stu-id="99c2d-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99c2d-119">子要素</span><span class="sxs-lookup"><span data-stu-id="99c2d-119">Child Elements</span></span>  
 <span data-ttu-id="99c2d-120">なし</span><span class="sxs-lookup"><span data-stu-id="99c2d-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99c2d-121">親要素</span><span class="sxs-lookup"><span data-stu-id="99c2d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="99c2d-122">要素</span><span class="sxs-lookup"><span data-stu-id="99c2d-122">Element</span></span>|<span data-ttu-id="99c2d-123">説明</span><span class="sxs-lookup"><span data-stu-id="99c2d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99c2d-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="99c2d-124">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="99c2d-125">ネットワーク要求のキャッシュ メカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="99c2d-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99c2d-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="99c2d-126">Remarks</span></span>  
 <span data-ttu-id="99c2d-127">値、`policyLevel`属性があるか、`BypassCache`または`Default`します。</span><span class="sxs-lookup"><span data-stu-id="99c2d-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="99c2d-128">値を`maximumAge`、 `maximumStale`、および`minimumFresh`要素の形式のいずれか、明示的な時間間隔は、 *d*.*hh*:*mm*:*ss* (日、時間、分、および秒)、または定数`minValue`または`maxValue`必要に応じて、します。</span><span class="sxs-lookup"><span data-stu-id="99c2d-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="99c2d-129">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="99c2d-129">Configuration Files</span></span>  
 <span data-ttu-id="99c2d-130">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="99c2d-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99c2d-131">例</span><span class="sxs-lookup"><span data-stu-id="99c2d-131">Example</span></span>  
 <span data-ttu-id="99c2d-132">次の例では、6 時間、2 日間の最大の有効期間と 4 時間の最大の古い時刻の最小の新しい時刻を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="99c2d-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99c2d-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="99c2d-133">See Also</span></span>  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [<span data-ttu-id="99c2d-134">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="99c2d-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

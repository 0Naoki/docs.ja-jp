---
title: <performanceCounter> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 30c5cd07c92a8fc3c340cab0ff9ae74e940c0c12
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210933"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="66416-102">\<performanceCounter > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="66416-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="66416-103">有効または、ネットワーク パフォーマンス カウンターを無効にします。</span><span class="sxs-lookup"><span data-stu-id="66416-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="66416-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="66416-104">\<configuration></span></span>  
<span data-ttu-id="66416-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="66416-105">\<system.net></span></span>  
<span data-ttu-id="66416-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="66416-106">\<settings></span></span>  
<span data-ttu-id="66416-107">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="66416-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66416-108">構文</span><span class="sxs-lookup"><span data-stu-id="66416-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66416-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="66416-109">Attributes and Elements</span></span>  
 <span data-ttu-id="66416-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="66416-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66416-111">属性</span><span class="sxs-lookup"><span data-stu-id="66416-111">Attributes</span></span>  
  
|<span data-ttu-id="66416-112">属性</span><span class="sxs-lookup"><span data-stu-id="66416-112">Attribute</span></span>|<span data-ttu-id="66416-113">説明</span><span class="sxs-lookup"><span data-stu-id="66416-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="66416-114">ネットワークのパフォーマンス カウンターが有効になっているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="66416-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="66416-115">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="66416-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66416-116">子要素</span><span class="sxs-lookup"><span data-stu-id="66416-116">Child Elements</span></span>  
 <span data-ttu-id="66416-117">なし。</span><span class="sxs-lookup"><span data-stu-id="66416-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66416-118">親要素</span><span class="sxs-lookup"><span data-stu-id="66416-118">Parent Elements</span></span>  
  
|<span data-ttu-id="66416-119">要素</span><span class="sxs-lookup"><span data-stu-id="66416-119">Element</span></span>|<span data-ttu-id="66416-120">説明</span><span class="sxs-lookup"><span data-stu-id="66416-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66416-121">設定</span><span class="sxs-lookup"><span data-stu-id="66416-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="66416-122"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="66416-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66416-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="66416-123">Remarks</span></span>  
 <span data-ttu-id="66416-124">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="66416-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="66416-125">ネットワーク パフォーマンス カウンターは、使用される構成ファイルで有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="66416-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="66416-126">すべてのネットワーク パフォーマンス カウンターは、構成ファイル内の 1 つの設定で有効または無効にされます。</span><span class="sxs-lookup"><span data-stu-id="66416-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="66416-127">ネットワーク パフォーマンス カウンターを個別に有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="66416-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="66416-128">特定のネットワーク パフォーマンス カウンターの詳細については、次を参照してください。[ネットワーク パフォーマンス カウンター](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking)します。</span><span class="sxs-lookup"><span data-stu-id="66416-128">For more information on the specific networking performance counters, see [Networking Performance Counters](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking).</span></span>  
  
 <span data-ttu-id="66416-129">既定値は、そのネットワークのパフォーマンス カウンターが無効です。</span><span class="sxs-lookup"><span data-stu-id="66416-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="66416-130"><xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>プロパティを使用しての現在の値を取得すること、**有効になっている**該当する構成ファイルからの属性。</span><span class="sxs-lookup"><span data-stu-id="66416-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66416-131">例</span><span class="sxs-lookup"><span data-stu-id="66416-131">Example</span></span>  
 <span data-ttu-id="66416-132">次の例は、構成する方法を示します、<xref:System.Net>と関連するネットワークのパフォーマンス カウンターを有効にする名前空間。</span><span class="sxs-lookup"><span data-stu-id="66416-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="66416-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="66416-133">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="66416-134">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="66416-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="66416-135">ネットワーク パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="66416-135">Networking Performance Counters</span></span>](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking)

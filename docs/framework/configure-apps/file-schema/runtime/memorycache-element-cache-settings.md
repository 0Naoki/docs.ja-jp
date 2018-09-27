---
title: '&lt;memoryCache&gt;要素 (キャッシュ設定)'
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2d6b7a1ba9c9b7ba598dbcea076ff6ee553ddc9a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2018
ms.locfileid: "47396904"
---
# <a name="ltmemorycachegt-element-cache-settings"></a><span data-ttu-id="099c7-102">&lt;memoryCache&gt;要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="099c7-102">&lt;memoryCache&gt; Element (Cache Settings)</span></span>
<span data-ttu-id="099c7-103"><xref:System.Runtime.Caching.MemoryCache> クラスに基づくキャッシュを構成するために使用される要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="099c7-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="099c7-104"><xref:System.Runtime.Caching.Configuration.MemoryCacheElement> クラスは、キャッシュの構成に使用できる [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) 要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="099c7-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="099c7-105"><xref:System.Runtime.Caching.MemoryCache> クラスの複数のインスタンスを、単一のアプリケーションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="099c7-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="099c7-106">構成ファイル内の各 `memoryCache` 要素には、指定した <xref:System.Runtime.Caching.MemoryCache> インスタンスの設定を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="099c7-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
 <span data-ttu-id="099c7-107">\<configuration></span><span class="sxs-lookup"><span data-stu-id="099c7-107">\<configuration></span></span>  
<span data-ttu-id="099c7-108">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="099c7-108">\<system.runtime.caching></span></span>  
<span data-ttu-id="099c7-109">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="099c7-109">\<memoryCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="099c7-110">構文</span><span class="sxs-lookup"><span data-stu-id="099c7-110">Syntax</span></span>  
  
```xml  
<memoryCache>   
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>   
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="099c7-111">型</span><span class="sxs-lookup"><span data-stu-id="099c7-111">Type</span></span>  
 <span data-ttu-id="099c7-112"><xref:System.Runtime.Caching.MemoryCache> クラス。</span><span class="sxs-lookup"><span data-stu-id="099c7-112"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="099c7-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="099c7-113">Attributes and Elements</span></span>  
 <span data-ttu-id="099c7-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="099c7-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="099c7-115">属性</span><span class="sxs-lookup"><span data-stu-id="099c7-115">Attributes</span></span>  
  
|<span data-ttu-id="099c7-116">属性</span><span class="sxs-lookup"><span data-stu-id="099c7-116">Attribute</span></span>|<span data-ttu-id="099c7-117">説明</span><span class="sxs-lookup"><span data-stu-id="099c7-117">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="099c7-118"><xref:System.Runtime.Caching.MemoryCache> オブジェクトのインスタンスを拡張できる最大メモリ サイズ (メガバイト)。</span><span class="sxs-lookup"><span data-stu-id="099c7-118">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="099c7-119">既定値は 0 であり、これは <xref:System.Runtime.Caching.MemoryCache> クラスの自動サイズ調整ヒューリスティックが既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="099c7-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="099c7-120">キャッシュ構成の名前。</span><span class="sxs-lookup"><span data-stu-id="099c7-120">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="099c7-121">キャッシュが使用できる物理メモリの割合。</span><span class="sxs-lookup"><span data-stu-id="099c7-121">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="099c7-122">既定値は 0 であり、これは <xref:System.Runtime.Caching.MemoryCache> クラスの自動サイズ調整ヒューリスティックが既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="099c7-122">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="099c7-123">時間間隔を示す値。この値を超えると、キャッシュの実装によりキャッシュ インスタンスに設定されている絶対およびパーセントのメモリ制限と現在のメモリ負荷が比較されます。</span><span class="sxs-lookup"><span data-stu-id="099c7-123">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="099c7-124">値は "HH:MM:SS" 形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="099c7-124">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="099c7-125">子要素</span><span class="sxs-lookup"><span data-stu-id="099c7-125">Child Elements</span></span>  
  
|<span data-ttu-id="099c7-126">要素</span><span class="sxs-lookup"><span data-stu-id="099c7-126">Element</span></span>|<span data-ttu-id="099c7-127">説明</span><span class="sxs-lookup"><span data-stu-id="099c7-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="099c7-128">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="099c7-128">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="099c7-129">`namedCache` インスタンスの構成設定のコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="099c7-129">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="099c7-130">親要素</span><span class="sxs-lookup"><span data-stu-id="099c7-130">Parent Elements</span></span>  
  
|<span data-ttu-id="099c7-131">要素</span><span class="sxs-lookup"><span data-stu-id="099c7-131">Element</span></span>|<span data-ttu-id="099c7-132">説明</span><span class="sxs-lookup"><span data-stu-id="099c7-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="099c7-133">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="099c7-133">\<system.runtime.caching></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="099c7-134">[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]に組み込まれているアプリケーションに出力キャッシュを実装できるようにするタイプが含まれます。</span><span class="sxs-lookup"><span data-stu-id="099c7-134">Contains types that let you implement output caching in applications that are built into the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="099c7-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="099c7-135">Remarks</span></span>  
 <span data-ttu-id="099c7-136"><xref:System.Runtime.Caching.MemoryCache> クラスは、抽象 <xref:System.Runtime.Caching.ObjectCache> クラスの具象実装です。</span><span class="sxs-lookup"><span data-stu-id="099c7-136">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="099c7-137"><xref:System.Runtime.Caching.MemoryCache> クラスのインスタンスには、アプリケーション構成ファイルの構成情報を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="099c7-137">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="099c7-138">[memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) 構成セクションには、 `namedCaches` の構成コレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="099c7-138">The [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="099c7-139">メモリ ベースのキャッシュ オブジェクトが初期化されると、まず、メモリ キャッシュ コンストラクターに渡されるパラメーターの名前と一致する `namedCaches` のエントリの検索が試行されます。</span><span class="sxs-lookup"><span data-stu-id="099c7-139">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="099c7-140">`namedCaches` のエントリが見つかると、ポーリングとメモリ管理の情報が構成ファイルから取得されます。</span><span class="sxs-lookup"><span data-stu-id="099c7-140">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="099c7-141">次に、初期化プロセスで、コンストラクターの構成情報にある名前/値ペアの任意のコレクションを使用して、構成エントリがオーバーライドされているかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="099c7-141">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="099c7-142">名前/値ペアのコレクションの、次の値のいずれかを渡すと、構成ファイルから取得した情報をその値がオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="099c7-142">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
-   <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
-   <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
-   <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="099c7-143">例</span><span class="sxs-lookup"><span data-stu-id="099c7-143">Example</span></span>  
 <span data-ttu-id="099c7-144">次の例は、 <xref:System.Runtime.Caching.MemoryCache> 属性を "default" に設定することで、 `name` オブジェクトの名前を既定のキャッシュ オブジェクト名に設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="099c7-144">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="099c7-145">`cacheMemoryLimitMegabytes` 属性および `physicalMemoryLimitPercentage` 属性はゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="099c7-145">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="099c7-146">これらの属性をゼロに設定すると、 <xref:System.Runtime.Caching.MemoryCache> の自動サイズ調整ヒューリスティックが既定で使用されることになります。</span><span class="sxs-lookup"><span data-stu-id="099c7-146">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="099c7-147">キャッシュの実装では、現在のメモリ負荷と絶対およびパーセントのメモリ制限を 2 分ごとに比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="099c7-147">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="099c7-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="099c7-148">See Also</span></span>  
 <xref:System.Runtime.Caching.MemoryCache>  
 [<span data-ttu-id="099c7-149">\<system.runtime.caching > 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="099c7-149">\<system.runtime.caching> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)  
 [<span data-ttu-id="099c7-150">\<namedCaches > 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="099c7-150">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)

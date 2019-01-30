---
title: <applicationPool> 要素 (Web 設定)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: b1afd6227444828c58b6dbb44de24fe82af9f8b2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271981"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="4e79b-102">\<applicationPool > 要素 (Web 設定)</span><span class="sxs-lookup"><span data-stu-id="4e79b-102">\<applicationPool> Element (Web Settings)</span></span>
<span data-ttu-id="4e79b-103">ASP.NET アプリケーションが統合モードで実行されている場合に、プロセス全体の動作を管理する、ASP.NET で使用される構成設定を指定します[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="4e79b-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4e79b-104">ASP.NET アプリケーションがホストされている場合のみ機能をサポートこの要素と機能[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="4e79b-104">This element and the feature it supports only work if your ASP.NET application is hosted on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="4e79b-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4e79b-105">\<configuration></span></span>  
<span data-ttu-id="4e79b-106">\<system.web > 要素 (Web 設定)</span><span class="sxs-lookup"><span data-stu-id="4e79b-106">\<system.web> Element (Web Settings)</span></span>  
<span data-ttu-id="4e79b-107">\<applicationPool > 要素 (Web 設定)</span><span class="sxs-lookup"><span data-stu-id="4e79b-107">\<applicationPool> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e79b-108">構文</span><span class="sxs-lookup"><span data-stu-id="4e79b-108">Syntax</span></span>  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e79b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4e79b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4e79b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e79b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e79b-111">属性</span><span class="sxs-lookup"><span data-stu-id="4e79b-111">Attributes</span></span>  
  
|<span data-ttu-id="4e79b-112">属性</span><span class="sxs-lookup"><span data-stu-id="4e79b-112">Attribute</span></span>|<span data-ttu-id="4e79b-113">説明</span><span class="sxs-lookup"><span data-stu-id="4e79b-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="4e79b-114">ASP.NET では、CPU ごとの同時要求の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e79b-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="4e79b-115">アプリケーション プールの各 CPU の実行できる同時スレッドの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e79b-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="4e79b-116">これにより、CPU あたりの要求を処理するために使用できるマネージ スレッドの数を制限するため、ASP.NET の同時実行を制御する別の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e79b-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="4e79b-117">既定では、この設定は 0 で、ASP.NET で制限しないこと、CPU ごとに作成できるスレッドの数が、CLR スレッド プールでは、作成できるスレッドの数によっても制限は。</span><span class="sxs-lookup"><span data-stu-id="4e79b-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="4e79b-118">ASP.NET の 1 つのプロセスでキューに追加される要求の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e79b-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="4e79b-119">2 つまたは複数の ASP.NET アプリケーションは、1 つのアプリケーション プールで実行すると、アプリケーション プール内の任意のアプリケーションに対する要求の累積的なセットは、この設定の対象です。</span><span class="sxs-lookup"><span data-stu-id="4e79b-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e79b-120">子要素</span><span class="sxs-lookup"><span data-stu-id="4e79b-120">Child Elements</span></span>  
 <span data-ttu-id="4e79b-121">なし。</span><span class="sxs-lookup"><span data-stu-id="4e79b-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e79b-122">親要素</span><span class="sxs-lookup"><span data-stu-id="4e79b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4e79b-123">要素</span><span class="sxs-lookup"><span data-stu-id="4e79b-123">Element</span></span>|<span data-ttu-id="4e79b-124">説明</span><span class="sxs-lookup"><span data-stu-id="4e79b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e79b-125">\<system.web ></span><span class="sxs-lookup"><span data-stu-id="4e79b-125">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="4e79b-126">ASP.NET がホスト アプリケーションと対話する方法についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="4e79b-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e79b-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="4e79b-127">Remarks</span></span>  
 <span data-ttu-id="4e79b-128">実行するときに[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]統合モードで以降のバージョンがこの要素を組み合わせて、アプリケーションが IIS アプリケーション プールでホストされている場合に、ASP.NET がスレッドとキューの要求を管理する方法を設定できますか。</span><span class="sxs-lookup"><span data-stu-id="4e79b-128">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="4e79b-129">IIS 6 を実行するかを実行する[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]クラシック モードまたは ISAPI モードでは、これらの設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="4e79b-129">If you run IIS 6 or you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
 <span data-ttu-id="4e79b-130">`applicationPool`設定、.NET Framework の特定のバージョンで実行されるすべてのアプリケーション プールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4e79b-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="4e79b-131">設定は、aspnet.config ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4e79b-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="4e79b-132">このファイルのバージョン 2.0 と 4.0 の .NET Framework のバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="4e79b-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="4e79b-133">(バージョン 3.0 および .NET framework 3.5 に、バージョン 2.0 ではある aspnet.config ファイルが共有)。</span><span class="sxs-lookup"><span data-stu-id="4e79b-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4e79b-134">実行する場合[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]で[!INCLUDE[win7](../../../../../includes/win7-md.md)]、すべてのアプリケーション プールの別の aspnet.config ファイルを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="4e79b-134">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] on [!INCLUDE[win7](../../../../../includes/win7-md.md)], you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="4e79b-135">これにより、各アプリケーション プールのスレッドのパフォーマンスを調整できます。</span><span class="sxs-lookup"><span data-stu-id="4e79b-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
 <span data-ttu-id="4e79b-136">`maxConcurrentRequestsPerCPU`設定、「5000」の既定の設定、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]が実際には、CPU あたり 5000 以上の要求がない限り、要求の調整をオフに効果的が ASP.NET によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="4e79b-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="4e79b-137">既定の設定は、CPU あたりの同時実行を自動的に管理する CLR のスレッド プールに代わりに依存します。</span><span class="sxs-lookup"><span data-stu-id="4e79b-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="4e79b-138">非同期要求の処理の広範な使用を構成する、またはネットワーク I/O でブロックされている多くの実行時間の長い要求のアプリケーションにメリットが増加の既定の制限から、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4e79b-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="4e79b-139">設定`maxConcurrentRequestsPerCPU`ASP.NET 要求を処理するためのマネージ スレッドの使用を解除します。 0 にします。</span><span class="sxs-lookup"><span data-stu-id="4e79b-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="4e79b-140">アプリケーションを IIS アプリケーション プールで実行すると、IIS の I/O スレッドで常に要求とスレッドの IIS 設定によって同時実行を調整するためです。</span><span class="sxs-lookup"><span data-stu-id="4e79b-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
 <span data-ttu-id="4e79b-141">`requestQueueLimit`設定と同じように機能、`requestQueueLimit`の属性、 [processModel](https://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d)要素で、ASP.NET アプリケーションの Web.config ファイルで設定されます。</span><span class="sxs-lookup"><span data-stu-id="4e79b-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="4e79b-142">ただし、 `requestQueueLimit` aspnet.config ファイルの設定のオーバーライド、 `requestQueueLimit` Web.config ファイルで設定します。</span><span class="sxs-lookup"><span data-stu-id="4e79b-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="4e79b-143">つまり、両方の属性が設定されている場合 (既定では、これが true)、 `requestQueueLimit` aspnet.config ファイルで設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="4e79b-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e79b-144">例</span><span class="sxs-lookup"><span data-stu-id="4e79b-144">Example</span></span>  
 <span data-ttu-id="4e79b-145">次の例では、次の状況で aspnet.config ファイルに ASP.NET プロセス全体の動作を構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4e79b-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
-   <span data-ttu-id="4e79b-146">アプリケーションがホストされている、[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]アプリケーション プール。</span><span class="sxs-lookup"><span data-stu-id="4e79b-146">The application is hosted in an [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] application pool.</span></span>  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] <span data-ttu-id="4e79b-147">統合モードで実行されています。</span><span class="sxs-lookup"><span data-stu-id="4e79b-147">is running in Integrated mode.</span></span>  
  
-   <span data-ttu-id="4e79b-148">アプリケーションを使用して、[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="4e79b-148">The application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span>  
  
 <span data-ttu-id="4e79b-149">値の例では、既定値です。</span><span class="sxs-lookup"><span data-stu-id="4e79b-149">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="4e79b-150">要素情報</span><span class="sxs-lookup"><span data-stu-id="4e79b-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4e79b-151">名前空間</span><span class="sxs-lookup"><span data-stu-id="4e79b-151">Namespace</span></span>||  
|<span data-ttu-id="4e79b-152">スキーマ名</span><span class="sxs-lookup"><span data-stu-id="4e79b-152">Schema Name</span></span>||  
|<span data-ttu-id="4e79b-153">検証ファイル</span><span class="sxs-lookup"><span data-stu-id="4e79b-153">Validation File</span></span>||  
|<span data-ttu-id="4e79b-154">空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4e79b-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="4e79b-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e79b-155">See also</span></span>
- [<span data-ttu-id="4e79b-156">\<system.web> 要素 (Web 設定)</span><span class="sxs-lookup"><span data-stu-id="4e79b-156">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)

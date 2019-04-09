---
title: <system.web> 要素 (Web 設定)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: 50566422c5e28585e93171c991144cf12a6866eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131951"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="102f8-102">\<system.web > 要素 (Web 設定)</span><span class="sxs-lookup"><span data-stu-id="102f8-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="102f8-103">ASP.NET ホスト レイヤーがプロセス全体の動作を管理する方法についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="102f8-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
 <span data-ttu-id="102f8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="102f8-104">\<configuration></span></span>  
<span data-ttu-id="102f8-105">\<system.web > 要素 (Web 設定)</span><span class="sxs-lookup"><span data-stu-id="102f8-105">\<system.web> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="102f8-106">構文</span><span class="sxs-lookup"><span data-stu-id="102f8-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="102f8-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="102f8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="102f8-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="102f8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="102f8-109">属性</span><span class="sxs-lookup"><span data-stu-id="102f8-109">Attributes</span></span>  
 <span data-ttu-id="102f8-110">なし。</span><span class="sxs-lookup"><span data-stu-id="102f8-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="102f8-111">子要素</span><span class="sxs-lookup"><span data-stu-id="102f8-111">Child Elements</span></span>  
  
|<span data-ttu-id="102f8-112">要素</span><span class="sxs-lookup"><span data-stu-id="102f8-112">Element</span></span>|<span data-ttu-id="102f8-113">説明</span><span class="sxs-lookup"><span data-stu-id="102f8-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="102f8-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="102f8-114">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="102f8-115">Aspnet.config ファイルには、IIS アプリケーション プールの構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="102f8-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="102f8-116">親要素</span><span class="sxs-lookup"><span data-stu-id="102f8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="102f8-117">要素</span><span class="sxs-lookup"><span data-stu-id="102f8-117">Element</span></span>|<span data-ttu-id="102f8-118">説明</span><span class="sxs-lookup"><span data-stu-id="102f8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="102f8-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="102f8-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="102f8-120">共通言語ランタイムおよび [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="102f8-120">Specifies the root element in every configuration file that is used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="102f8-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="102f8-121">Remarks</span></span>  
 <span data-ttu-id="102f8-122">`system.web`要素とその子`applicationPool`に要素が追加された、[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]の[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="102f8-122">The `system.web` element and its child `applicationPool` element were added to the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] as of [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="102f8-123">実行すると[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]も以降のバージョンの統合モードでは、この要素を組み合わせて、ASP.NET スレッドを管理する方法と、ASP.NET が IIS アプリケーション プールでホストされている場合に要求をキューにする方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="102f8-123">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="102f8-124">実行する場合[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]以降のバージョン、クラシックまたは ISAPI のモードでこれらの設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="102f8-124">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="102f8-125">例</span><span class="sxs-lookup"><span data-stu-id="102f8-125">Example</span></span>  
 <span data-ttu-id="102f8-126">次の例では、ASP.NET が IIS アプリケーション プールでホストされている場合は、aspnet.config ファイルに ASP.NET プロセス全体の動作を構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="102f8-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="102f8-127">この例では統合で IIS が実行されているモードと、アプリケーションを使用している、[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="102f8-127">The example assumes that IIS is running in Integrated mode and that the application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span> <span data-ttu-id="102f8-128">バージョンでこの動作は発生しません、[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]よりも前、[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="102f8-128">This behavior does not occur in versions of the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] earlier than the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="102f8-129">値の例では、既定値です。</span><span class="sxs-lookup"><span data-stu-id="102f8-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="102f8-130">要素情報</span><span class="sxs-lookup"><span data-stu-id="102f8-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="102f8-131">名前空間</span><span class="sxs-lookup"><span data-stu-id="102f8-131">Namespace</span></span>||  
|<span data-ttu-id="102f8-132">スキーマ名</span><span class="sxs-lookup"><span data-stu-id="102f8-132">Schema Name</span></span>||  
|<span data-ttu-id="102f8-133">検証ファイル</span><span class="sxs-lookup"><span data-stu-id="102f8-133">Validation File</span></span>||  
|<span data-ttu-id="102f8-134">空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="102f8-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="102f8-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="102f8-135">See also</span></span>

- [<span data-ttu-id="102f8-136">\<applicationPool > 要素 (Web 設定)</span><span class="sxs-lookup"><span data-stu-id="102f8-136">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)

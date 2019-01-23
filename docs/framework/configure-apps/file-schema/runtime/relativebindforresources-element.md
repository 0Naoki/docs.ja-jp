---
title: '&lt;relativeBindForResources&gt;要素'
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3aa3ca9c9d0e64b2290b503f09b83140b4d029b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534797"
---
# <a name="ltrelativebindforresourcesgt-element"></a><span data-ttu-id="04c2e-102">&lt;relativeBindForResources&gt;要素</span><span class="sxs-lookup"><span data-stu-id="04c2e-102">&lt;relativeBindForResources&gt; Element</span></span>
<span data-ttu-id="04c2e-103">サテライト アセンブリのプローブを最適化します。</span><span class="sxs-lookup"><span data-stu-id="04c2e-103">Optimizes the probe for satellite assemblies.</span></span>  
  
 <span data-ttu-id="04c2e-104">\<configuration > 要素</span><span class="sxs-lookup"><span data-stu-id="04c2e-104">\<configuration> Element</span></span>  
<span data-ttu-id="04c2e-105">\<ランタイム > 要素</span><span class="sxs-lookup"><span data-stu-id="04c2e-105">\<runtime> Element</span></span>  
<span data-ttu-id="04c2e-106">\<relativeBindForResources > 要素</span><span class="sxs-lookup"><span data-stu-id="04c2e-106">\<relativeBindForResources> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c2e-107">構文</span><span class="sxs-lookup"><span data-stu-id="04c2e-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04c2e-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="04c2e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="04c2e-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="04c2e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04c2e-110">属性</span><span class="sxs-lookup"><span data-stu-id="04c2e-110">Attributes</span></span>  
  
|<span data-ttu-id="04c2e-111">属性</span><span class="sxs-lookup"><span data-stu-id="04c2e-111">Attribute</span></span>|<span data-ttu-id="04c2e-112">説明</span><span class="sxs-lookup"><span data-stu-id="04c2e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="04c2e-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="04c2e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="04c2e-114">共通言語ランタイムがサテライト アセンブリのプローブを最適化するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="04c2e-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="04c2e-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="04c2e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="04c2e-116">値</span><span class="sxs-lookup"><span data-stu-id="04c2e-116">Value</span></span>|<span data-ttu-id="04c2e-117">説明</span><span class="sxs-lookup"><span data-stu-id="04c2e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="04c2e-118">ランタイムでは、サテライト アセンブリのプローブは最適化されません。</span><span class="sxs-lookup"><span data-stu-id="04c2e-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="04c2e-119">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="04c2e-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="04c2e-120">ランタイムは、サテライト アセンブリのプローブを最適化します。</span><span class="sxs-lookup"><span data-stu-id="04c2e-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04c2e-121">子要素</span><span class="sxs-lookup"><span data-stu-id="04c2e-121">Child Elements</span></span>  
 <span data-ttu-id="04c2e-122">なし。</span><span class="sxs-lookup"><span data-stu-id="04c2e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04c2e-123">親要素</span><span class="sxs-lookup"><span data-stu-id="04c2e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="04c2e-124">要素</span><span class="sxs-lookup"><span data-stu-id="04c2e-124">Element</span></span>|<span data-ttu-id="04c2e-125">説明</span><span class="sxs-lookup"><span data-stu-id="04c2e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="04c2e-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="04c2e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="04c2e-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="04c2e-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04c2e-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="04c2e-128">Remarks</span></span>  
 <span data-ttu-id="04c2e-129">記載されているのリソースについては、Resource Manager が一般に、プローブ、 [Packaging and Deploying Resources](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="04c2e-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="04c2e-130">つまり、リソース マネージャーは、リソースの特定のローカライズされたバージョンのプローブ、ときに、可能性があります、グローバル アセンブリ キャッシュ ファイルの場所、カルチャ固有のフォルダー、アプリケーションのコード ベース、クエリ Windows インストーラーでサテライト アセンブリでは、検索対象を発生させる、<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>イベント。</span><span class="sxs-lookup"><span data-stu-id="04c2e-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="04c2e-131">`<relativeBindForResources>`要素は、Resource Manager がサテライト アセンブリをプローブする方法を最適化します。</span><span class="sxs-lookup"><span data-stu-id="04c2e-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="04c2e-132">次の条件下でリソースのプローブは、パフォーマンスを向上させることできます。</span><span class="sxs-lookup"><span data-stu-id="04c2e-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
-   <span data-ttu-id="04c2e-133">ときに、サテライト アセンブリは、コード アセンブリと同じ場所にデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="04c2e-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="04c2e-134">つまり、コード アセンブリがグローバル アセンブリ キャッシュにインストールする場合、サテライト アセンブリもインストールしなければなりませんがあります。</span><span class="sxs-lookup"><span data-stu-id="04c2e-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="04c2e-135">コード アセンブリは、アプリケーションのコード ベースでインストールする場合、コード ベースのカルチャ固有のフォルダーにもこのサテライト アセンブリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04c2e-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
-   <span data-ttu-id="04c2e-136">Windows インストーラーが実行されていないまたはほとんど使用されないサテライト アセンブリのオンデマンドでインストールします。</span><span class="sxs-lookup"><span data-stu-id="04c2e-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
-   <span data-ttu-id="04c2e-137">アプリケーション コードが処理しない場合、<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>イベント。</span><span class="sxs-lookup"><span data-stu-id="04c2e-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="04c2e-138">設定、`enabled`の属性、`<relativeBindForResources>`要素を`true`サテライト アセンブリの次のように Resource Manager のプローブを最適化します。</span><span class="sxs-lookup"><span data-stu-id="04c2e-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
-   <span data-ttu-id="04c2e-139">親コード アセンブリの場所を使って、サテライト アセンブリをプローブします。</span><span class="sxs-lookup"><span data-stu-id="04c2e-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
-   <span data-ttu-id="04c2e-140">Windows インストーラーをサテライト アセンブリに照会しません。</span><span class="sxs-lookup"><span data-stu-id="04c2e-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
-   <span data-ttu-id="04c2e-141">発生させない、<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>イベント。</span><span class="sxs-lookup"><span data-stu-id="04c2e-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04c2e-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="04c2e-142">See also</span></span>
- [<span data-ttu-id="04c2e-143">リソースのパッケージ化と配置</span><span class="sxs-lookup"><span data-stu-id="04c2e-143">Packaging and Deploying Resources</span></span>](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="04c2e-144">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="04c2e-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="04c2e-145">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="04c2e-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

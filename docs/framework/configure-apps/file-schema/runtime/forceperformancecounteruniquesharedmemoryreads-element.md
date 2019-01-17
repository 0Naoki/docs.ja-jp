---
title: '&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt;要素'
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b53debd8f71bddb353ff7709decf0142c339e5d
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612700"
---
# <a name="ltforceperformancecounteruniquesharedmemoryreadsgt-element"></a><span data-ttu-id="a62b2-102">&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt;要素</span><span class="sxs-lookup"><span data-stu-id="a62b2-102">&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; Element</span></span>
<span data-ttu-id="a62b2-103">PerfCounter.dll が、.NET Framework バージョン 1.1 のアプリケーションの CategoryOptions レジストリ設定を使用してするかどうかを指定して、カテゴリ別の共有メモリとグローバル メモリのどちらからパフォーマンス カウンター データを読み込むかを決定します。</span><span class="sxs-lookup"><span data-stu-id="a62b2-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
 <span data-ttu-id="a62b2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a62b2-104">\<configuration></span></span>  
<span data-ttu-id="a62b2-105">\<ランタイム ></span><span class="sxs-lookup"><span data-stu-id="a62b2-105">\<runtime></span></span>  
<span data-ttu-id="a62b2-106">\<forcePerformanceCounterUniqueSharedMemoryReads ></span><span class="sxs-lookup"><span data-stu-id="a62b2-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a62b2-107">構文</span><span class="sxs-lookup"><span data-stu-id="a62b2-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a62b2-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a62b2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a62b2-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a62b2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a62b2-110">属性</span><span class="sxs-lookup"><span data-stu-id="a62b2-110">Attributes</span></span>  
  
|<span data-ttu-id="a62b2-111">属性</span><span class="sxs-lookup"><span data-stu-id="a62b2-111">Attribute</span></span>|<span data-ttu-id="a62b2-112">説明</span><span class="sxs-lookup"><span data-stu-id="a62b2-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a62b2-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="a62b2-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a62b2-114">どちらがカテゴリ別の共有メモリとグローバル メモリからパフォーマンス カウンター データを読み込むかどうかを判断する CategoryOptions レジストリ設定を使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a62b2-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a62b2-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="a62b2-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a62b2-116">値</span><span class="sxs-lookup"><span data-stu-id="a62b2-116">Value</span></span>|<span data-ttu-id="a62b2-117">説明</span><span class="sxs-lookup"><span data-stu-id="a62b2-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a62b2-118">どちらを使用しません、CategoryOptions レジストリ設定ではこれが既定値。</span><span class="sxs-lookup"><span data-stu-id="a62b2-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="a62b2-119">どちらでは、CategoryOptions レジストリ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="a62b2-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a62b2-120">子要素</span><span class="sxs-lookup"><span data-stu-id="a62b2-120">Child Elements</span></span>  
 <span data-ttu-id="a62b2-121">なし。</span><span class="sxs-lookup"><span data-stu-id="a62b2-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a62b2-122">親要素</span><span class="sxs-lookup"><span data-stu-id="a62b2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a62b2-123">要素</span><span class="sxs-lookup"><span data-stu-id="a62b2-123">Element</span></span>|<span data-ttu-id="a62b2-124">説明</span><span class="sxs-lookup"><span data-stu-id="a62b2-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a62b2-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a62b2-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a62b2-126">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a62b2-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a62b2-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="a62b2-127">Remarks</span></span>  
 <span data-ttu-id="a62b2-128">前に .NET Framework のバージョンでは、 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]、読み込まれているどちらのバージョンは、プロセスに読み込まれたランタイムに対応します。</span><span class="sxs-lookup"><span data-stu-id="a62b2-128">In versions of the .NET Framework before the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="a62b2-129">かどうか、コンピューターが両方の .NET Framework version 1.1 と[!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)]、インストールされている .NET Framework 1.1 アプリケーションはどちらの .NET Framework 1.1 バージョンを読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="a62b2-129">If a computer had both the .NET Framework version 1.1 and the [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="a62b2-130">以降では、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]どちらのインストールされている最新のバージョンが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="a62b2-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="a62b2-131">つまり、.NET Framework 1.1 アプリケーションが読み込むこと、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]バージョンどちらの場合、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]がコンピューターにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="a62b2-131">This means that a .NET Framework 1.1 application will load the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] version of PerfCounter.dll if the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] is installed on the computer.</span></span>  
  
 <span data-ttu-id="a62b2-132">以降では、 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]、パフォーマンス カウンターを使用するときにどちらがカテゴリ別の共有メモリまたはグローバル共有メモリから読み取る必要があります、かどうかを確認するには、各プロバイダーの CategoryOptions レジストリ エントリを確認します。</span><span class="sxs-lookup"><span data-stu-id="a62b2-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="a62b2-133">カテゴリに固有の共有メモリの対応でないため、.NET Framework 1.1 のどちらがレジストリのエントリを読み取れませんグローバル共有メモリから常に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a62b2-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="a62b2-134">旧バージョンとの互換性のため、 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] .NET Framework 1.1 アプリケーションの実行時にどちらが CategoryOptions レジストリ エントリを確認できません。</span><span class="sxs-lookup"><span data-stu-id="a62b2-134">For backward compatibility, the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="a62b2-135">単に、.NET Framework 1.1 のどちらの場合と同様のグローバル共有メモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="a62b2-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="a62b2-136">ただし、指示すること、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]どちらを有効にすると、レジストリ設定を確認する、`<forcePerformanceCounterUniqueSharedMemoryReads>`要素。</span><span class="sxs-lookup"><span data-stu-id="a62b2-136">However, you can instruct the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a62b2-137">有効にすると、`<forcePerformanceCounterUniqueSharedMemoryReads>`要素がカテゴリ別の共有メモリが使用されることを保証していません。</span><span class="sxs-lookup"><span data-stu-id="a62b2-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="a62b2-138">設定を有効になっている`true`CategoryOptions レジストリ設定を参照するどちらでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="a62b2-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="a62b2-139">CategoryOptions の既定の設定は、カテゴリ固有の共有メモリを使用することです。ただし、グローバル共有メモリを使用することを示す CategoryOptions を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a62b2-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="a62b2-140">CategoryOptions 設定を格納するレジストリ キーは hkey_local_machine \system\currentcontrolset\services\\< categoryName\>\Performance します。</span><span class="sxs-lookup"><span data-stu-id="a62b2-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="a62b2-141">既定では、CategoryOptions は設定を 3 にどちら カテゴリ固有の共有メモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="a62b2-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="a62b2-142">CategoryOptions が 0 に設定されている場合、どちらはグローバル共有メモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="a62b2-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="a62b2-143">作成中のインスタンスの名前は再利用されるインスタンスと同じ場合にのみ、インスタンス データを再利用されます。</span><span class="sxs-lookup"><span data-stu-id="a62b2-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="a62b2-144">すべてのバージョンは、カテゴリに書き込みを可能になります。</span><span class="sxs-lookup"><span data-stu-id="a62b2-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="a62b2-145">CategoryOptions が 1 に設定されている場合は、グローバル共有メモリが使用されますが、カテゴリ名が再利用されるカテゴリと同じ長さである場合は、インスタンス データを再利用されることができます。</span><span class="sxs-lookup"><span data-stu-id="a62b2-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="a62b2-146">0 と 1 の設定は、メモリ リークおよびパフォーマンス カウンターのメモリの不足につながります。</span><span class="sxs-lookup"><span data-stu-id="a62b2-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a62b2-147">例</span><span class="sxs-lookup"><span data-stu-id="a62b2-147">Example</span></span>  
 <span data-ttu-id="a62b2-148">次の例では、どちらがカテゴリ別の共有メモリを使用するかどうかを判断する CategoryOptions レジストリ エントリを参照する必要がありますを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a62b2-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a62b2-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="a62b2-149">See Also</span></span>  
- [<span data-ttu-id="a62b2-150">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a62b2-150">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="a62b2-151">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="a62b2-151">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

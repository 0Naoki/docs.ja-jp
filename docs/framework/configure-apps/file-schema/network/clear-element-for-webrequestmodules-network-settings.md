---
title: '&lt;オフ&gt;webRequestModules (ネットワーク設定) の要素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2b313aa2481b1257715ac4dbc6d452e2120f4726
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2018
ms.locfileid: "48838332"
---
# <a name="ltcleargt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="c0ff3-102">&lt;オフ&gt;webRequestModules (ネットワーク設定) の要素</span><span class="sxs-lookup"><span data-stu-id="c0ff3-102">&lt;clear&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="c0ff3-103">アプリケーションから登録済みのすべての Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="c0ff3-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="c0ff3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c0ff3-104">\<configuration></span></span>  
<span data-ttu-id="c0ff3-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="c0ff3-105">\<system.net></span></span>  
<span data-ttu-id="c0ff3-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="c0ff3-106">\<webRequestModules></span></span>  
<span data-ttu-id="c0ff3-107">\<クリア ></span><span class="sxs-lookup"><span data-stu-id="c0ff3-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0ff3-108">構文</span><span class="sxs-lookup"><span data-stu-id="c0ff3-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0ff3-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c0ff3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c0ff3-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0ff3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0ff3-111">属性</span><span class="sxs-lookup"><span data-stu-id="c0ff3-111">Attributes</span></span>  
 <span data-ttu-id="c0ff3-112">なし。</span><span class="sxs-lookup"><span data-stu-id="c0ff3-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c0ff3-113">子要素</span><span class="sxs-lookup"><span data-stu-id="c0ff3-113">Child Elements</span></span>  
 <span data-ttu-id="c0ff3-114">なし。</span><span class="sxs-lookup"><span data-stu-id="c0ff3-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0ff3-115">親要素</span><span class="sxs-lookup"><span data-stu-id="c0ff3-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c0ff3-116">**要素**</span><span class="sxs-lookup"><span data-stu-id="c0ff3-116">**Element**</span></span>|<span data-ttu-id="c0ff3-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="c0ff3-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c0ff3-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="c0ff3-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="c0ff3-119">使用してネットワークのホストから情報を要求するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0ff3-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0ff3-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0ff3-120">Remarks</span></span>  
 <span data-ttu-id="c0ff3-121">`clear`要素は、構成ファイルで、または構成階層のより高いレベルで既に定義されているすべての登録済みの Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="c0ff3-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c0ff3-122">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="c0ff3-122">Configuration Files</span></span>  
 <span data-ttu-id="c0ff3-123">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0ff3-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0ff3-124">例</span><span class="sxs-lookup"><span data-stu-id="c0ff3-124">Example</span></span>  
 <span data-ttu-id="c0ff3-125">次の例では、すべての Web 要求モジュールを削除し、http Web 要求モジュールを登録します。</span><span class="sxs-lookup"><span data-stu-id="c0ff3-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0ff3-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0ff3-126">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="c0ff3-127">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="c0ff3-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

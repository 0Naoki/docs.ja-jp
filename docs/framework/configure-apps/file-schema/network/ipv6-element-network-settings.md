---
title: '&lt;ipv6&gt;要素 (ネットワーク設定)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 5b1707d7490de07520603f6fdf6d1ee1a44ffba7
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2018
ms.locfileid: "48840488"
---
# <a name="ltipv6gt-element-network-settings"></a><span data-ttu-id="4f78e-102">&lt;ipv6&gt;要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="4f78e-102">&lt;ipv6&gt; Element (Network Settings)</span></span>
<span data-ttu-id="4f78e-103">により、インターネット プロトコル バージョン 6 (IPv6) の廃止されたメンバーからの応答、<xref:System.Net.Dns>クラス。</span><span class="sxs-lookup"><span data-stu-id="4f78e-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
 <span data-ttu-id="4f78e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4f78e-104">\<configuration></span></span>  
<span data-ttu-id="4f78e-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="4f78e-105">\<system.net></span></span>  
<span data-ttu-id="4f78e-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="4f78e-106">\<settings></span></span>  
<span data-ttu-id="4f78e-107">\<ipv6 ></span><span class="sxs-lookup"><span data-stu-id="4f78e-107">\<ipv6></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f78e-108">構文</span><span class="sxs-lookup"><span data-stu-id="4f78e-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f78e-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4f78e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4f78e-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f78e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f78e-111">属性</span><span class="sxs-lookup"><span data-stu-id="4f78e-111">Attributes</span></span>  
  
|<span data-ttu-id="4f78e-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="4f78e-112">**Attribute**</span></span>|<span data-ttu-id="4f78e-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="4f78e-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="4f78e-114">指定するかどうかのメンバー、<xref:System.Net.Dns>クラスは、インターネット プロトコル バージョン 6 (IPv6) アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="4f78e-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="4f78e-115">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="4f78e-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f78e-116">子要素</span><span class="sxs-lookup"><span data-stu-id="4f78e-116">Child Elements</span></span>  
 <span data-ttu-id="4f78e-117">なし。</span><span class="sxs-lookup"><span data-stu-id="4f78e-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f78e-118">親要素</span><span class="sxs-lookup"><span data-stu-id="4f78e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4f78e-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="4f78e-119">**Element**</span></span>|<span data-ttu-id="4f78e-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="4f78e-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4f78e-121">settings</span><span class="sxs-lookup"><span data-stu-id="4f78e-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="4f78e-122"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f78e-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f78e-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="4f78e-123">Remarks</span></span>  
 <span data-ttu-id="4f78e-124">この設定により、IPv6 のサポートの廃止されたメンバーの<xref:System.Net.Dns>クラス: <xref:System.Net.Dns.BeginGetHostByName%2A>、 <xref:System.Net.Dns.BeginResolve%2A>、 <xref:System.Net.Dns.EndGetHostByName%2A>、 <xref:System.Net.Dns.EndResolve%2A>、 <xref:System.Net.Dns.GetHostByAddress%2A>、 <xref:System.Net.Dns.GetHostByName%2A>、および<xref:System.Net.Dns.Resolve%2A>します。</span><span class="sxs-lookup"><span data-stu-id="4f78e-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="4f78e-125">他のメンバー、<xref:System.Net?displayProperty=nameWithType>名前空間、IPv6 アドレスが表示されるオペレーティング システムで IPv6 が有効になっている場合。</span><span class="sxs-lookup"><span data-stu-id="4f78e-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4f78e-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="4f78e-126">Configuration Files</span></span>  
 <span data-ttu-id="4f78e-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f78e-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f78e-128">例</span><span class="sxs-lookup"><span data-stu-id="4f78e-128">Example</span></span>  
 <span data-ttu-id="4f78e-129">次の例の IPv6 サポートを有効にする方法を示しています、<xref:System.Net.Dns>クラス。</span><span class="sxs-lookup"><span data-stu-id="4f78e-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f78e-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f78e-130">See Also</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 <xref:System.Net.Dns?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="4f78e-131">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="4f78e-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

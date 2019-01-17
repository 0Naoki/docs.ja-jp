---
title: '&lt;defaultProxy&gt;要素 (ネットワーク設定)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 54185c7cca734ced166fbe0a52b96214321d4469
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200510"
---
# <a name="ltdefaultproxygt-element-network-settings"></a><span data-ttu-id="35416-102">&lt;defaultProxy&gt;要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="35416-102">&lt;defaultProxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="35416-103">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="35416-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
 <span data-ttu-id="35416-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="35416-104">\<configuration></span></span>  
<span data-ttu-id="35416-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="35416-105">\<system.net></span></span>  
<span data-ttu-id="35416-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="35416-106">\<defaultProxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35416-107">構文</span><span class="sxs-lookup"><span data-stu-id="35416-107">Syntax</span></span>  
  
```xml  
      <defaultProxy  
        enabled="true|false"  
        useDefaultCredentials="true|false">  
           <bypasslist> … </bypasslist>  
           <proxy> … </proxy>  
           <module> … </module>  
      </defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35416-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="35416-108">Attributes and Elements</span></span>  
 <span data-ttu-id="35416-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="35416-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35416-110">属性</span><span class="sxs-lookup"><span data-stu-id="35416-110">Attributes</span></span>  
  
|<span data-ttu-id="35416-111">**要素**</span><span class="sxs-lookup"><span data-stu-id="35416-111">**Element**</span></span>|<span data-ttu-id="35416-112">**説明**</span><span class="sxs-lookup"><span data-stu-id="35416-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="35416-113">Web プロキシが使用されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="35416-113">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="35416-114">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="35416-114">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="35416-115">このホストに対する既定の資格情報が Web プロキシにアクセスするために使用されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="35416-115">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="35416-116">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="35416-116">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35416-117">子要素</span><span class="sxs-lookup"><span data-stu-id="35416-117">Child Elements</span></span>  
  
|<span data-ttu-id="35416-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="35416-118">**Element**</span></span>|<span data-ttu-id="35416-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="35416-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="35416-120">bypasslist</span><span class="sxs-lookup"><span data-stu-id="35416-120">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="35416-121">プロキシを使用しないアドレスを記述する一連の正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="35416-121">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="35416-122">module</span><span class="sxs-lookup"><span data-stu-id="35416-122">module</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)|<span data-ttu-id="35416-123">新しいプロキシ モジュールをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="35416-123">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="35416-124">proxy</span><span class="sxs-lookup"><span data-stu-id="35416-124">proxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md)|<span data-ttu-id="35416-125">プロキシ サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="35416-125">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="35416-126">親要素</span><span class="sxs-lookup"><span data-stu-id="35416-126">Parent Elements</span></span>  
  
|<span data-ttu-id="35416-127">**要素**</span><span class="sxs-lookup"><span data-stu-id="35416-127">**Element**</span></span>|<span data-ttu-id="35416-128">**説明**</span><span class="sxs-lookup"><span data-stu-id="35416-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="35416-129">system.net</span><span class="sxs-lookup"><span data-stu-id="35416-129">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="35416-130">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="35416-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35416-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="35416-131">Remarks</span></span>  
 <span data-ttu-id="35416-132">defaultProxy 要素が空の場合、Internet Explorer のプロキシ設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="35416-132">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="35416-133">この動作は、.NET Framework Version 1.1 とは異なります。</span><span class="sxs-lookup"><span data-stu-id="35416-133">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="35416-134">場合、例外がスローされます、[モジュール](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)要素がパブリックでない型を指定します、種類がから派生していない、<xref:System.Net.IWebProxy>クラスでは、このオブジェクトの既定のコンス トラクターから例外が発生しました、または例外が発生しました、システム指定の既定のプロキシを取得しています。</span><span class="sxs-lookup"><span data-stu-id="35416-134">An exception is thrown if the [module](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the default constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="35416-135">例外の <xref:System.Exception.InnerException%2A> プロパティに、このエラーの根本原因に関する詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="35416-135">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="35416-136">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="35416-136">Configuration Files</span></span>  
 <span data-ttu-id="35416-137">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="35416-137">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35416-138">例</span><span class="sxs-lookup"><span data-stu-id="35416-138">Example</span></span>  
 <span data-ttu-id="35416-139">次の例は、既定値を Internet Explorer のプロキシを使用して、プロキシ アドレスを指定し、ローカル アクセスおよび contoso.com のプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="35416-139">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="35416-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="35416-140">See Also</span></span>  
- <xref:System.Net.WebProxy?displayProperty=nameWithType>  
- [<span data-ttu-id="35416-141">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="35416-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

---
title: connectionManagement の &lt;remove&gt; 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
ms.openlocfilehash: 03cac1523c0fce268c2df8d04134c0d5e88830e2
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181554"
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="7f3b4-102">connectionManagement の &lt;remove&gt; 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="7f3b4-102">&lt;remove&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="7f3b4-103">接続管理リストから IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="7f3b4-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="7f3b4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7f3b4-104">\<configuration></span></span>  
<span data-ttu-id="7f3b4-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="7f3b4-105">\<system.net></span></span>  
<span data-ttu-id="7f3b4-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="7f3b4-106">\<connectionManagement></span></span>  
<span data-ttu-id="7f3b4-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="7f3b4-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f3b4-108">構文</span><span class="sxs-lookup"><span data-stu-id="7f3b4-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f3b4-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7f3b4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7f3b4-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f3b4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f3b4-111">属性</span><span class="sxs-lookup"><span data-stu-id="7f3b4-111">Attributes</span></span>  
  
|<span data-ttu-id="7f3b4-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="7f3b4-112">**Attribute**</span></span>|<span data-ttu-id="7f3b4-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="7f3b4-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="7f3b4-114">IP アドレスまたは DNS 名。</span><span class="sxs-lookup"><span data-stu-id="7f3b4-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f3b4-115">子要素</span><span class="sxs-lookup"><span data-stu-id="7f3b4-115">Child Elements</span></span>  
 <span data-ttu-id="7f3b4-116">なし。</span><span class="sxs-lookup"><span data-stu-id="7f3b4-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f3b4-117">親要素</span><span class="sxs-lookup"><span data-stu-id="7f3b4-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7f3b4-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="7f3b4-118">**Element**</span></span>|<span data-ttu-id="7f3b4-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="7f3b4-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7f3b4-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="7f3b4-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="7f3b4-121">ネットワーク ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f3b4-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f3b4-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="7f3b4-122">Remarks</span></span>  
 <span data-ttu-id="7f3b4-123">`remove`要素が指定されたサーバーの接続管理リスト エントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="7f3b4-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="7f3b4-124">値、`address`属性が有効な IP アドレスまたはホスト名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f3b4-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7f3b4-125">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="7f3b4-125">Configuration Files</span></span>  
 <span data-ttu-id="7f3b4-126">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f3b4-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f3b4-127">例</span><span class="sxs-lookup"><span data-stu-id="7f3b4-127">Example</span></span>  
 <span data-ttu-id="7f3b4-128">次の例は、サーバーの接続管理リスト エントリを削除します。`www.adventure-works.com`され、サーバーに 4 つの接続を使用するアプリケーションを構成して、`www.contoso.com`とその他のすべてのサーバーに 2 つの接続。</span><span class="sxs-lookup"><span data-stu-id="7f3b4-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f3b4-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f3b4-129">See Also</span></span>  
- <xref:System.Net.ServicePoint>  
- <xref:System.Net.ServicePointManager>  
- [<span data-ttu-id="7f3b4-130">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="7f3b4-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

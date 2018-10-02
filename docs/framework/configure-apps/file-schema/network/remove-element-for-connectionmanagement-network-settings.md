---
title: '&lt;削除&gt;connectionManagement (ネットワーク設定) の要素'
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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d249cc412a1638e62b57b4976adc23fdf8f36e80
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48024585"
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="b7bde-102">&lt;削除&gt;connectionManagement (ネットワーク設定) の要素</span><span class="sxs-lookup"><span data-stu-id="b7bde-102">&lt;remove&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="b7bde-103">接続管理リストから IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="b7bde-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="b7bde-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b7bde-104">\<configuration></span></span>  
<span data-ttu-id="b7bde-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b7bde-105">\<system.net></span></span>  
<span data-ttu-id="b7bde-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="b7bde-106">\<connectionManagement></span></span>  
<span data-ttu-id="b7bde-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="b7bde-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7bde-108">構文</span><span class="sxs-lookup"><span data-stu-id="b7bde-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7bde-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b7bde-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b7bde-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7bde-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7bde-111">属性</span><span class="sxs-lookup"><span data-stu-id="b7bde-111">Attributes</span></span>  
  
|<span data-ttu-id="b7bde-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="b7bde-112">**Attribute**</span></span>|<span data-ttu-id="b7bde-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="b7bde-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="b7bde-114">IP アドレスまたは DNS 名。</span><span class="sxs-lookup"><span data-stu-id="b7bde-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7bde-115">子要素</span><span class="sxs-lookup"><span data-stu-id="b7bde-115">Child Elements</span></span>  
 <span data-ttu-id="b7bde-116">なし。</span><span class="sxs-lookup"><span data-stu-id="b7bde-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7bde-117">親要素</span><span class="sxs-lookup"><span data-stu-id="b7bde-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b7bde-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="b7bde-118">**Element**</span></span>|<span data-ttu-id="b7bde-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="b7bde-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b7bde-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="b7bde-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="b7bde-121">ネットワーク ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7bde-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7bde-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7bde-122">Remarks</span></span>  
 <span data-ttu-id="b7bde-123">`remove`要素が指定されたサーバーの接続管理リスト エントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="b7bde-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="b7bde-124">値、`address`属性が有効な IP アドレスまたはホスト名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7bde-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b7bde-125">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="b7bde-125">Configuration Files</span></span>  
 <span data-ttu-id="b7bde-126">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7bde-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7bde-127">例</span><span class="sxs-lookup"><span data-stu-id="b7bde-127">Example</span></span>  
 <span data-ttu-id="b7bde-128">次の例では、server www.adventure-works.com の任意の接続管理リストのエントリを削除し、サーバー www.contoso.com への 4 つの接続とその他のすべてのサーバーに 2 つの接続を使用するアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="b7bde-128">The following example removes any connection management list entries for the server www.adventure-works.com and then configures an application to use four connections to the server www.contoso.com and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b7bde-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7bde-129">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="b7bde-130">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b7bde-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

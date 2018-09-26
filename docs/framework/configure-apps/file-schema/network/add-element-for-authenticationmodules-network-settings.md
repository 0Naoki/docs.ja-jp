---
title: '&lt;追加&gt;authenticationModules (ネットワーク設定) の要素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 4a9bcc6cd5d2bbf30f463da0a51e1bccbcd5a3f1
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "47206103"
---
# <a name="ltaddgt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="e9fbe-102">&lt;追加&gt;authenticationModules (ネットワーク設定) の要素</span><span class="sxs-lookup"><span data-stu-id="e9fbe-102">&lt;add&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="e9fbe-103">アプリケーションに認証モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="e9fbe-103">Adds an authentication module to the application.</span></span>  
  
 <span data-ttu-id="e9fbe-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e9fbe-104">\<configuration></span></span>  
<span data-ttu-id="e9fbe-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e9fbe-105">\<system.net></span></span>  
<span data-ttu-id="e9fbe-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="e9fbe-106">\<authenticationModules></span></span>  
<span data-ttu-id="e9fbe-107">\<add></span><span class="sxs-lookup"><span data-stu-id="e9fbe-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9fbe-108">構文</span><span class="sxs-lookup"><span data-stu-id="e9fbe-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9fbe-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e9fbe-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e9fbe-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9fbe-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9fbe-111">属性</span><span class="sxs-lookup"><span data-stu-id="e9fbe-111">Attributes</span></span>  
  
|<span data-ttu-id="e9fbe-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="e9fbe-112">**Attribute**</span></span>|<span data-ttu-id="e9fbe-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="e9fbe-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="e9fbe-114">完全修飾型名 (によって示される、<xref:System.Type.FullName%2A>プロパティ) とアセンブリ名 (によって示される、<xref:System.Reflection.Assembly.FullName%2A>プロパティ)、コンマで区切られました。</span><span class="sxs-lookup"><span data-stu-id="e9fbe-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9fbe-115">子要素</span><span class="sxs-lookup"><span data-stu-id="e9fbe-115">Child Elements</span></span>  
 <span data-ttu-id="e9fbe-116">なし。</span><span class="sxs-lookup"><span data-stu-id="e9fbe-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9fbe-117">親要素</span><span class="sxs-lookup"><span data-stu-id="e9fbe-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e9fbe-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="e9fbe-118">**Element**</span></span>|<span data-ttu-id="e9fbe-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="e9fbe-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e9fbe-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="e9fbe-120">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="e9fbe-121">ネットワーク要求の認証に使用されるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9fbe-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9fbe-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="e9fbe-122">Remarks</span></span>  
 <span data-ttu-id="e9fbe-123">`add`要素認証モジュールを登録済み認証モジュールの一覧の末尾に追加します。</span><span class="sxs-lookup"><span data-stu-id="e9fbe-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="e9fbe-124">認証モジュールは、一覧に追加された順序で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e9fbe-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="e9fbe-125">値、`type`属性が有効な型名と対応するアセンブリ名、コンマで区切られたにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9fbe-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e9fbe-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="e9fbe-126">Configuration Files</span></span>  
 <span data-ttu-id="e9fbe-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9fbe-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9fbe-128">例</span><span class="sxs-lookup"><span data-stu-id="e9fbe-128">Example</span></span>  
 <span data-ttu-id="e9fbe-129">次の例で、既定の認証モジュール。</span><span class="sxs-lookup"><span data-stu-id="e9fbe-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="e9fbe-130">指定したモジュールの正しい値で、バージョンおよび PublicKeyToken の値を置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9fbe-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9fbe-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9fbe-131">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="e9fbe-132">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="e9fbe-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

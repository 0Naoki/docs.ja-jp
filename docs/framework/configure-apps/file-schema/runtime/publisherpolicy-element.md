---
title: <publisherPolicy> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29932eb27bcd13876ea6982982e67341edb8e0de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076290"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="e493c-102">\<publisherPolicy > 要素</span><span class="sxs-lookup"><span data-stu-id="e493c-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="e493c-103">ランタイムが発行元ポリシーを適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e493c-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
 <span data-ttu-id="e493c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e493c-104">\<configuration></span></span>  
<span data-ttu-id="e493c-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="e493c-105">\<runtime></span></span>  
<span data-ttu-id="e493c-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="e493c-106">\<assemblyBinding></span></span>  
<span data-ttu-id="e493c-107">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="e493c-107">\<dependentAssembly></span></span>  
<span data-ttu-id="e493c-108">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="e493c-108">\<publisherPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e493c-109">構文</span><span class="sxs-lookup"><span data-stu-id="e493c-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e493c-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e493c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e493c-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e493c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e493c-112">属性</span><span class="sxs-lookup"><span data-stu-id="e493c-112">Attributes</span></span>  
  
|<span data-ttu-id="e493c-113">属性</span><span class="sxs-lookup"><span data-stu-id="e493c-113">Attribute</span></span>|<span data-ttu-id="e493c-114">説明</span><span class="sxs-lookup"><span data-stu-id="e493c-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="e493c-115">発行者ポリシーを適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e493c-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="e493c-116">属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="e493c-116">apply Attribute</span></span>  
  
|<span data-ttu-id="e493c-117">[値]</span><span class="sxs-lookup"><span data-stu-id="e493c-117">Value</span></span>|<span data-ttu-id="e493c-118">説明</span><span class="sxs-lookup"><span data-stu-id="e493c-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="e493c-119">発行者ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="e493c-119">Applies publisher policy.</span></span> <span data-ttu-id="e493c-120">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="e493c-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="e493c-121">発行元ポリシーは適用されません。</span><span class="sxs-lookup"><span data-stu-id="e493c-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e493c-122">子要素</span><span class="sxs-lookup"><span data-stu-id="e493c-122">Child Elements</span></span>  
 <span data-ttu-id="e493c-123">なし。</span><span class="sxs-lookup"><span data-stu-id="e493c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e493c-124">親要素</span><span class="sxs-lookup"><span data-stu-id="e493c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e493c-125">要素</span><span class="sxs-lookup"><span data-stu-id="e493c-125">Element</span></span>|<span data-ttu-id="e493c-126">説明</span><span class="sxs-lookup"><span data-stu-id="e493c-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e493c-127">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="e493c-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e493c-128">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e493c-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e493c-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="e493c-129">Remarks</span></span>  
 <span data-ttu-id="e493c-130">コンポーネント ベンダーは、アセンブリの新しいバージョンをリリースするとき、ベンダーは、古いバージョンを今すぐ使用するアプリケーションが新しいバージョンを使用するように発行者ポリシーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e493c-130">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="e493c-131">特定のアセンブリに発行者ポリシーを適用するかどうかを指定するには、配置、  **\<publisherPolicy >** 内の要素、  **\<dependentAssembly >** 要素。</span><span class="sxs-lookup"><span data-stu-id="e493c-131">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="e493c-132">既定の設定、**適用**属性が**はい**します。</span><span class="sxs-lookup"><span data-stu-id="e493c-132">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="e493c-133">設定、**適用**属性を**ありません**上書き前**はい**アセンブリの設定。</span><span class="sxs-lookup"><span data-stu-id="e493c-133">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="e493c-134">アクセス許可が明示的にポリシーを使用してパブリッシャーを無視するアプリケーションに必要な[ \<publisherPolicy 適用 ="no"/>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)アプリケーション構成ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="e493c-134">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="e493c-135">許可を設定して、<xref:System.Security.Permissions.SecurityPermissionFlag>にフラグ、<xref:System.Security.Permissions.SecurityPermission>します。</span><span class="sxs-lookup"><span data-stu-id="e493c-135">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="e493c-136">詳細については、次を参照してください。[アセンブリ バインド リダイレクトのセキュリティ権限](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md)します。</span><span class="sxs-lookup"><span data-stu-id="e493c-136">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e493c-137">例</span><span class="sxs-lookup"><span data-stu-id="e493c-137">Example</span></span>  
 <span data-ttu-id="e493c-138">次の例が、アセンブリの発行者ポリシーをオフに`myAssembly`します。</span><span class="sxs-lookup"><span data-stu-id="e493c-138">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e493c-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="e493c-139">See also</span></span>

- [<span data-ttu-id="e493c-140">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="e493c-140">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="e493c-141">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="e493c-141">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="e493c-142">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="e493c-142">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="e493c-143">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="e493c-143">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)

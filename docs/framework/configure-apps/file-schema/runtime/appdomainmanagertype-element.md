---
title: '&lt;appDomainManagerType&gt;要素'
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e7f37fd652ce98e24d2e2e99edcd3d59a0e597b
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610432"
---
# <a name="ltappdomainmanagertypegt-element"></a><span data-ttu-id="054f3-102">&lt;appDomainManagerType&gt;要素</span><span class="sxs-lookup"><span data-stu-id="054f3-102">&lt;appDomainManagerType&gt; Element</span></span>
<span data-ttu-id="054f3-103">既定のアプリケーション ドメインのアプリケーション ドメイン マネージャーの役割を果たす種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="054f3-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
 <span data-ttu-id="054f3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="054f3-104">\<configuration></span></span>  
<span data-ttu-id="054f3-105">\<ランタイム ></span><span class="sxs-lookup"><span data-stu-id="054f3-105">\<runtime></span></span>  
<span data-ttu-id="054f3-106">\<appDomainManagerType ></span><span class="sxs-lookup"><span data-stu-id="054f3-106">\<appDomainManagerType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="054f3-107">構文</span><span class="sxs-lookup"><span data-stu-id="054f3-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="054f3-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="054f3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="054f3-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="054f3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="054f3-110">属性</span><span class="sxs-lookup"><span data-stu-id="054f3-110">Attributes</span></span>  
  
|<span data-ttu-id="054f3-111">属性</span><span class="sxs-lookup"><span data-stu-id="054f3-111">Attribute</span></span>|<span data-ttu-id="054f3-112">説明</span><span class="sxs-lookup"><span data-stu-id="054f3-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="054f3-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="054f3-113">Required attribute.</span></span> <span data-ttu-id="054f3-114">プロセスの既定のアプリケーション ドメインのアプリケーション ドメイン マネージャーとして機能する名前空間を含む、型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="054f3-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="054f3-115">子要素</span><span class="sxs-lookup"><span data-stu-id="054f3-115">Child Elements</span></span>  
 <span data-ttu-id="054f3-116">なし。</span><span class="sxs-lookup"><span data-stu-id="054f3-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="054f3-117">親要素</span><span class="sxs-lookup"><span data-stu-id="054f3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="054f3-118">要素</span><span class="sxs-lookup"><span data-stu-id="054f3-118">Element</span></span>|<span data-ttu-id="054f3-119">説明</span><span class="sxs-lookup"><span data-stu-id="054f3-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="054f3-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="054f3-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="054f3-121">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="054f3-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="054f3-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="054f3-122">Remarks</span></span>  
 <span data-ttu-id="054f3-123">アプリケーション ドメイン マネージャーの種類を指定するには、この両方の要素を指定する必要があります、 [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)要素。</span><span class="sxs-lookup"><span data-stu-id="054f3-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="054f3-124">これらの要素のいずれかが指定されていない場合、その他は無視されます。</span><span class="sxs-lookup"><span data-stu-id="054f3-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="054f3-125">既定のアプリケーション ドメインが読み込まれるときに<xref:System.TypeLoadException>で指定されたアセンブリでは、指定した型が存在しない場合にスローされる、 [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)要素; とプロセスが失敗する起動します。</span><span class="sxs-lookup"><span data-stu-id="054f3-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="054f3-126">既定のアプリケーション ドメインのアプリケーション ドメイン マネージャーの種類を指定すると、既定のアプリケーション ドメインから作成されたその他のアプリケーション ドメインは、アプリケーション ドメイン マネージャーの型を継承します。</span><span class="sxs-lookup"><span data-stu-id="054f3-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="054f3-127">使用して、<xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>と<xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>プロパティを新しいアプリケーション ドメインの別のアプリケーション ドメイン マネージャーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="054f3-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="054f3-128">アプリケーション ドメイン マネージャーの種類を指定するには、完全な信頼のアプリケーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="054f3-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="054f3-129">(たとえば、デスクトップで実行されているアプリケーションは完全な信頼があります。)アプリケーションには、完全な信頼がない場合、<xref:System.TypeLoadException>がスローされます。</span><span class="sxs-lookup"><span data-stu-id="054f3-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="054f3-130">型および名前空間の形式が使用されるのと同じ形式、<xref:System.Type.FullName%2A?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="054f3-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="054f3-131">この構成要素はでのみ使用できますが、[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]以降。</span><span class="sxs-lookup"><span data-stu-id="054f3-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="054f3-132">例</span><span class="sxs-lookup"><span data-stu-id="054f3-132">Example</span></span>  
 <span data-ttu-id="054f3-133">次の例では、プロセスの既定のアプリケーション ドメインのアプリケーション ドメイン マネージャーを指定する方法を示しています、`MyMgr`で入力、`AdMgrExample`アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="054f3-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="054f3-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="054f3-134">See Also</span></span>  
- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="054f3-135">\<appDomainManagerAssembly > 要素</span><span class="sxs-lookup"><span data-stu-id="054f3-135">\<appDomainManagerAssembly> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
- [<span data-ttu-id="054f3-136">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="054f3-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="054f3-137">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="054f3-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="054f3-138">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="054f3-138">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)

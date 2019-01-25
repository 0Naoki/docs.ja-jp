---
title: '&lt;serviceActivations&gt; の &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: d0e1f45cc8ff5b544eff5ff5dae33d5989aaf405
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587636"
---
# <a name="ltaddgt-of-ltserviceactivationsgt"></a><span data-ttu-id="ef904-102">&lt;serviceActivations&gt; の &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="ef904-102">&lt;add&gt; of &lt;serviceActivations&gt;</span></span>
<span data-ttu-id="ef904-103">仮想サービス アクティベーション設定を定義することができます、Windows Communication Foundation (WCF) サービスの型にマップする構成要素。</span><span class="sxs-lookup"><span data-stu-id="ef904-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="ef904-104">これにより、.svc ファイルを使用せずに、WAS/IIS でホストされているサービスをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="ef904-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="ef904-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ef904-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="ef904-106">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="ef904-106">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef904-107">構文</span><span class="sxs-lookup"><span data-stu-id="ef904-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef904-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ef904-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ef904-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ef904-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef904-110">属性</span><span class="sxs-lookup"><span data-stu-id="ef904-110">Attributes</span></span>  
  
|<span data-ttu-id="ef904-111">属性</span><span class="sxs-lookup"><span data-stu-id="ef904-111">Attribute</span></span>|<span data-ttu-id="ef904-112">説明</span><span class="sxs-lookup"><span data-stu-id="ef904-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef904-113">factory</span><span class="sxs-lookup"><span data-stu-id="ef904-113">factory</span></span>|<span data-ttu-id="ef904-114">サービス アクティベーション要素を生成するファクトリの CLR 型名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="ef904-114">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|  
|<span data-ttu-id="ef904-115">service</span><span class="sxs-lookup"><span data-stu-id="ef904-115">service</span></span>|<span data-ttu-id="ef904-116">サービスを実装する ServiceType (完全修飾 Typename または省略形の Typename (App_Code フォルダーに配置されている場合))。</span><span class="sxs-lookup"><span data-stu-id="ef904-116">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|  
|<span data-ttu-id="ef904-117">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="ef904-117">relativeAddress</span></span>|<span data-ttu-id="ef904-118">現在の IIS アプリケーション内の相対アドレス (たとえば "Service.svc")。</span><span class="sxs-lookup"><span data-stu-id="ef904-118">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="ef904-119">WCF 4.0 ではこの相対アドレスが 1 個の既知のファイル拡張子 (.svc、.xamlx など) を含む必要があります。relativeUrl 用の物理ファイルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ef904-119">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef904-120">子要素</span><span class="sxs-lookup"><span data-stu-id="ef904-120">Child Elements</span></span>  
 <span data-ttu-id="ef904-121">なし。</span><span class="sxs-lookup"><span data-stu-id="ef904-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef904-122">親要素</span><span class="sxs-lookup"><span data-stu-id="ef904-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ef904-123">要素</span><span class="sxs-lookup"><span data-stu-id="ef904-123">Element</span></span>|<span data-ttu-id="ef904-124">説明</span><span class="sxs-lookup"><span data-stu-id="ef904-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef904-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="ef904-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="ef904-126">アクティベーション設定を記述する構成セクション。</span><span class="sxs-lookup"><span data-stu-id="ef904-126">A configuration section that describes activation settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef904-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="ef904-127">Remarks</span></span>  
 <span data-ttu-id="ef904-128">web.config ファイルでアクティベーション設定を構成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="ef904-128">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```  
  
 <span data-ttu-id="ef904-129">この構成を使用して、.svc ファイルを使用せずに、GreetingService をアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="ef904-129">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="ef904-130">`<serviceHostingEnvironment>` はアプリケーション レベルの構成であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ef904-130">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="ef904-131">構成を格納した `web.config` は、仮想アプリケーションのルートの下に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef904-131">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="ef904-132">また、`serviceHostingEnvironment` は machinetoApplication の継承可能なセクションです。</span><span class="sxs-lookup"><span data-stu-id="ef904-132">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="ef904-133">コンピューターのルートに単一のサービスを登録すると、アプリケーションの各サービスはこのサービスを継承します。</span><span class="sxs-lookup"><span data-stu-id="ef904-133">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="ef904-134">構成ベースのアクティベーションは、http および非 http プロトコル経由のアクティベーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ef904-134">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="ef904-135">relatativeAddress では、.svc、.xoml、.xamlx などの拡張子が必要です。</span><span class="sxs-lookup"><span data-stu-id="ef904-135">It requires extensions in the relatativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="ef904-136">既知の buildProviders に対して独自の拡張子をマップできます。これにより、任意の拡張子を使用してサービスをアクティブ化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ef904-136">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="ef904-137">競合が発生した場合には、`<serviceActivations>` セクションにより、.svc の登録がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="ef904-137">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef904-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef904-138">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>

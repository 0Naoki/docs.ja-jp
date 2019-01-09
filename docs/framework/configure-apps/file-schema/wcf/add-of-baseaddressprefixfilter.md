---
title: '&lt;baseAddressPrefixFilter&gt; の &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: ece3178c48c84c609ab959a5cfc426062de9255f
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145602"
---
# <a name="ltaddgt-of-ltbaseaddressprefixfiltergt"></a><span data-ttu-id="1403b-102">&lt;baseAddressPrefixFilter&gt; の &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="1403b-102">&lt;add&gt; of &lt;baseAddressPrefixFilter&gt;</span></span>
<span data-ttu-id="1403b-103">パススルー フィルター、IIS で Windows Communication Foundation (WCF) アプリケーションをホストする場合は、適切なインターネット インフォメーション サービス (IIS) バインドを選択するメカニズムを提供するを指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="1403b-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
 <span data-ttu-id="1403b-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1403b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1403b-105">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="1403b-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="1403b-106">\<baseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="1403b-106">\<baseAddressPrefixFilters></span></span>  
<span data-ttu-id="1403b-107">\<add></span><span class="sxs-lookup"><span data-stu-id="1403b-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1403b-108">構文</span><span class="sxs-lookup"><span data-stu-id="1403b-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1403b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1403b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1403b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1403b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1403b-111">属性</span><span class="sxs-lookup"><span data-stu-id="1403b-111">Attributes</span></span>  
  
|<span data-ttu-id="1403b-112">属性</span><span class="sxs-lookup"><span data-stu-id="1403b-112">Attribute</span></span>|<span data-ttu-id="1403b-113">説明</span><span class="sxs-lookup"><span data-stu-id="1403b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1403b-114">prefix</span><span class="sxs-lookup"><span data-stu-id="1403b-114">prefix</span></span>|<span data-ttu-id="1403b-115">ベース アドレスの一部の一致に使用される URI。</span><span class="sxs-lookup"><span data-stu-id="1403b-115">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1403b-116">子要素</span><span class="sxs-lookup"><span data-stu-id="1403b-116">Child Elements</span></span>  
 <span data-ttu-id="1403b-117">なし。</span><span class="sxs-lookup"><span data-stu-id="1403b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1403b-118">親要素</span><span class="sxs-lookup"><span data-stu-id="1403b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1403b-119">要素</span><span class="sxs-lookup"><span data-stu-id="1403b-119">Element</span></span>|<span data-ttu-id="1403b-120">説明</span><span class="sxs-lookup"><span data-stu-id="1403b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1403b-121">\<baseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="1403b-121">\<baseAddressPrefixFilters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|<span data-ttu-id="1403b-122">パススルー フィルター、IIS で Windows Communication Foundation (WCF) アプリケーションをホストする場合は、適切な IIS バインドを選択するためのメカニズムを提供するを指定する構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="1403b-122">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1403b-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="1403b-123">Remarks</span></span>  
 <span data-ttu-id="1403b-124">プレフィックス フィルターは、サービスによって使用される URI を、共有ホスティング プロバイダーが指定できるようにする手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="1403b-124">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="1403b-125">これにより、共有ホストは、同じサイト上の同じスキームに対して、別々のベース アドレスを使用して複数のアプリケーションをホストできるようになります。</span><span class="sxs-lookup"><span data-stu-id="1403b-125">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="1403b-126">IIS Web サイトは、仮想ディレクトリを含む仮想アプリケーションのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="1403b-126">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="1403b-127">サイト内のアプリケーションに、1 つ以上の IIS バインディングからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1403b-127">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="1403b-128">IIS バインディングは、バインディング プロトコルとバインディング情報という 2 つの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1403b-128">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="1403b-129">バインディング プロトコル (HTTP など) は通信を行うスキームを定義し、バインディング情報 (IP アドレス、ポート、ホスト ヘッダーなど) にはサイトにアクセスするために使用するデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1403b-129">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="1403b-130">IIS では、サイトごとに複数の IIS バインディングを指定できるので、各スキームに複数のベース アドレスが定義されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1403b-130">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="1403b-131">サイトでホストされている WCF サービスにスキームごとに 1 つだけのベース アドレスにバインドが使用できるため、ホステッド サービスの必要なベース アドレスを選択、プレフィックス フィルター機能を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1403b-131">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="1403b-132">IIS によって指定される受信ベース アドレスは、オプションのプレフィックス リスト フィルターに基づいてフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="1403b-132">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="1403b-133">たとえば、サイトに次のベース アドレスが含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="1403b-133">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="1403b-134">次の構成ファイルを使用して、appdomain レベルでプレフィックス フィルターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1403b-134">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 <span data-ttu-id="1403b-135">この例では、`net.tcp://test1.fabrikam.com:8000` と `http://test2.fabrikam.com:9000` はそれぞれのスキームにおいて、そのまま渡すことができる唯一のベース アドレスです。</span><span class="sxs-lookup"><span data-stu-id="1403b-135">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="1403b-136">既定では、プレフィックスを指定しない場合、すべてのアドレスが渡されます。</span><span class="sxs-lookup"><span data-stu-id="1403b-136">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="1403b-137">プレフィックスだけを指定すると、そのスキームに一致するベース アドレスを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="1403b-137">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1403b-138">フィルターでワイルドカードはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="1403b-138">The filter does not support any wildcards.</span></span> <span data-ttu-id="1403b-139">また、IIS が提供する baseAddresses には、`baseAddressPrefixFilters` リストに存在しない他のスキームにバインドされたアドレスが指定される場合があります。</span><span class="sxs-lookup"><span data-stu-id="1403b-139">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="1403b-140">これらのアドレスはフィルターで除外されません。</span><span class="sxs-lookup"><span data-stu-id="1403b-140">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1403b-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="1403b-141">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="1403b-142">ホスティング</span><span class="sxs-lookup"><span data-stu-id="1403b-142">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)

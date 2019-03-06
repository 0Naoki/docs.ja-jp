---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: e82312cb17fbd3f76f781ea37f761e946319a0a0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351856"
---
# <a name="findcriteria"></a><span data-ttu-id="8d4bb-101">\<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="8d4bb-101">\<findCriteria></span></span>
<span data-ttu-id="8d4bb-102">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-102">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="8d4bb-103">条件は、(探しているサービスの種類を指定して) 検索条件にグループ化することができ、検索 (検索持続期間)、終了条件。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-103">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
 <span data-ttu-id="8d4bb-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8d4bb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8d4bb-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="8d4bb-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d4bb-106">構文</span><span class="sxs-lookup"><span data-stu-id="8d4bb-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            </contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d4bb-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8d4bb-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8d4bb-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d4bb-109">属性</span><span class="sxs-lookup"><span data-stu-id="8d4bb-109">Attributes</span></span>  
  
|<span data-ttu-id="8d4bb-110">属性</span><span class="sxs-lookup"><span data-stu-id="8d4bb-110">Attribute</span></span>|<span data-ttu-id="8d4bb-111">説明</span><span class="sxs-lookup"><span data-stu-id="8d4bb-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8d4bb-112">duration</span><span class="sxs-lookup"><span data-stu-id="8d4bb-112">duration</span></span>|<span data-ttu-id="8d4bb-113">ネットワーク上でサービスからの応答を待機する最長時間を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-113">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="8d4bb-114">既定の時間は 20 秒です。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-114">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="8d4bb-115">maxResults</span><span class="sxs-lookup"><span data-stu-id="8d4bb-115">maxResults</span></span>|<span data-ttu-id="8d4bb-116">ネットワークまたはインターネット上で待機する、サービスから応答の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-116">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="8d4bb-117">`duration` 属性に指定した時間が経過する前に応答の最大数に達した場合、検索操作は終了します。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-117">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="8d4bb-118">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="8d4bb-118">scopeMatchBy</span></span>|<span data-ttu-id="8d4bb-119">Probe メッセージのスコープをエンドポイントのスコープと一致させるときに使用する、一致のアルゴリズムを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-119">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="8d4bb-120">サポートされているスコープ一致規則は 5 つあります。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-120">There are five supported scope-matching rules.</span></span> <span data-ttu-id="8d4bb-121">スコープ一致規則を指定しなかった場合は、`ScopeMatchByPrefix` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-121">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="8d4bb-122">詳細については、「<xref:System.ServiceModel.Discovery.FindCriteria>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-122">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d4bb-123">子要素</span><span class="sxs-lookup"><span data-stu-id="8d4bb-123">Child Elements</span></span>  
  
|<span data-ttu-id="8d4bb-124">要素</span><span class="sxs-lookup"><span data-stu-id="8d4bb-124">Element</span></span>|<span data-ttu-id="8d4bb-125">説明</span><span class="sxs-lookup"><span data-stu-id="8d4bb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d4bb-126">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="8d4bb-126">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="8d4bb-127">ワークフロー サービス コントラクト型の名前を格納する構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-127">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="8d4bb-128">\<拡張機能 > の\<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="8d4bb-128">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="8d4bb-129">拡張を提供する XML 要素オブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-129">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="8d4bb-130">\<scopes></span><span class="sxs-lookup"><span data-stu-id="8d4bb-130">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="8d4bb-131">特定のサービスを特定する検索操作の実行中に使用される絶対 URI を格納するオブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-131">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="8d4bb-132">特定のサービスが見つかった場合、サービス URI とスコープ URI が一致します。複雑な一致を処理するスコープ規則が使用されることもあります。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-132">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8d4bb-133">親要素</span><span class="sxs-lookup"><span data-stu-id="8d4bb-133">Parent Elements</span></span>  
  
|<span data-ttu-id="8d4bb-134">要素</span><span class="sxs-lookup"><span data-stu-id="8d4bb-134">Element</span></span>|<span data-ttu-id="8d4bb-135">説明</span><span class="sxs-lookup"><span data-stu-id="8d4bb-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d4bb-136">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="8d4bb-136">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="8d4bb-137">サービス探索プロセスにクライアントとして参加するためにアプリケーションが必要とする設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="8d4bb-137">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d4bb-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d4bb-138">See also</span></span>
- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>

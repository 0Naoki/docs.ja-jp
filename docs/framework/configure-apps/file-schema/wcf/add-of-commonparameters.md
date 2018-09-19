---
title: '&lt;commonParameters&gt; の &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: 93e82aa3bd44a747d1e85986c51c21522d709bd0
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46287265"
---
# <a name="ltaddgt-of-ltcommonparametersgt"></a><span data-ttu-id="db6cf-102">&lt;commonParameters&gt; の &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="db6cf-102">&lt;add&gt; of &lt;commonParameters&gt;</span></span>
<span data-ttu-id="db6cf-103">複数のサービスでグローバルに使用されるパラメーターの名前と値のペアを指定します。</span><span class="sxs-lookup"><span data-stu-id="db6cf-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="db6cf-104">このパラメーターには通常、永続性サービスによって共有されるデータベース接続文字列が格納されます。</span><span class="sxs-lookup"><span data-stu-id="db6cf-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="db6cf-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="db6cf-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="db6cf-106">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="db6cf-106">\<behaviors></span></span>  
<span data-ttu-id="db6cf-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="db6cf-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="db6cf-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="db6cf-108">\<behavior></span></span>  
<span data-ttu-id="db6cf-109">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="db6cf-109">\<workflowRuntime></span></span>  
<span data-ttu-id="db6cf-110">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="db6cf-110">\<commonParameters></span></span>  
<span data-ttu-id="db6cf-111">\<add></span><span class="sxs-lookup"><span data-stu-id="db6cf-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db6cf-112">構文</span><span class="sxs-lookup"><span data-stu-id="db6cf-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db6cf-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="db6cf-113">Attributes and Elements</span></span>  
 <span data-ttu-id="db6cf-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="db6cf-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db6cf-115">属性</span><span class="sxs-lookup"><span data-stu-id="db6cf-115">Attributes</span></span>  
  
|<span data-ttu-id="db6cf-116">属性</span><span class="sxs-lookup"><span data-stu-id="db6cf-116">Attribute</span></span>|<span data-ttu-id="db6cf-117">説明</span><span class="sxs-lookup"><span data-stu-id="db6cf-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db6cf-118">name</span><span class="sxs-lookup"><span data-stu-id="db6cf-118">name</span></span>|<span data-ttu-id="db6cf-119">サービスに対して指定されたパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="db6cf-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="db6cf-120">value</span><span class="sxs-lookup"><span data-stu-id="db6cf-120">value</span></span>|<span data-ttu-id="db6cf-121">サービスに対して指定されたパラメーターの値。</span><span class="sxs-lookup"><span data-stu-id="db6cf-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db6cf-122">子要素</span><span class="sxs-lookup"><span data-stu-id="db6cf-122">Child Elements</span></span>  
 <span data-ttu-id="db6cf-123">なし。</span><span class="sxs-lookup"><span data-stu-id="db6cf-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db6cf-124">親要素</span><span class="sxs-lookup"><span data-stu-id="db6cf-124">Parent Elements</span></span>  
  
|<span data-ttu-id="db6cf-125">要素</span><span class="sxs-lookup"><span data-stu-id="db6cf-125">Element</span></span>|<span data-ttu-id="db6cf-126">説明</span><span class="sxs-lookup"><span data-stu-id="db6cf-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db6cf-127">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="db6cf-127">\<commonParameters></span></span>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|<span data-ttu-id="db6cf-128">サービスによって使用される共通パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="db6cf-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="db6cf-129">このコレクションには通常、永続性サービスによって共有されるデータベース接続文字列が格納されます。</span><span class="sxs-lookup"><span data-stu-id="db6cf-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db6cf-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="db6cf-130">Remarks</span></span>  
 <span data-ttu-id="db6cf-131">最初の要素 `<commonParameters>` は、複数のサービスでグローバルに使用されるパラメーターを定義します (たとえば `ConnectionString` を使用する場合の <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>)。</span><span class="sxs-lookup"><span data-stu-id="db6cf-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="db6cf-132"><xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> や <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService> など、作業バッチを永続的ストアにコミットするサービスでは、`EnableRetries` パラメーターを次の例のように使用することで、トランザクションの再試行を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="db6cf-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 <span data-ttu-id="db6cf-133">注意して、`EnableRetries`パラメーターで設定できますか、グローバル レベル (ように、 *CommonParameters*セクション)、または個々 のサービスをサポートする`EnableRetries`(ように、*サービス*セクション)。</span><span class="sxs-lookup"><span data-stu-id="db6cf-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="db6cf-134">動作を制御する構成ファイルの使用の詳細については、<xref:System.Workflow.Runtime.WorkflowRuntime>オブジェクトの Windows Workflow Foundation ホスト アプリケーションでは、次を参照してください。[ワークフロー構成ファイル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))します。</span><span class="sxs-lookup"><span data-stu-id="db6cf-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="db6cf-135">例</span><span class="sxs-lookup"><span data-stu-id="db6cf-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="db6cf-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="db6cf-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 <span data-ttu-id="db6cf-137">[ワークフロー構成ファイル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="db6cf-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>  
 [<span data-ttu-id="db6cf-138">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="db6cf-138">\<commonParameters></span></span>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)

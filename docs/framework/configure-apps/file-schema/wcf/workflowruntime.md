---
title: '&lt;workflowRuntime&gt;'
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: 849b09936f303c21fe55a6a46d561590c6a4c808
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43455758"
---
# <a name="ltworkflowruntimegt"></a><span data-ttu-id="567cf-102">&lt;workflowRuntime&gt;</span><span class="sxs-lookup"><span data-stu-id="567cf-102">&lt;workflowRuntime&gt;</span></span>
<span data-ttu-id="567cf-103">インスタンスの設定を指定<xref:System.Workflow.Runtime.WorkflowRuntime>ワークフロー ベースの Windows Communication Foundation (WCF) サービスをホストするためです。</span><span class="sxs-lookup"><span data-stu-id="567cf-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
 <span data-ttu-id="567cf-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="567cf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="567cf-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="567cf-105">\<behaviors></span></span>  
<span data-ttu-id="567cf-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="567cf-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="567cf-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="567cf-107">\<behavior></span></span>  
<span data-ttu-id="567cf-108">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="567cf-108">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="567cf-109">構文</span><span class="sxs-lookup"><span data-stu-id="567cf-109">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"  
                                  enablePerformanceCounters="Boolean"  
                                  name="String"  
                                  validateOnCreate="Boolean">  
                 <commonParameters>  
                    <add name="String" value="String" />  
                 </commonParameters>  
                 <services>  
                    <add type="String"/>  
                 </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="567cf-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="567cf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="567cf-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="567cf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="567cf-112">属性</span><span class="sxs-lookup"><span data-stu-id="567cf-112">Attributes</span></span>  
  
|<span data-ttu-id="567cf-113">属性</span><span class="sxs-lookup"><span data-stu-id="567cf-113">Attribute</span></span>|<span data-ttu-id="567cf-114">説明</span><span class="sxs-lookup"><span data-stu-id="567cf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="567cf-115">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="567cf-115">cachedInstanceExpiration</span></span>|<span data-ttu-id="567cf-116">ワークフロー インスタンスが強制的にアンロードまたは中止される前に、アイドル状態でメモリに残ることができる最大期間を指定する、省略可能な <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="567cf-116">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="567cf-117">unloadOnIdle を実行する `PersistenceService` が workflowruntime に設定されている場合、この属性は無視されます。</span><span class="sxs-lookup"><span data-stu-id="567cf-117">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="567cf-118">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="567cf-118">enablePerformanceCounters</span></span>|<span data-ttu-id="567cf-119">パフォーマンス カウンターが有効であるかどうかを指定する省略可能なブール値。</span><span class="sxs-lookup"><span data-stu-id="567cf-119">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="567cf-120">パフォーマンス カウンターは、ワークフローに関連したさまざまな統計情報を提供します。ただしそのために、ワークフロー ランタイム エンジンが起動してワークフロー インスタンスが実行されている間は、パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="567cf-120">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="567cf-121">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="567cf-121">The default value is `true`.</span></span>|  
|<span data-ttu-id="567cf-122">name</span><span class="sxs-lookup"><span data-stu-id="567cf-122">name</span></span>|<span data-ttu-id="567cf-123">ワークフロー ランタイム エンジンの名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="567cf-123">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="567cf-124">名前は出力で使用され、このランタイムを、システムで実行されている他のランタイム (パフォーマンス カウンターなど) と区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="567cf-124">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="567cf-125">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="567cf-125">The default is an empty string.</span></span>|  
|<span data-ttu-id="567cf-126">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="567cf-126">validateOnCreate</span></span>|<span data-ttu-id="567cf-127">WorkflowServiceHost を開いたときにワークフロー定義の検証を行うかどうかを指定する省略可能なブール値。</span><span class="sxs-lookup"><span data-stu-id="567cf-127">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="567cf-128">この属性が `true` に設定されているときは、`WorkflowServiceHost.Open` が呼び出されるたびにワークフローの検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="567cf-128">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="567cf-129">検証エラーが見つかった場合は、<xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="567cf-129">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="567cf-130">このプロパティが `false` に設定されている場合、ワークフロー定義の検証は行われません。</span><span class="sxs-lookup"><span data-stu-id="567cf-130">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="567cf-131">このプロパティの既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="567cf-131">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="567cf-132">子要素</span><span class="sxs-lookup"><span data-stu-id="567cf-132">Child Elements</span></span>  
  
|<span data-ttu-id="567cf-133">要素</span><span class="sxs-lookup"><span data-stu-id="567cf-133">Element</span></span>|<span data-ttu-id="567cf-134">説明</span><span class="sxs-lookup"><span data-stu-id="567cf-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="567cf-135">commonParameters</span><span class="sxs-lookup"><span data-stu-id="567cf-135">commonParameters</span></span>|<span data-ttu-id="567cf-136">サービスによって使用される共通パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="567cf-136">A collection of common parameters used by services.</span></span> <span data-ttu-id="567cf-137">このコレクションには通常、永続性サービスによって共有されるデータベース接続文字列が格納されます。</span><span class="sxs-lookup"><span data-stu-id="567cf-137">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="567cf-138">サービス</span><span class="sxs-lookup"><span data-stu-id="567cf-138">services</span></span>|<span data-ttu-id="567cf-139"><xref:System.Workflow.Runtime.WorkflowRuntime> エンジンに追加されるサービスのコレクション。</span><span class="sxs-lookup"><span data-stu-id="567cf-139">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="567cf-140">要素は、<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="567cf-140">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="567cf-141">コレクションで指定されたサービスはワークフロー ランタイム エンジンによって初期化され、適切な <xref:System.Workflow.Runtime.WorkflowRuntime> コンストラクターが呼び出されるとワークフロー ランタイム エンジンのサービスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="567cf-141">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="567cf-142">したがって、コレクションで指定されたサービスは、そのコンストラクターのシグネチャに関して一定の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="567cf-142">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="567cf-143">詳細については、「<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="567cf-143">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="567cf-144">親要素</span><span class="sxs-lookup"><span data-stu-id="567cf-144">Parent Elements</span></span>  
  
|<span data-ttu-id="567cf-145">要素</span><span class="sxs-lookup"><span data-stu-id="567cf-145">Element</span></span>|<span data-ttu-id="567cf-146">説明</span><span class="sxs-lookup"><span data-stu-id="567cf-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="567cf-147">\<behavior></span><span class="sxs-lookup"><span data-stu-id="567cf-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="567cf-148">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="567cf-148">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="567cf-149">Remarks</span><span class="sxs-lookup"><span data-stu-id="567cf-149">Remarks</span></span>  
 <span data-ttu-id="567cf-150">動作を制御する構成ファイルの使用の詳細については、<xref:System.Workflow.Runtime.WorkflowRuntime>オブジェクトの Windows Workflow Foundation ホスト アプリケーションでは、次を参照してください。[ワークフロー構成ファイル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))します。</span><span class="sxs-lookup"><span data-stu-id="567cf-150">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="567cf-151">例</span><span class="sxs-lookup"><span data-stu-id="567cf-151">Example</span></span>  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <commonParameters>  
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
            <add name="EnableRetries" value="True" />  
         </commonParameters>  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="567cf-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="567cf-152">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <span data-ttu-id="567cf-153">[ワークフロー構成ファイル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="567cf-153">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>

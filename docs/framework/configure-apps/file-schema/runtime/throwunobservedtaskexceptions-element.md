---
title: '&lt;ThrowUnobservedTaskExceptions&gt;要素'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: edf3fd9a4561677813adbfb970a9d6be43d7c83d
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612583"
---
# <a name="ltthrowunobservedtaskexceptionsgt-element"></a><span data-ttu-id="1a596-102">&lt;ThrowUnobservedTaskExceptions&gt;要素</span><span class="sxs-lookup"><span data-stu-id="1a596-102">&lt;ThrowUnobservedTaskExceptions&gt; Element</span></span>
<span data-ttu-id="1a596-103">タスクがハンドルされない例外によって実行中のプロセスを終了するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a596-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
 <span data-ttu-id="1a596-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1a596-104">\<configuration></span></span>  
<span data-ttu-id="1a596-105">\<ランタイム ></span><span class="sxs-lookup"><span data-stu-id="1a596-105">\<runtime></span></span>  
<span data-ttu-id="1a596-106">\<ThrowUnobservedTaskExceptions ></span><span class="sxs-lookup"><span data-stu-id="1a596-106">\<ThrowUnobservedTaskExceptions></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a596-107">構文</span><span class="sxs-lookup"><span data-stu-id="1a596-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a596-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1a596-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1a596-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a596-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a596-110">属性</span><span class="sxs-lookup"><span data-stu-id="1a596-110">Attributes</span></span>  
  
|<span data-ttu-id="1a596-111">属性</span><span class="sxs-lookup"><span data-stu-id="1a596-111">Attribute</span></span>|<span data-ttu-id="1a596-112">説明</span><span class="sxs-lookup"><span data-stu-id="1a596-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1a596-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="1a596-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="1a596-114">タスクがハンドルされない例外が実行中のプロセスを終了するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a596-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1a596-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="1a596-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="1a596-116">値</span><span class="sxs-lookup"><span data-stu-id="1a596-116">Value</span></span>|<span data-ttu-id="1a596-117">説明</span><span class="sxs-lookup"><span data-stu-id="1a596-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1a596-118">タスクがハンドルされない例外の実行中のプロセスを終了しません。</span><span class="sxs-lookup"><span data-stu-id="1a596-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="1a596-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="1a596-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="1a596-120">タスクがハンドルされない例外の実行中のプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="1a596-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a596-121">子要素</span><span class="sxs-lookup"><span data-stu-id="1a596-121">Child Elements</span></span>  
 <span data-ttu-id="1a596-122">なし。</span><span class="sxs-lookup"><span data-stu-id="1a596-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a596-123">親要素</span><span class="sxs-lookup"><span data-stu-id="1a596-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1a596-124">要素</span><span class="sxs-lookup"><span data-stu-id="1a596-124">Element</span></span>|<span data-ttu-id="1a596-125">説明</span><span class="sxs-lookup"><span data-stu-id="1a596-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1a596-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="1a596-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1a596-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="1a596-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="1a596-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="1a596-128">Remarks</span></span>  
 <span data-ttu-id="1a596-129">例外に関連付けられている場合、<xref:System.Threading.Tasks.Task>が監視されていません、あるありません<xref:System.Threading.Tasks.Task.Wait%2A>操作、親がアタッチされていないと、<xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType>プロパティは、タスクの例外を監視できないと見なさが読み取られていません。</span><span class="sxs-lookup"><span data-stu-id="1a596-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="1a596-130">[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]により、既定では場合、<xref:System.Threading.Tasks.Task>を持つ、無視された例外は、ガベージ コレクション、ファイナライザーが例外をスローし、プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="1a596-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="1a596-131">プロセスの終了は、ガベージ コレクションとファイナライズのタイミングによって決まります。</span><span class="sxs-lookup"><span data-stu-id="1a596-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="1a596-132">タスク ベースの非同期コードを記述する開発者向けに容易にできるように、[!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]監視されていない例外の場合は、この既定動作が変わります。</span><span class="sxs-lookup"><span data-stu-id="1a596-132">To make it easier for developers to write asynchronous code based on tasks, the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="1a596-133">無視された例外の原因となる、<xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>イベントを発生させるには、既定では、プロセスを終了しません。</span><span class="sxs-lookup"><span data-stu-id="1a596-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="1a596-134">代わりに、イベント ハンドラーが例外を監視するかどうかに関係なく、イベントが発生した後、例外は無視されます。</span><span class="sxs-lookup"><span data-stu-id="1a596-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="1a596-135">[!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]、使用することができます、 [ \<ThrowUnobservedTaskExceptions > 要素](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)を有効にするアプリケーション構成ファイルで、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]動作が例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="1a596-135">In the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], you can use the [\<ThrowUnobservedTaskExceptions> element](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) in an application configuration file to enable the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="1a596-136">次の方法のいずれかで例外の動作を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a596-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
-   <span data-ttu-id="1a596-137">環境変数を設定して`COMPlus_ThrowUnobservedTaskExceptions`(`set COMPlus_ThrowUnobservedTaskExceptions=1`)。</span><span class="sxs-lookup"><span data-stu-id="1a596-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
-   <span data-ttu-id="1a596-138">DWORD のレジストリ設定値 ThrowUnobservedTaskExceptions = 1 に、hkey_local_machine \software\microsoft\\します。NETFramework キー。</span><span class="sxs-lookup"><span data-stu-id="1a596-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a596-139">例</span><span class="sxs-lookup"><span data-stu-id="1a596-139">Example</span></span>  
 <span data-ttu-id="1a596-140">次の例では、アプリケーション構成ファイルを使用して、タスクでの例外のスローを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1a596-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="1a596-141">例</span><span class="sxs-lookup"><span data-stu-id="1a596-141">Example</span></span>  
 <span data-ttu-id="1a596-142">次の例では、タスクから無視された例外をスローする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1a596-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="1a596-143">コードは、正常に動作するリリース プログラムとして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a596-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1a596-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a596-144">See Also</span></span>  
- [<span data-ttu-id="1a596-145">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="1a596-145">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="1a596-146">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="1a596-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

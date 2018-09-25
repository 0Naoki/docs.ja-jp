---
title: '&lt;削除&gt;要素&lt;リスナー&gt;の&lt;トレース&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 54fd529c571c8e8cf43c5dabe2398ae4a6cf4f11
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47088959"
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="9fd71-102">&lt;削除&gt;要素&lt;リスナー&gt;の&lt;トレース&gt;</span><span class="sxs-lookup"><span data-stu-id="9fd71-102">&lt;remove&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="9fd71-103">リスナーを削除、**リスナー**コレクション。</span><span class="sxs-lookup"><span data-stu-id="9fd71-103">Removes a listener from the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="9fd71-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9fd71-104">\<configuration></span></span>  
<span data-ttu-id="9fd71-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="9fd71-105">\<system.diagnostics></span></span>  
<span data-ttu-id="9fd71-106">\<トレース ></span><span class="sxs-lookup"><span data-stu-id="9fd71-106">\<trace></span></span>  
<span data-ttu-id="9fd71-107">\<リスナー ></span><span class="sxs-lookup"><span data-stu-id="9fd71-107">\<listeners></span></span>  
<span data-ttu-id="9fd71-108">\<remove></span><span class="sxs-lookup"><span data-stu-id="9fd71-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fd71-109">構文</span><span class="sxs-lookup"><span data-stu-id="9fd71-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fd71-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9fd71-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9fd71-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9fd71-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fd71-112">属性</span><span class="sxs-lookup"><span data-stu-id="9fd71-112">Attributes</span></span>  
  
|<span data-ttu-id="9fd71-113">属性</span><span class="sxs-lookup"><span data-stu-id="9fd71-113">Attribute</span></span>|<span data-ttu-id="9fd71-114">説明</span><span class="sxs-lookup"><span data-stu-id="9fd71-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9fd71-115">**name**</span><span class="sxs-lookup"><span data-stu-id="9fd71-115">**name**</span></span>|<span data-ttu-id="9fd71-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="9fd71-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="9fd71-117">削除するリスナーの名前、**リスナー**コレクション。</span><span class="sxs-lookup"><span data-stu-id="9fd71-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fd71-118">子要素</span><span class="sxs-lookup"><span data-stu-id="9fd71-118">Child Elements</span></span>  
 <span data-ttu-id="9fd71-119">なし。</span><span class="sxs-lookup"><span data-stu-id="9fd71-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9fd71-120">親要素</span><span class="sxs-lookup"><span data-stu-id="9fd71-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9fd71-121">要素</span><span class="sxs-lookup"><span data-stu-id="9fd71-121">Element</span></span>|<span data-ttu-id="9fd71-122">説明</span><span class="sxs-lookup"><span data-stu-id="9fd71-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9fd71-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="9fd71-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="9fd71-124">収集、するリスナーをストアを指定し、メッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="9fd71-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="9fd71-125">リスナーでは、適切なターゲットのトレースを出力します。</span><span class="sxs-lookup"><span data-stu-id="9fd71-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="9fd71-126">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fd71-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="9fd71-127">ASP.NET トレース サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="9fd71-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fd71-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="9fd71-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fd71-129">削除、<xref:System.Diagnostics.DefaultTraceListener>から、`Listeners`コレクションの動作を変更する、 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>、 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>、 <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>、および<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="9fd71-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="9fd71-130">呼び出す、`Assert`または`Fail`メソッド結果は、通常、メッセージ ボックスの表示の場合、メッセージ ボックスは表示されませんが、<xref:System.Diagnostics.DefaultTraceListener>内にない、`Listeners`コレクション。</span><span class="sxs-lookup"><span data-stu-id="9fd71-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fd71-131">例</span><span class="sxs-lookup"><span data-stu-id="9fd71-131">Example</span></span>  
 <span data-ttu-id="9fd71-132">次の例は、トレースから既定のトレース リスナーを削除する方法を示しています。**リスナー**コレクション。</span><span class="sxs-lookup"><span data-stu-id="9fd71-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fd71-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="9fd71-133">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [<span data-ttu-id="9fd71-134">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="9fd71-134">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)

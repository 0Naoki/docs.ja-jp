---
title: '&lt;ソース&gt;要素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a9c5c5529e349eca2ba089ed6fb71da4bd48430a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084450"
---
# <a name="ltsourcesgt-element"></a><span data-ttu-id="b76d6-102">&lt;ソース&gt;要素</span><span class="sxs-lookup"><span data-stu-id="b76d6-102">&lt;sources&gt; Element</span></span>
<span data-ttu-id="b76d6-103">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="b76d6-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="b76d6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b76d6-104">\<configuration></span></span>  
<span data-ttu-id="b76d6-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="b76d6-105">\<system.diagnostics></span></span>  
<span data-ttu-id="b76d6-106">\<ソース ></span><span class="sxs-lookup"><span data-stu-id="b76d6-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b76d6-107">構文</span><span class="sxs-lookup"><span data-stu-id="b76d6-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b76d6-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b76d6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b76d6-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b76d6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b76d6-110">属性</span><span class="sxs-lookup"><span data-stu-id="b76d6-110">Attributes</span></span>  
 <span data-ttu-id="b76d6-111">なし。</span><span class="sxs-lookup"><span data-stu-id="b76d6-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b76d6-112">子要素</span><span class="sxs-lookup"><span data-stu-id="b76d6-112">Child Elements</span></span>  
  
|<span data-ttu-id="b76d6-113">要素</span><span class="sxs-lookup"><span data-stu-id="b76d6-113">Element</span></span>|<span data-ttu-id="b76d6-114">説明</span><span class="sxs-lookup"><span data-stu-id="b76d6-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b76d6-115">\<source></span><span class="sxs-lookup"><span data-stu-id="b76d6-115">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="b76d6-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="b76d6-116">Required element.</span></span><br /><br /> <span data-ttu-id="b76d6-117">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="b76d6-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b76d6-118">親要素</span><span class="sxs-lookup"><span data-stu-id="b76d6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b76d6-119">要素</span><span class="sxs-lookup"><span data-stu-id="b76d6-119">Element</span></span>|<span data-ttu-id="b76d6-120">説明</span><span class="sxs-lookup"><span data-stu-id="b76d6-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b76d6-121">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b76d6-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b76d6-122">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b76d6-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b76d6-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="b76d6-123">Remarks</span></span>  
 <span data-ttu-id="b76d6-124">この要素は、マシン構成ファイル (Machine.config) と、アプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b76d6-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b76d6-125">例</span><span class="sxs-lookup"><span data-stu-id="b76d6-125">Example</span></span>  
 <span data-ttu-id="b76d6-126">次の例は、使用する方法を示します、`<sources>`トレース ソースを追加する要素`mySource`という名前のソース スイッチのレベルを設定して`sourceSwitch`します。</span><span class="sxs-lookup"><span data-stu-id="b76d6-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="b76d6-127">トレース情報をコンソールに出力する、コンソール トレース リスナーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="b76d6-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"   
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"   
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"   
                     initializeData="Error" />  
               </add>  
               <remove name="Default" />  
            </listeners>  
         </source>  
      </sources>  
      <switches>  
         <add name="sourceSwitch" value="Warning" />  
      </switches>    
   </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b76d6-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="b76d6-128">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 [<span data-ttu-id="b76d6-129">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="b76d6-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="b76d6-130">\<source></span><span class="sxs-lookup"><span data-stu-id="b76d6-130">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)

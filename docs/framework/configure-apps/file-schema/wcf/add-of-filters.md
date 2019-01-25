---
title: '&lt;filters&gt; の &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 43898485ea5730e958cbc4e9968d25c0e7f0d951
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709456"
---
# <a name="ltaddgt-of-ltfiltersgt"></a><span data-ttu-id="e9cf5-102">&lt;filters&gt; の &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="e9cf5-102">&lt;add&gt; of &lt;filters&gt;</span></span>
<span data-ttu-id="e9cf5-103">ログに記録するメッセージの種類を指定する XPath フィルター。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
 <span data-ttu-id="e9cf5-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e9cf5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e9cf5-105">\<診断 ></span><span class="sxs-lookup"><span data-stu-id="e9cf5-105">\<diagnostic></span></span>  
<span data-ttu-id="e9cf5-106">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="e9cf5-106">\<messageLogging></span></span>  
<span data-ttu-id="e9cf5-107">\<filters></span><span class="sxs-lookup"><span data-stu-id="e9cf5-107">\<filters></span></span>  
<span data-ttu-id="e9cf5-108">\<add></span><span class="sxs-lookup"><span data-stu-id="e9cf5-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9cf5-109">構文</span><span class="sxs-lookup"><span data-stu-id="e9cf5-109">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9cf5-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e9cf5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e9cf5-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9cf5-112">属性</span><span class="sxs-lookup"><span data-stu-id="e9cf5-112">Attributes</span></span>  
  
|<span data-ttu-id="e9cf5-113">属性</span><span class="sxs-lookup"><span data-stu-id="e9cf5-113">Attribute</span></span>|<span data-ttu-id="e9cf5-114">説明</span><span class="sxs-lookup"><span data-stu-id="e9cf5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9cf5-115">フィルター</span><span class="sxs-lookup"><span data-stu-id="e9cf5-115">filter</span></span>|<span data-ttu-id="e9cf5-116">XPath 1.0 の式によって定義される、XML ドキュメントのクエリを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-116">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="e9cf5-117">詳細については、「 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-117">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9cf5-118">子要素</span><span class="sxs-lookup"><span data-stu-id="e9cf5-118">Child Elements</span></span>  
 <span data-ttu-id="e9cf5-119">なし。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9cf5-120">親要素</span><span class="sxs-lookup"><span data-stu-id="e9cf5-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e9cf5-121">要素</span><span class="sxs-lookup"><span data-stu-id="e9cf5-121">Element</span></span>|<span data-ttu-id="e9cf5-122">説明</span><span class="sxs-lookup"><span data-stu-id="e9cf5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9cf5-123">\<filters></span><span class="sxs-lookup"><span data-stu-id="e9cf5-123">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters.md)|<span data-ttu-id="e9cf5-124">ログに記録されるメッセージの種類を制御する XPath フィルターのコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-124">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9cf5-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="e9cf5-125">Remarks</span></span>  
 <span data-ttu-id="e9cf5-126">フィルターは、`logMessagesAtTransportLevel` を `true` に設定することによって指定されるトランスポート層でのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-126">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="e9cf5-127">サービス レベルおよび形式が正しくないメッセージ ログ記録は、フィルターの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-127">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="e9cf5-128">コレクションにフィルターを追加するには、`add` を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-128">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="e9cf5-129">1 つ以上のフィルターを定義した場合は、少なくとも 1 つのフィルターと一致するメッセージだけが記録されます。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-129">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="e9cf5-130">フィルターを定義しなかった場合は、すべてのメッセージが通過します。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-130">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="e9cf5-131">フィルターは、完全な XPath 構文をサポートし、構成ファイルでの出現順に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-131">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="e9cf5-132">フィルターが構文的に正しくない場合は、構成例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-132">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="e9cf5-133">SOAP ヘッダー セクションがあるメッセージだけを記録するフィルターの設定方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-133">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9cf5-134">例</span><span class="sxs-lookup"><span data-stu-id="e9cf5-134">Example</span></span>  
 <span data-ttu-id="e9cf5-135">SOAP ヘッダー セクションがあるメッセージだけを記録するフィルターの設定方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e9cf5-135">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="420">
  <filters>
    <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
      /soap:Envelope/soap:Headers
    </add>
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a><span data-ttu-id="e9cf5-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9cf5-136">See also</span></span>
- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="e9cf5-137">メッセージ ログの構成</span><span class="sxs-lookup"><span data-stu-id="e9cf5-137">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="e9cf5-138">メッセージ ログの構成</span><span class="sxs-lookup"><span data-stu-id="e9cf5-138">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="e9cf5-139">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="e9cf5-139">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)

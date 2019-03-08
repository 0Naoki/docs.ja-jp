---
title: UI オートメーションにおけるキャッシュの使用
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- caching, UI Automation
- UI Automation, caching
ms.assetid: ec722dff-6009-4279-b86a-e18d3fa94ebf
ms.openlocfilehash: 0c12b8347e0dfe239189a7e1d1569aaf2dabc0a2
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675499"
---
# <a name="use-caching-in-ui-automation"></a><span data-ttu-id="875f2-102">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="875f2-102">Use Caching in UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="875f2-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="875f2-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="875f2-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="875f2-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="875f2-105">ここでは、 <xref:System.Windows.Automation.AutomationElement> プロパティとコントロール パターンのキャッシュを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="875f2-105">This section shows how to implement caching of <xref:System.Windows.Automation.AutomationElement> properties and control patterns.</span></span>  
  
### <a name="activate-a-cache-request"></a><span data-ttu-id="875f2-106">キャッシュ要求のアクティブ化</span><span class="sxs-lookup"><span data-stu-id="875f2-106">Activate a Cache Request</span></span>  
  
1.  <span data-ttu-id="875f2-107"><xref:System.Windows.Automation.CacheRequest>を作成します。</span><span class="sxs-lookup"><span data-stu-id="875f2-107">Create a <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2.  <span data-ttu-id="875f2-108"><xref:System.Windows.Automation.CacheRequest.Add%2A>を使用して、キャッシュするプロパティとパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="875f2-108">Specify properties and patterns to cache by using <xref:System.Windows.Automation.CacheRequest.Add%2A>.</span></span>  
  
3.  <span data-ttu-id="875f2-109"><xref:System.Windows.Automation.CacheRequest.TreeScope%2A> プロパティを設定することにより、キャッシュのスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="875f2-109">Specify the scope of caching by setting the <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> property.</span></span>  
  
4.  <span data-ttu-id="875f2-110"><xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> プロパティを設定することにより、サブツリーのビューを指定します。</span><span class="sxs-lookup"><span data-stu-id="875f2-110">Specify the view of the subtree by setting the <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> property.</span></span>  
  
5.  <span data-ttu-id="875f2-111">オブジェクトへの完全な参照を取得しないようにして効率化を図りたい場合は、 <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> プロパティを <xref:System.Windows.Automation.AutomationElementMode.None> に設定します。</span><span class="sxs-lookup"><span data-stu-id="875f2-111">Set the <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> property to <xref:System.Windows.Automation.AutomationElementMode.None> if you wish to increase efficiency by not retrieving a full reference to objects.</span></span> <span data-ttu-id="875f2-112">(このようにすると、これらのオブジェクトから現在の値を取得できなくなります。)</span><span class="sxs-lookup"><span data-stu-id="875f2-112">(This will make it impossible to retrieve current values from those objects.)</span></span>  
  
6.  <span data-ttu-id="875f2-113">使用して、要求をアクティブ化<xref:System.Windows.Automation.CacheRequest.Activate%2A>内、`using`ブロック (`Using` Microsoft Visual Basic .NET で)。</span><span class="sxs-lookup"><span data-stu-id="875f2-113">Activate the request by using <xref:System.Windows.Automation.CacheRequest.Activate%2A> within a `using` block (`Using` in Microsoft Visual Basic .NET).</span></span>  
  
 <span data-ttu-id="875f2-114"><xref:System.Windows.Automation.AutomationElement> オブジェクトの取得後、またはイベントのサブスクライブ後に、 <xref:System.Windows.Automation.CacheRequest.Pop%2A> を使用するか ( <xref:System.Windows.Automation.CacheRequest.Push%2A> を使用した場合)、または <xref:System.Windows.Automation.CacheRequest.Activate%2A>で作成したオブジェクトを破棄することにより、要求を非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="875f2-114">After obtaining <xref:System.Windows.Automation.AutomationElement> objects or subscribing to events, deactivate the request by using <xref:System.Windows.Automation.CacheRequest.Pop%2A> (if <xref:System.Windows.Automation.CacheRequest.Push%2A> was used) or by disposing the object created by <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span> <span data-ttu-id="875f2-115">(使用<xref:System.Windows.Automation.CacheRequest.Activate%2A>で、`using`ブロック (`Using` Microsoft Visual Basic .NET で)。</span><span class="sxs-lookup"><span data-stu-id="875f2-115">(Use <xref:System.Windows.Automation.CacheRequest.Activate%2A> in a `using` block (`Using` in Microsoft Visual Basic .NET).</span></span>  
  
### <a name="cache-automationelement-properties"></a><span data-ttu-id="875f2-116">AutomationElement プロパティのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="875f2-116">Cache AutomationElement Properties</span></span>  
  
1.  <span data-ttu-id="875f2-117"><xref:System.Windows.Automation.CacheRequest> がアクティブな間に、 <xref:System.Windows.Automation.AutomationElement> または <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> を使用して、 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>オブジェクトを取得します。あるいは、 <xref:System.Windows.Automation.AutomationElement> がアクティブな間に登録したイベントのソースとして <xref:System.Windows.Automation.CacheRequest> を取得します</span><span class="sxs-lookup"><span data-stu-id="875f2-117">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="875f2-118">(GetUpdatedCache またはいずれかの <xref:System.Windows.Automation.CacheRequest> メソッドに <xref:System.Windows.Automation.TreeWalker> を渡すことにより、キャッシュを作成することも可能です)。</span><span class="sxs-lookup"><span data-stu-id="875f2-118">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2.  <span data-ttu-id="875f2-119"><xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> を使用するか、または <xref:System.Windows.Automation.AutomationElement.Cached%2A> の <xref:System.Windows.Automation.AutomationElement>プロパティからプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="875f2-119">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> or retrieve a property from the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property of the <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
### <a name="obtain-cached-patterns-and-their-properties"></a><span data-ttu-id="875f2-120">キャッシュされたパターンとプロパティの取得</span><span class="sxs-lookup"><span data-stu-id="875f2-120">Obtain Cached Patterns and Their Properties</span></span>  
  
1.  <span data-ttu-id="875f2-121"><xref:System.Windows.Automation.CacheRequest> がアクティブな間に、 <xref:System.Windows.Automation.AutomationElement> または <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> を使用して、 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>オブジェクトを取得します。あるいは、 <xref:System.Windows.Automation.AutomationElement> がアクティブな間に登録したイベントのソースとして <xref:System.Windows.Automation.CacheRequest> を取得します</span><span class="sxs-lookup"><span data-stu-id="875f2-121">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="875f2-122">(GetUpdatedCache またはいずれかの <xref:System.Windows.Automation.CacheRequest> メソッドに <xref:System.Windows.Automation.TreeWalker> を渡すことにより、キャッシュを作成することも可能です)。</span><span class="sxs-lookup"><span data-stu-id="875f2-122">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2.  <span data-ttu-id="875f2-123">キャッシュされたパターンを取得するために、 <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> または <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="875f2-123">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> to retrieve a cached pattern.</span></span>  
  
3.  <span data-ttu-id="875f2-124">コントロール パターンの `Cached` プロパティからプロパティ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="875f2-124">Retrieve property values from the `Cached` property of the control pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="875f2-125">例</span><span class="sxs-lookup"><span data-stu-id="875f2-125">Example</span></span>  
 <span data-ttu-id="875f2-126">次のコード例は、キャッシュのさまざまな側面を示し、 <xref:System.Windows.Automation.CacheRequest.Activate%2A> を使用して <xref:System.Windows.Automation.CacheRequest>をアクティブ化しています。</span><span class="sxs-lookup"><span data-stu-id="875f2-126">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Activate%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
 [!code-csharp[UIAClient_snip#107](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#107)]
 [!code-vb[UIAClient_snip#107](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#107)]  
  
## <a name="example"></a><span data-ttu-id="875f2-127">例</span><span class="sxs-lookup"><span data-stu-id="875f2-127">Example</span></span>  
 <span data-ttu-id="875f2-128">次のコード例は、キャッシュのさまざまな側面を示し、 <xref:System.Windows.Automation.CacheRequest.Push%2A> を使用して <xref:System.Windows.Automation.CacheRequest>をアクティブ化しています。</span><span class="sxs-lookup"><span data-stu-id="875f2-128">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Push%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span> <span data-ttu-id="875f2-129">キャッシュ要求を入れ子にする場合を除き、 <xref:System.Windows.Automation.CacheRequest.Activate%2A>を使用する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="875f2-129">Except when you wish to nest cache requests, it is preferable to use <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#108](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#108)]
 [!code-vb[UIAClient_snip#108](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#108)]  
  
## <a name="see-also"></a><span data-ttu-id="875f2-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="875f2-130">See also</span></span>
- [<span data-ttu-id="875f2-131">UI オートメーション クライアントにおけるキャッシュ</span><span class="sxs-lookup"><span data-stu-id="875f2-131">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)

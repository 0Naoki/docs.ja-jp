---
title: UI オートメーション MultipleView コントロール パターンの実装
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: edef213c0f4d43a15b7c6842ef6c62e95544da66
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039499"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a><span data-ttu-id="3a228-102">UI オートメーション MultipleView コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="3a228-102">Implementing the UI Automation MultipleView Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="3a228-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="3a228-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3a228-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI Automation (Windows のオートメーション API: UI オートメーション)](https://go.microsoft.com/fwlink/?LinkID=156746)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a228-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="3a228-105">このトピックでは、イベントおよびプロパティに関する情報など、 <xref:System.Windows.Automation.Provider.IMultipleViewProvider>の実装のためのガイドラインと規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a228-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, including information about events and properties.</span></span> <span data-ttu-id="3a228-106">その他のリファレンスへのリンクは、トピックの最後に記載します。</span><span class="sxs-lookup"><span data-stu-id="3a228-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="3a228-107"><xref:System.Windows.Automation.MultipleViewPattern> コントロール パターンは、同じ情報セットまたは子コントロールの複数の表現を提供し、それらの表現を切り替えることができるコントロールをサポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="3a228-107">The <xref:System.Windows.Automation.MultipleViewPattern> control pattern is used to support controls that provide, and are able to switch between, multiple representations of the same set of information or child controls.</span></span>  
  
 <span data-ttu-id="3a228-108">複数のビューを表示するコントロールの例としては、リストビュー (コンテンツをサムネイル、タイル、アイコン、詳細として表示できる)、[!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] グラフ (円、線、横棒、セルの値など)、[!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] ドキュメント (標準、Web レイアウト、印刷レイアウト) などがあります。閲覧レイアウト、アウトライン)、Microsoft Outlook カレンダー (年、月、週、日)、および Microsoft Windows Media Player スキン。</span><span class="sxs-lookup"><span data-stu-id="3a228-108">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] charts (pie, line, bar, cell value with a formula), [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] documents (normal, Web layout, print layout, reading layout, outline), Microsoft Outlook calendar (year, month, week, day), and Microsoft Windows Media Player skins.</span></span> <span data-ttu-id="3a228-109">サポートされるビューはコントロールの開発者によって決定され、各コントロールに固有です。</span><span class="sxs-lookup"><span data-stu-id="3a228-109">The supported views are determined by the control developer and are specific to each control.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="3a228-110">実装のガイドラインと規則</span><span class="sxs-lookup"><span data-stu-id="3a228-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="3a228-111">Multiple View コントロール パターンを実装する場合は、次のガイドラインと規則にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="3a228-111">When implementing the Multiple View control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="3a228-112">現在のビューを管理するコンテナーが現在のビューを提供するコントロールとは異なる場合は、現在のビューを管理するためのコンテナーにも<xref:System.Windows.Automation.Provider.IMultipleViewProvider> を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a228-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> should also be implemented on a container that manages the current view if it is different from a control that provides the current view.</span></span> <span data-ttu-id="3a228-113">たとえば、Windows エクスプローラーには現在のフォルダーのコンテンツの List コントロールが含まれていますが、そのコントロールのビューは Windows エクスプローラーのアプリケーションから管理されています。</span><span class="sxs-lookup"><span data-stu-id="3a228-113">For example, Windows Explorer contains a List control for the current folder content while the view for the control is managed from the Windows Explorer application.</span></span>  
  
- <span data-ttu-id="3a228-114">自身のコンテンツを並べ替えることができるコントロールは、複数のビューをサポートしているとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="3a228-114">A control that is able to sort its content is not considered to support multiple views.</span></span>  
  
- <span data-ttu-id="3a228-115">ビューのコレクションは、インスタンス間で同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a228-115">The collection of views must be identical across instances.</span></span>  
  
- <span data-ttu-id="3a228-116">ビューの名前は、読み上げ、ブライユ点字、その他の人間が判読できるアプリケーションでの使用に適した名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a228-116">View names must be suitable for use in Text to Speech, Braille, and other human-readable applications.</span></span>  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>   
## <a name="required-members-for-imultipleviewprovider"></a><span data-ttu-id="3a228-117">IMultipleViewProvider の必須メンバー</span><span class="sxs-lookup"><span data-stu-id="3a228-117">Required Members for IMultipleViewProvider</span></span>  
 <span data-ttu-id="3a228-118">IMultipleViewProvider の実装には、次のプロパティとメソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="3a228-118">The following properties and methods are required for implementing IMultipleViewProvider.</span></span>  
  
|<span data-ttu-id="3a228-119">必須メンバー</span><span class="sxs-lookup"><span data-stu-id="3a228-119">Required members</span></span>|<span data-ttu-id="3a228-120">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="3a228-120">Member type</span></span>|<span data-ttu-id="3a228-121">ノート</span><span class="sxs-lookup"><span data-stu-id="3a228-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|<span data-ttu-id="3a228-122">property</span><span class="sxs-lookup"><span data-stu-id="3a228-122">Property</span></span>|<span data-ttu-id="3a228-123">None</span><span class="sxs-lookup"><span data-stu-id="3a228-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|<span data-ttu-id="3a228-124">メソッド</span><span class="sxs-lookup"><span data-stu-id="3a228-124">Method</span></span>|<span data-ttu-id="3a228-125">None</span><span class="sxs-lookup"><span data-stu-id="3a228-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|<span data-ttu-id="3a228-126">メソッド</span><span class="sxs-lookup"><span data-stu-id="3a228-126">Method</span></span>|<span data-ttu-id="3a228-127">None</span><span class="sxs-lookup"><span data-stu-id="3a228-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|<span data-ttu-id="3a228-128">メソッド</span><span class="sxs-lookup"><span data-stu-id="3a228-128">Method</span></span>|<span data-ttu-id="3a228-129">None</span><span class="sxs-lookup"><span data-stu-id="3a228-129">None</span></span>|  
  
 <span data-ttu-id="3a228-130">このコントロールのパターンに関連付けられているイベントはありません。</span><span class="sxs-lookup"><span data-stu-id="3a228-130">There are no events associated with this control pattern.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="3a228-131">例外</span><span class="sxs-lookup"><span data-stu-id="3a228-131">Exceptions</span></span>  
 <span data-ttu-id="3a228-132">プロバイダーは、次の例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a228-132">Provider must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="3a228-133">例外の種類</span><span class="sxs-lookup"><span data-stu-id="3a228-133">Exception type</span></span>|<span data-ttu-id="3a228-134">条件</span><span class="sxs-lookup"><span data-stu-id="3a228-134">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="3a228-135"><xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> または <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> が、サポートされているビュー コレクションのメンバーではないパラメーターで呼び出された場合。</span><span class="sxs-lookup"><span data-stu-id="3a228-135">When either <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> or <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> is called with a parameter that is not a member of the supported views collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a228-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a228-136">See also</span></span>

- [<span data-ttu-id="3a228-137">UI Automation コントロール パターンの概要</span><span class="sxs-lookup"><span data-stu-id="3a228-137">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="3a228-138">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="3a228-138">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="3a228-139">クライアントの UI オートメーション コントロール パターン</span><span class="sxs-lookup"><span data-stu-id="3a228-139">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="3a228-140">UI Automation ツリーの概要</span><span class="sxs-lookup"><span data-stu-id="3a228-140">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="3a228-141">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="3a228-141">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)

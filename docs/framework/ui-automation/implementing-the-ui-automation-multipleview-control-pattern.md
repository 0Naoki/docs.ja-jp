---
title: UI オートメーション MultipleView コントロール パターンの実装
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: 5c875794a3d6fb0325bf282bc0f4b903aa29de07
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674290"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a><span data-ttu-id="b4ba9-102">UI オートメーション MultipleView コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="b4ba9-102">Implementing the UI Automation MultipleView Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="b4ba9-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b4ba9-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="b4ba9-105">このトピックでは、イベントおよびプロパティに関する情報など、 <xref:System.Windows.Automation.Provider.IMultipleViewProvider>の実装のためのガイドラインと規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, including information about events and properties.</span></span> <span data-ttu-id="b4ba9-106">その他のリファレンスへのリンクは、トピックの最後に記載します。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="b4ba9-107"><xref:System.Windows.Automation.MultipleViewPattern> コントロール パターンは、同じ情報セットまたは子コントロールの複数の表現を提供し、それらの表現を切り替えることができるコントロールをサポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-107">The <xref:System.Windows.Automation.MultipleViewPattern> control pattern is used to support controls that provide, and are able to switch between, multiple representations of the same set of information or child controls.</span></span>  
  
 <span data-ttu-id="b4ba9-108">複数のビューを表示できるコントロールの例には、リスト ビュー (サムネイル、タイル、アイコン、または詳細の形でコンテンツを表示できる)、 [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] チャート (円、線、棒、式を含むセル値)、 [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] 文書 (標準、Web レイアウト、印刷レイアウト、閲覧レイアウト、アウトライン)、 [!INCLUDE[TLA#tla_outlook](../../../includes/tlasharptla-outlook-md.md)] カレンダー (年、月、週、日)、 [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] スキンなどがあります。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-108">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] charts (pie, line, bar, cell value with a formula), [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] documents (normal, Web layout, print layout, reading layout, outline), [!INCLUDE[TLA#tla_outlook](../../../includes/tlasharptla-outlook-md.md)] calendar (year, month, week, day), and [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] skins.</span></span> <span data-ttu-id="b4ba9-109">サポートされるビューはコントロールの開発者によって決定され、各コントロールに固有です。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-109">The supported views are determined by the control developer and are specific to each control.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="b4ba9-110">実装のガイドラインと規則</span><span class="sxs-lookup"><span data-stu-id="b4ba9-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="b4ba9-111">Multiple View コントロール パターンを実装する場合は、次のガイドラインと規則にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-111">When implementing the Multiple View control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="b4ba9-112">現在のビューを管理するコンテナーが現在のビューを提供するコントロールとは異なる場合は、現在のビューを管理するためのコンテナーにも<xref:System.Windows.Automation.Provider.IMultipleViewProvider> を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> should also be implemented on a container that manages the current view if it is different from a control that provides the current view.</span></span> <span data-ttu-id="b4ba9-113">たとえば、Windows エクスプローラーには現在のフォルダーのコンテンツの List コントロールが含まれていますが、そのコントロールのビューは Windows エクスプローラーのアプリケーションから管理されています。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-113">For example, Windows Explorer contains a List control for the current folder content while the view for the control is managed from the Windows Explorer application.</span></span>  
  
-   <span data-ttu-id="b4ba9-114">自身のコンテンツを並べ替えることができるコントロールは、複数のビューをサポートしているとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-114">A control that is able to sort its content is not considered to support multiple views.</span></span>  
  
-   <span data-ttu-id="b4ba9-115">ビューのコレクションは、インスタンス間で同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-115">The collection of views must be identical across instances.</span></span>  
  
-   <span data-ttu-id="b4ba9-116">ビューの名前は、読み上げ、ブライユ点字、その他の人間が判読できるアプリケーションでの使用に適した名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-116">View names must be suitable for use in Text to Speech, Braille, and other human-readable applications.</span></span>  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>   
## <a name="required-members-for-imultipleviewprovider"></a><span data-ttu-id="b4ba9-117">IMultipleViewProvider の必須メンバー</span><span class="sxs-lookup"><span data-stu-id="b4ba9-117">Required Members for IMultipleViewProvider</span></span>  
 <span data-ttu-id="b4ba9-118">IMultipleViewProvider の実装には、次のプロパティとメソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-118">The following properties and methods are required for implementing IMultipleViewProvider.</span></span>  
  
|<span data-ttu-id="b4ba9-119">必須メンバー</span><span class="sxs-lookup"><span data-stu-id="b4ba9-119">Required members</span></span>|<span data-ttu-id="b4ba9-120">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="b4ba9-120">Member type</span></span>|<span data-ttu-id="b4ba9-121">メモ</span><span class="sxs-lookup"><span data-stu-id="b4ba9-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|<span data-ttu-id="b4ba9-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b4ba9-122">Property</span></span>|<span data-ttu-id="b4ba9-123">なし</span><span class="sxs-lookup"><span data-stu-id="b4ba9-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|<span data-ttu-id="b4ba9-124">メソッド</span><span class="sxs-lookup"><span data-stu-id="b4ba9-124">Method</span></span>|<span data-ttu-id="b4ba9-125">なし</span><span class="sxs-lookup"><span data-stu-id="b4ba9-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|<span data-ttu-id="b4ba9-126">メソッド</span><span class="sxs-lookup"><span data-stu-id="b4ba9-126">Method</span></span>|<span data-ttu-id="b4ba9-127">なし</span><span class="sxs-lookup"><span data-stu-id="b4ba9-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|<span data-ttu-id="b4ba9-128">メソッド</span><span class="sxs-lookup"><span data-stu-id="b4ba9-128">Method</span></span>|<span data-ttu-id="b4ba9-129">なし</span><span class="sxs-lookup"><span data-stu-id="b4ba9-129">None</span></span>|  
  
 <span data-ttu-id="b4ba9-130">このコントロールのパターンに関連付けられているイベントはありません。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-130">There are no events associated with this control pattern.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="b4ba9-131">例外</span><span class="sxs-lookup"><span data-stu-id="b4ba9-131">Exceptions</span></span>  
 <span data-ttu-id="b4ba9-132">プロバイダーは、次の例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-132">Provider must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="b4ba9-133">例外の種類</span><span class="sxs-lookup"><span data-stu-id="b4ba9-133">Exception type</span></span>|<span data-ttu-id="b4ba9-134">条件</span><span class="sxs-lookup"><span data-stu-id="b4ba9-134">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="b4ba9-135"><xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> または <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> が、サポートされているビュー コレクションのメンバーではないパラメーターで呼び出された場合。</span><span class="sxs-lookup"><span data-stu-id="b4ba9-135">When either <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> or <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> is called with a parameter that is not a member of the supported views collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4ba9-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4ba9-136">See also</span></span>
- [<span data-ttu-id="b4ba9-137">UI Automation コントロール パターンの概要</span><span class="sxs-lookup"><span data-stu-id="b4ba9-137">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="b4ba9-138">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="b4ba9-138">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="b4ba9-139">クライアントの UI オートメーション コントロール パターン</span><span class="sxs-lookup"><span data-stu-id="b4ba9-139">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="b4ba9-140">UI Automation ツリーの概要</span><span class="sxs-lookup"><span data-stu-id="b4ba9-140">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="b4ba9-141">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="b4ba9-141">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)

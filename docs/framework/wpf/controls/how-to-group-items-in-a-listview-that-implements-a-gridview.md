---
title: '方法: GridView を実装する ListView の項目をグループ化する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: 3989f0fcdaf2e3d3003aca9feb27cbf02f949389
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364477"
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="8536e-102">方法: GridView を実装する ListView の項目をグループ化する</span><span class="sxs-lookup"><span data-stu-id="8536e-102">How to: Group Items in a ListView That Implements a GridView</span></span>
<span data-ttu-id="8536e-103">この例では、グループ内の項目の表示、<xref:System.Windows.Controls.GridView>の表示モード、<xref:System.Windows.Controls.ListView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="8536e-103">This example shows how to display groups of items in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8536e-104">例</span><span class="sxs-lookup"><span data-stu-id="8536e-104">Example</span></span>  
 <span data-ttu-id="8536e-105">内の項目のグループを表示する、 <xref:System.Windows.Controls.ListView>、定義、<xref:System.Windows.Data.CollectionViewSource>します。</span><span class="sxs-lookup"><span data-stu-id="8536e-105">To display groups of items in a <xref:System.Windows.Controls.ListView>, define a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="8536e-106">次の例は、<xref:System.Windows.Data.CollectionViewSource>の値に基づいてデータ項目をグループ化、`Catalog`データ フィールド。</span><span class="sxs-lookup"><span data-stu-id="8536e-106">The following example shows a <xref:System.Windows.Data.CollectionViewSource> that groups data items according to the value of the `Catalog` data field.</span></span>  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 <span data-ttu-id="8536e-107">次の例のセット、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>の<xref:System.Windows.Controls.ListView>を<xref:System.Windows.Data.CollectionViewSource>前の例を定義します。</span><span class="sxs-lookup"><span data-stu-id="8536e-107">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> to the <xref:System.Windows.Data.CollectionViewSource> that the previous example defines.</span></span> <span data-ttu-id="8536e-108">また、<xref:System.Windows.Controls.ItemsControl.GroupStyle%2A>を実装する、<xref:System.Windows.Controls.Expander>コントロール。</span><span class="sxs-lookup"><span data-stu-id="8536e-108">The example also defines a <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> that implements an <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a><span data-ttu-id="8536e-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="8536e-109">See also</span></span>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="8536e-110">方法トピック</span><span class="sxs-lookup"><span data-stu-id="8536e-110">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="8536e-111">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="8536e-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="8536e-112">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="8536e-112">GridView Overview</span></span>](gridview-overview.md)

---
title: '方法: 階層データでマスター詳細パターンを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e0bbb24b07fdc1c362e2be43d69d189defbc27a4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59346185"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="38b8b-102">方法: 階層データでマスター詳細パターンを使用する</span><span class="sxs-lookup"><span data-stu-id="38b8b-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="38b8b-103">この例では、マスター/詳細シナリオを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="38b8b-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38b8b-104">例</span><span class="sxs-lookup"><span data-stu-id="38b8b-104">Example</span></span>  
 <span data-ttu-id="38b8b-105">この例で`LeagueList`のコレクションである`Leagues`します。</span><span class="sxs-lookup"><span data-stu-id="38b8b-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="38b8b-106">各`League`が、`Name`と一連の`Divisions`、および各`Division`名は、一連の`Teams`します。</span><span class="sxs-lookup"><span data-stu-id="38b8b-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="38b8b-107">各`Team`チームの名前します。</span><span class="sxs-lookup"><span data-stu-id="38b8b-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="38b8b-108">次に示すのは、この例のスクリーンショットです。</span><span class="sxs-lookup"><span data-stu-id="38b8b-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="38b8b-109">`Divisions` <xref:System.Windows.Controls.ListBox>の選択項目が自動的に追跡、 `Leagues` <xref:System.Windows.Controls.ListBox>し、対応するデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="38b8b-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="38b8b-110">`Teams` <xref:System.Windows.Controls.ListBox>他の 2 つの選択項目を追跡<xref:System.Windows.Controls.ListBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="38b8b-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![マスターを示すスクリーン ショット&#45;詳細のシナリオ例。](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="38b8b-112">この例では、2 つの処理は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="38b8b-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="38b8b-113">3 つ<xref:System.Windows.Controls.ListBox>コントロールは、同じソースにバインドします。</span><span class="sxs-lookup"><span data-stu-id="38b8b-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="38b8b-114">設定する、<xref:System.Windows.Data.Binding.Path%2A>するデータのレベルを指定するバインドのプロパティ、<xref:System.Windows.Controls.ListBox>を表示します。</span><span class="sxs-lookup"><span data-stu-id="38b8b-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="38b8b-115">設定する必要があります、<xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>プロパティを`true`で、<xref:System.Windows.Controls.ListBox>コントロールを追跡して選択します。</span><span class="sxs-lookup"><span data-stu-id="38b8b-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="38b8b-116">このプロパティ設定によって、選択した項目として常に設定されている、<xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>します。</span><span class="sxs-lookup"><span data-stu-id="38b8b-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="38b8b-117">また場合、<xref:System.Windows.Controls.ListBox>からデータを取得しますが、<xref:System.Windows.Data.CollectionViewSource>の選択と通貨を自動的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="38b8b-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="38b8b-118">使用する場合に、この手法は若干異なります[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]データ。</span><span class="sxs-lookup"><span data-stu-id="38b8b-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="38b8b-119">例については、次を参照してください。[階層 XML データでマスター詳細パターンを使用して](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="38b8b-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38b8b-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="38b8b-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="38b8b-121">コレクションにバインドして選択に基づく情報を表示する</span><span class="sxs-lookup"><span data-stu-id="38b8b-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="38b8b-122">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="38b8b-122">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="38b8b-123">データ テンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="38b8b-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="38b8b-124">方法トピック</span><span class="sxs-lookup"><span data-stu-id="38b8b-124">How-to Topics</span></span>](data-binding-how-to-topics.md)

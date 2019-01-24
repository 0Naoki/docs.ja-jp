---
title: '方法: ビュー内のデータをフィルター処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: 33af517c086f8f89cc06a1de7a2979c5b1624109
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689325"
---
# <a name="how-to-filter-data-in-a-view"></a><span data-ttu-id="ee782-102">方法: ビュー内のデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="ee782-102">How to: Filter Data in a View</span></span>
<span data-ttu-id="ee782-103">この例では、ビュー内のデータをフィルター処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ee782-103">This example shows how to filter data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee782-104">例</span><span class="sxs-lookup"><span data-stu-id="ee782-104">Example</span></span>  
 <span data-ttu-id="ee782-105">フィルターを作成するには、フィルター処理のロジックを提供するメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="ee782-105">To create a filter, define a method that provides the filtering logic.</span></span> <span data-ttu-id="ee782-106">メソッドは、コールバックとして使用され、型のパラメーターを受け入れる`object`します。</span><span class="sxs-lookup"><span data-stu-id="ee782-106">The method is used as a callback and accepts a parameter of type `object`.</span></span> <span data-ttu-id="ee782-107">次のメソッドは、すべてを返します、`Order`オブジェクトを`filled`プロパティを"No"に、オブジェクトの残りの部分でフィルター処理を設定します。</span><span class="sxs-lookup"><span data-stu-id="ee782-107">The following method returns all the `Order` objects with the `filled` property set to "No", filtering out the rest of the objects.</span></span>  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="ee782-108">次の例に示すように、フィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="ee782-108">You can then apply the filter, as shown in the following example.</span></span> <span data-ttu-id="ee782-109">この例で`myCollectionView`は、<xref:System.Windows.Data.ListCollectionView>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ee782-109">In this example, `myCollectionView` is a <xref:System.Windows.Data.ListCollectionView> object.</span></span>  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 <span data-ttu-id="ee782-110">フィルター処理を元に戻すには、設定することができます、<xref:System.Windows.Data.CollectionView.Filter%2A>プロパティを`null`:</span><span class="sxs-lookup"><span data-stu-id="ee782-110">To undo filtering, you can set the <xref:System.Windows.Data.CollectionView.Filter%2A> property to `null`:</span></span>  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 <span data-ttu-id="ee782-111">ビューを取得または作成する方法については、次を参照してください。[データ コレクションの既定のビューを取得](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)します。</span><span class="sxs-lookup"><span data-stu-id="ee782-111">For information about how to create or obtain a view, see [Get the Default View of a Data Collection](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="ee782-112">完全な例では、次を参照してください。[並べ替えとビューのサンプル内の項目をフィルター処理](https://go.microsoft.com/fwlink/?LinkID=160040)します。</span><span class="sxs-lookup"><span data-stu-id="ee782-112">For the complete example, see [Sorting and Filtering Items in a View Sample](https://go.microsoft.com/fwlink/?LinkID=160040).</span></span>  
  
 <span data-ttu-id="ee782-113">ビュー オブジェクトの場合、<xref:System.Windows.Data.CollectionViewSource>オブジェクトのイベント ハンドラーを設定してフィルター処理のロジックを適用する、<xref:System.Windows.Data.CollectionViewSource.Filter>イベント。</span><span class="sxs-lookup"><span data-stu-id="ee782-113">If your view object comes from a <xref:System.Windows.Data.CollectionViewSource> object, you apply filtering logic by setting an event handler for the <xref:System.Windows.Data.CollectionViewSource.Filter> event.</span></span> <span data-ttu-id="ee782-114">次の例では、`listingDataView`のインスタンスである<xref:System.Windows.Data.CollectionViewSource>します。</span><span class="sxs-lookup"><span data-stu-id="ee782-114">In the following example, `listingDataView` is an instance of <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 <span data-ttu-id="ee782-115">この例の実装を次に示します`ShowOnlyBargainsFilter`フィルター イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="ee782-115">The following shows the implementation of the example `ShowOnlyBargainsFilter` filter event handler.</span></span> <span data-ttu-id="ee782-116">このイベント ハンドラーを使用して、<xref:System.Windows.Data.FilterEventArgs.Accepted%2A>プロパティをフィルターで除外`AuctionItem`を持つオブジェクトを`CurrentPrice`25 ドル以上。</span><span class="sxs-lookup"><span data-stu-id="ee782-116">This event handler uses the <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> property to filter out `AuctionItem` objects that have a `CurrentPrice` of $25 or greater.</span></span>  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ee782-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee782-117">See also</span></span>
- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [<span data-ttu-id="ee782-118">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="ee782-118">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="ee782-119">ビュー内のデータの並べ替え</span><span class="sxs-lookup"><span data-stu-id="ee782-119">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="ee782-120">方法トピック</span><span class="sxs-lookup"><span data-stu-id="ee782-120">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

---
title: '方法: データ CollectionView のオブジェクト間を移動する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: c7de491a76ba6f8d5164c91f8c20bea4a8fa56d7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688403"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="b995c-102">方法: データ CollectionView のオブジェクト間を移動する</span><span class="sxs-lookup"><span data-stu-id="b995c-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="b995c-103">ビューでは、並べ替え、フィルター処理、またはグループ化に応じて、さまざまな方法で表示する同じデータ収集を許可します。</span><span class="sxs-lookup"><span data-stu-id="b995c-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="b995c-104">ビューは、現在のレコード ポインターの概念を提供し、ポインターの移動を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b995c-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="b995c-105">この例で提供される機能を使用してデータ コレクションのオブジェクト間を移動するほか、現在のオブジェクトを取得する方法を示しています、<xref:System.Windows.Data.CollectionView>クラス。</span><span class="sxs-lookup"><span data-stu-id="b995c-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b995c-106">例</span><span class="sxs-lookup"><span data-stu-id="b995c-106">Example</span></span>  
 <span data-ttu-id="b995c-107">この例で`myCollectionView`は、<xref:System.Windows.Data.CollectionView>ビューでバインドされたコレクションであるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b995c-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="b995c-108">次の例では、`OnButton`のイベント ハンドラー、`Previous`と`Next`により、ユーザー データのコレクションを移動するボタンであるアプリケーションでは、ボタン。</span><span class="sxs-lookup"><span data-stu-id="b995c-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="b995c-109">なお、<xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A>と<xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A>プロパティを報告するかどうか、現在のレコード ポインターに来た、先頭と末尾のリストのそれぞれためを<xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A>と<xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A>として適切に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="b995c-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="b995c-110"><xref:System.Windows.Data.CollectionView.CurrentItem%2A>としてキャストは、ビューのプロパティ、`Order`コレクション内の現在の注文アイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="b995c-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="b995c-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b995c-111">See also</span></span>
- [<span data-ttu-id="b995c-112">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="b995c-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="b995c-113">ビュー内のデータの並べ替え</span><span class="sxs-lookup"><span data-stu-id="b995c-113">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="b995c-114">ビュー内のデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="b995c-114">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="b995c-115">XAML でビューを使用してデータの並べ替えおよびグループ化を行う</span><span class="sxs-lookup"><span data-stu-id="b995c-115">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="b995c-116">方法トピック</span><span class="sxs-lookup"><span data-stu-id="b995c-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

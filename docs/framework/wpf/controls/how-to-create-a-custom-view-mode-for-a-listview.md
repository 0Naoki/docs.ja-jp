---
title: '方法 : ListView のカスタム表示モードを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 239fb2e9a364bd0265ff7cf644ee296878280cf3
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43799711"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="57d9c-102">方法 : ListView のカスタム表示モードを作成する</span><span class="sxs-lookup"><span data-stu-id="57d9c-102">How to: Create a Custom View Mode for a ListView</span></span>
<span data-ttu-id="57d9c-103">この例は、カスタムを作成する方法を示しています。<xref:System.Windows.Controls.ListView.View%2A>のモードを<xref:System.Windows.Controls.ListView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="57d9c-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57d9c-104">例</span><span class="sxs-lookup"><span data-stu-id="57d9c-104">Example</span></span>  
 <span data-ttu-id="57d9c-105">使用する必要があります、<xref:System.Windows.Controls.ViewBase>クラス用のカスタム ビューを作成するときに、<xref:System.Windows.Controls.ListView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="57d9c-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="57d9c-106">次の例では、呼び出される表示モード`PlainView`から派生、<xref:System.Windows.Controls.ViewBase>クラス。</span><span class="sxs-lookup"><span data-stu-id="57d9c-106">The following example shows a view mode that is called `PlainView`, which is derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="57d9c-107">カスタム ビューには、スタイルを適用するには、使用、<xref:System.Windows.Style>クラス。</span><span class="sxs-lookup"><span data-stu-id="57d9c-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="57d9c-108">次の例では、定義、<xref:System.Windows.Style>の`PlainView`表示モード。</span><span class="sxs-lookup"><span data-stu-id="57d9c-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="57d9c-109">前の例では、このスタイルが設定の値として、<xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A>プロパティに対して定義されている`PlainView`します。</span><span class="sxs-lookup"><span data-stu-id="57d9c-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that is defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="57d9c-110">カスタム表示モードでは、データのレイアウトを定義するには、定義、<xref:System.Windows.DataTemplate>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="57d9c-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="57d9c-111">次の例では、定義、<xref:System.Windows.DataTemplate>データを表示する使用できる、`PlainView`表示モード。</span><span class="sxs-lookup"><span data-stu-id="57d9c-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="57d9c-112">次の例は、定義する方法を示します、<xref:System.Windows.ResourceKey>の`PlainView`表示モードを使用する、<xref:System.Windows.DataTemplate>前の例で定義されています。</span><span class="sxs-lookup"><span data-stu-id="57d9c-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="57d9c-113">A<xref:System.Windows.Controls.ListView>設定した場合、コントロールがカスタム ビューを使用できます、<xref:System.Windows.Controls.ListView.View%2A>プロパティをリソース キー。</span><span class="sxs-lookup"><span data-stu-id="57d9c-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="57d9c-114">次の例は、指定する方法を示します`PlainView`の表示モードとして、<xref:System.Windows.Controls.ListView>します。</span><span class="sxs-lookup"><span data-stu-id="57d9c-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="57d9c-115">サンプル全体については、次を参照してください。 [ListView with Multiple Views Sample](https://go.microsoft.com/fwlink/?LinkID=160013)します。</span><span class="sxs-lookup"><span data-stu-id="57d9c-115">For the complete sample, see [ListView with Multiple Views Sample](https://go.microsoft.com/fwlink/?LinkID=160013).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57d9c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="57d9c-116">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="57d9c-117">方法トピック</span><span class="sxs-lookup"><span data-stu-id="57d9c-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="57d9c-118">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="57d9c-118">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="57d9c-119">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="57d9c-119">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)

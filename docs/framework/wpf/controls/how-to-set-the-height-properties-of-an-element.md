---
title: '方法: 要素の Height プロパティを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 608f74afd95ce03b3ecf71819c2181a9728b25af
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356293"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="ffdd9-102">方法: 要素の Height プロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="ffdd9-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="ffdd9-103">例</span><span class="sxs-lookup"><span data-stu-id="ffdd9-103">Example</span></span>  
 <span data-ttu-id="ffdd9-104">この例は、レンダリングの 4 つの高さに関連するプロパティの間での動作の違いを視覚的にでは[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ffdd9-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="ffdd9-105"><xref:System.Windows.FrameworkElement>クラスは、要素の高さの特性を記述する次の 4 つのプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="ffdd9-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="ffdd9-106">これら 4 つのプロパティが競合すること、および優先する値は次のように決定されます、:<xref:System.Windows.FrameworkElement.MinHeight%2A>値よりも優先、<xref:System.Windows.FrameworkElement.MaxHeight%2A>値で、さらによりも優先、<xref:System.Windows.FrameworkElement.Height%2A>値。</span><span class="sxs-lookup"><span data-stu-id="ffdd9-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="ffdd9-107">4 番目のプロパティ、<xref:System.Windows.FrameworkElement.ActualHeight%2A>は読み取り専用、および、レイアウト プロセスとの相互作用によって決定される実際の高さを報告します。</span><span class="sxs-lookup"><span data-stu-id="ffdd9-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="ffdd9-108">次[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]例の描画、<xref:System.Windows.Shapes.Rectangle>要素 (`rect1`) の子として<xref:System.Windows.Controls.Canvas>します。</span><span class="sxs-lookup"><span data-stu-id="ffdd9-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="ffdd9-109">高さのプロパティを変更することができます、<xref:System.Windows.Shapes.Rectangle>一連を使用して<xref:System.Windows.Controls.ListBox>要素のプロパティ値を表す<xref:System.Windows.FrameworkElement.MinHeight%2A>、 <xref:System.Windows.FrameworkElement.MaxHeight%2A>、および<xref:System.Windows.FrameworkElement.Height%2A>します。</span><span class="sxs-lookup"><span data-stu-id="ffdd9-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="ffdd9-110">この方法で、各プロパティの優先順位が視覚的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffdd9-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="ffdd9-111">次の分離コード例は、イベントを処理する、<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="ffdd9-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="ffdd9-112">各ハンドラーはから入力を受け取り、 <xref:System.Windows.Controls.ListBox>、として値を解析し、 <xref:System.Double>、し、指定した高さに関連するプロパティに値が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ffdd9-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="ffdd9-113">高さの値も文字列に変換し、さまざまなに書き込まれる<xref:System.Windows.Controls.TextBlock>要素 (それらの要素の定義は選択した XAML では表示されません)。</span><span class="sxs-lookup"><span data-stu-id="ffdd9-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="ffdd9-114">サンプル全体については、[高さのプロパティのサンプル](https://go.microsoft.com/fwlink/?LinkID=159993)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffdd9-114">For the complete sample, see [Height Properties Sample](https://go.microsoft.com/fwlink/?LinkID=159993).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffdd9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffdd9-115">See also</span></span>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [<span data-ttu-id="ffdd9-116">要素の Width プロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="ffdd9-116">Set the Width Properties of an Element</span></span>](how-to-set-the-width-properties-of-an-element.md)
- [<span data-ttu-id="ffdd9-117">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="ffdd9-117">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="ffdd9-118">高さのプロパティのサンプル</span><span class="sxs-lookup"><span data-stu-id="ffdd9-118">Height Properties Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159993)

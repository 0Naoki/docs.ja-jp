---
title: '方法: ポリライン要素を使用してポリラインを描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 4f55ecc206be0ef4947923047e796c36131c70ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003211"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="c3e47-102">方法: ポリライン要素を使用してポリラインを描画する</span><span class="sxs-lookup"><span data-stu-id="c3e47-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="c3e47-103">この例を使用して一連の接続線、多角形を描画する方法を示しています、<xref:System.Windows.Shapes.Polyline>要素。</span><span class="sxs-lookup"><span data-stu-id="c3e47-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="c3e47-104">ポリラインを描画するために作成、<xref:System.Windows.Shapes.Polyline>要素と使用してその<xref:System.Windows.Shapes.Polyline.Points%2A>図形の頂点を指定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c3e47-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="c3e47-105">最後に、使用して、<xref:System.Windows.Shapes.Shape.Stroke%2A>と<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>線なしの行が表示されないため、ポリラインを記述するプロパティが説明します。</span><span class="sxs-lookup"><span data-stu-id="c3e47-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3e47-106"><xref:System.Windows.Shapes.Polyline>要素は、閉じた図形ではありません、<xref:System.Windows.Shapes.Shape.Fill%2A>プロパティも何も起こりません、図形の輪郭を意図的に閉じた場合でもです。</span><span class="sxs-lookup"><span data-stu-id="c3e47-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="c3e47-107">閉じた図形を作成する、<xref:System.Windows.Shapes.Shape.Fill%2A>を使用して、<xref:System.Windows.Shapes.Polygon>要素。</span><span class="sxs-lookup"><span data-stu-id="c3e47-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="c3e47-108">次の例では、2 つの描画<xref:System.Windows.Shapes.Polyline>内の要素を<xref:System.Windows.Controls.Canvas>します。</span><span class="sxs-lookup"><span data-stu-id="c3e47-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3e47-109">例</span><span class="sxs-lookup"><span data-stu-id="c3e47-109">Example</span></span>  
 <span data-ttu-id="c3e47-110">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ポイントの有効な構文がコンマで区切られた x 座標と y 座標のペアのスペースで区切られた一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="c3e47-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="c3e47-111">この例を使用しますが、<xref:System.Windows.Controls.Canvas>ポリラインを格納する際ポリライン要素 (およびその他のすべての図形要素) のいずれか<xref:System.Windows.Controls.Panel>または<xref:System.Windows.Controls.Control>テキスト以外のコンテンツをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c3e47-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="c3e47-112">この例より大きなサンプルの一部です。サンプル全体については、次を参照してください。 [Shape 要素のサンプル](https://go.microsoft.com/fwlink/?LinkID=160037)します。</span><span class="sxs-lookup"><span data-stu-id="c3e47-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e47-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3e47-113">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="c3e47-114">Shape 要素のサンプル</span><span class="sxs-lookup"><span data-stu-id="c3e47-114">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
- [<span data-ttu-id="c3e47-115">WPF での図形と基本描画の概要</span><span class="sxs-lookup"><span data-stu-id="c3e47-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)

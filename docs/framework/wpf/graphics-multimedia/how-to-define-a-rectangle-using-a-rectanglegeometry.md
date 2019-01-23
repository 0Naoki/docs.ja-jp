---
title: '方法: RectangleGeometry を使用して四角形を定義する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 9c57f1536065af0bca1f3752179547daa502c066
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511647"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a><span data-ttu-id="3773d-102">方法: RectangleGeometry を使用して四角形を定義する</span><span class="sxs-lookup"><span data-stu-id="3773d-102">How to: Define a Rectangle Using a RectangleGeometry</span></span>
<span data-ttu-id="3773d-103">この例は、使用する方法を説明します、<xref:System.Windows.Media.RectangleGeometry>を四角形を表すクラス。</span><span class="sxs-lookup"><span data-stu-id="3773d-103">This example describes how to use the <xref:System.Windows.Media.RectangleGeometry> class to describe a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3773d-104">例</span><span class="sxs-lookup"><span data-stu-id="3773d-104">Example</span></span>  
 <span data-ttu-id="3773d-105">次の例を作成してレンダリングする方法を示しています、<xref:System.Windows.Media.RectangleGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="3773d-105">The following example shows how to create and render a <xref:System.Windows.Media.RectangleGeometry>.</span></span>  <span data-ttu-id="3773d-106">相対的な位置と四角形のディメンションがによって定義、<xref:System.Windows.Rect>構造体。</span><span class="sxs-lookup"><span data-stu-id="3773d-106">The relative position and the dimensions of the rectangle are defined by a <xref:System.Windows.Rect> structure.</span></span> <span data-ttu-id="3773d-107">相対位置は`50,50`高さと幅はどちらも、`25`正方形を作成します。</span><span class="sxs-lookup"><span data-stu-id="3773d-107">The relative position is `50,50` and the height and the width are both `25` creating a square.</span></span> <span data-ttu-id="3773d-108">四角形の内部を塗りつぶす、<xref:System.Windows.Media.Brushes.LemonChiffon%2A>でペイント ブラシとアウトライン、<xref:System.Windows.Media.Brushes.Black%2A>ストロークの太さを`1`します。</span><span class="sxs-lookup"><span data-stu-id="3773d-108">The rectangle's interior is painted with a <xref:System.Windows.Media.Brushes.LemonChiffon%2A> brush and its outline is painted with a <xref:System.Windows.Media.Brushes.Black%2A> stroke with a thickness of `1`.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 <span data-ttu-id="3773d-109">![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span><span class="sxs-lookup"><span data-stu-id="3773d-109">![A RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span></span>  
<span data-ttu-id="3773d-110">RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="3773d-110">RectangleGeometry</span></span>  
  
 <span data-ttu-id="3773d-111">この例を<xref:System.Windows.Shapes.Path>レンダリングする要素、<xref:System.Windows.Media.RectangleGeometry>を使用する他の多くの方法はあります<xref:System.Windows.Media.RectangleGeometry>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3773d-111">Although this example used a <xref:System.Windows.Shapes.Path> element to render the <xref:System.Windows.Media.RectangleGeometry>, there are many other ways to use <xref:System.Windows.Media.RectangleGeometry> objects.</span></span> <span data-ttu-id="3773d-112">たとえば、<xref:System.Windows.Media.RectangleGeometry>を指定するために使用する、<xref:System.Windows.UIElement.Clip%2A>の<xref:System.Windows.UIElement>または<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>の<xref:System.Windows.Media.GeometryDrawing>。</span><span class="sxs-lookup"><span data-stu-id="3773d-112">For example, a <xref:System.Windows.Media.RectangleGeometry> can be used to specify the <xref:System.Windows.UIElement.Clip%2A> of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> of a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="3773d-113">その他の単純なジオメトリ クラス<xref:System.Windows.Media.LineGeometry>と<xref:System.Windows.Media.EllipseGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="3773d-113">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="3773d-114">複雑なものと同様にこれらのジオメトリを作成することもを使用して、<xref:System.Windows.Media.PathGeometry>または<xref:System.Windows.Media.StreamGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="3773d-114">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3773d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3773d-115">See also</span></span>
- [<span data-ttu-id="3773d-116">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="3773d-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [<span data-ttu-id="3773d-117">複合図形を作成する</span><span class="sxs-lookup"><span data-stu-id="3773d-117">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)
- [<span data-ttu-id="3773d-118">PathGeometry を使用して図形を作成する</span><span class="sxs-lookup"><span data-stu-id="3773d-118">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)

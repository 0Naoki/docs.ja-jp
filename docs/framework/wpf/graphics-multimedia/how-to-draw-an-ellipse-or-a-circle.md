---
title: '方法: 楕円または円を描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 3a3d25643daaf48f7a0230e199dbba8710184a43
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365348"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="ee5e8-102">方法: 楕円または円を描画する</span><span class="sxs-lookup"><span data-stu-id="ee5e8-102">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="ee5e8-103">この例を使用して楕円および真円を描画する方法を示しています、<xref:System.Windows.Shapes.Ellipse>要素。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-103">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="ee5e8-104">楕円を描画するために作成、<xref:System.Windows.Shapes.Ellipse>要素を指定し、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>します。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-104">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="ee5e8-105">使用してその<xref:System.Windows.Shapes.Shape.Fill%2A>プロパティを指定する、<xref:System.Windows.Media.Brush>楕円の内部を塗りつぶすために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-105">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="ee5e8-106">使用してその<xref:System.Windows.Shapes.Shape.Stroke%2A>プロパティを指定する、<xref:System.Windows.Media.Brush>楕円のアウトラインを描画するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-106">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="ee5e8-107"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>プロパティは、楕円のアウトラインの太さを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-107">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="ee5e8-108">円を描画するように、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>の<xref:System.Windows.Shapes.Ellipse>互いに等しくない要素。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-108">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="ee5e8-109">次の例では、4 つを描画<xref:System.Windows.Shapes.Ellipse>内の要素を<xref:System.Windows.Controls.Canvas>します。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-109">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee5e8-110">例</span><span class="sxs-lookup"><span data-stu-id="ee5e8-110">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="ee5e8-111">この例を使用しますが、 <xref:System.Windows.Controls.Canvas> 、省略記号を格納することができます使用する楕円要素 (およびその他のすべての図形要素) のいずれか<xref:System.Windows.Controls.Panel>または<xref:System.Windows.Controls.Control>テキスト以外のコンテンツをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="ee5e8-112">この例より大きなサンプルの一部です。サンプル全体については、[Shape 要素のサンプル](https://go.microsoft.com/fwlink/?LinkID=160037)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5e8-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee5e8-113">See also</span></span>
- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="ee5e8-114">Shape 要素のサンプル</span><span class="sxs-lookup"><span data-stu-id="ee5e8-114">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)

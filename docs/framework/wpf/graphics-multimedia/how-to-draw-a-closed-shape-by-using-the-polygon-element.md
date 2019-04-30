---
title: '方法: 多角形要素を使用して、閉じた図形を描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 533c341e2fae528ec896bf38bafa13974af1d127
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003237"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="3aa67-102">方法: 多角形要素を使用して、閉じた図形を描画する</span><span class="sxs-lookup"><span data-stu-id="3aa67-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="3aa67-103">この例を使用して、閉じた形状を描画する方法を示しています、<xref:System.Windows.Shapes.Polygon>要素。</span><span class="sxs-lookup"><span data-stu-id="3aa67-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="3aa67-104">閉じた図形を描画するために作成、<xref:System.Windows.Shapes.Polygon>要素と使用してその<xref:System.Windows.Shapes.Polygon.Points%2A>図形の頂点を指定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="3aa67-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="3aa67-105">行が最初と最後の点を結ぶを自動的に描画されます。</span><span class="sxs-lookup"><span data-stu-id="3aa67-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="3aa67-106">最後に、指定、 <xref:System.Windows.Shapes.Shape.Fill%2A>、 <xref:System.Windows.Shapes.Shape.Stroke%2A>、またはその両方です。</span><span class="sxs-lookup"><span data-stu-id="3aa67-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3aa67-107">例</span><span class="sxs-lookup"><span data-stu-id="3aa67-107">Example</span></span>  
 <span data-ttu-id="3aa67-108">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ポイントの有効な構文がコンマで区切られた x 座標と y 座標のペアのスペースで区切られた一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3aa67-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="3aa67-109">例を使用しますが、<xref:System.Windows.Controls.Canvas>多角形を格納することができます使用する多角形要素 (およびその他のすべての図形要素) と<xref:System.Windows.Controls.Panel>または<xref:System.Windows.Controls.Control>テキスト以外のコンテンツをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3aa67-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="3aa67-110">この例より大きなサンプルの一部です。サンプル全体については、次を参照してください。 [Shape 要素のサンプル](https://go.microsoft.com/fwlink/?LinkID=160037)します。</span><span class="sxs-lookup"><span data-stu-id="3aa67-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>

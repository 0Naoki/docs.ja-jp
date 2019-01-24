---
title: '方法: RectangleGeometry の角に丸みを付ける'
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: 1a3ea08e4f54af117474cee23e6ac1041a1ed72b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648376"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="1f8af-102">方法: RectangleGeometry の角に丸みを付ける</span><span class="sxs-lookup"><span data-stu-id="1f8af-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="1f8af-103">角を丸める、<xref:System.Windows.Media.RectangleGeometry>に設定して、その<xref:System.Windows.Media.RectangleGeometry.RadiusX%2A>と<xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>プロパティを 0 より大きい値です。</span><span class="sxs-lookup"><span data-stu-id="1f8af-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="1f8af-104">値が大きいほど、四角形の角はの角。</span><span class="sxs-lookup"><span data-stu-id="1f8af-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f8af-105">例</span><span class="sxs-lookup"><span data-stu-id="1f8af-105">Example</span></span>  
 <span data-ttu-id="1f8af-106">次の例をいくつか示します<xref:System.Windows.Media.RectangleGeometry>オブジェクトが異なる<xref:System.Windows.Media.RectangleGeometry.RadiusX%2A>と<xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>設定します。</span><span class="sxs-lookup"><span data-stu-id="1f8af-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="1f8af-107"><xref:System.Windows.Media.RectangleGeometry>を使用してオブジェクトが表示される<xref:System.Windows.Shapes.Path>要素。</span><span class="sxs-lookup"><span data-stu-id="1f8af-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="1f8af-108">![別の RadiusX 長方形&#47;RadiusY 設定](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="1f8af-108">![Rectangles with different RadiusX&#47;RadiusY settings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="1f8af-109">角の丸い四角形</span><span class="sxs-lookup"><span data-stu-id="1f8af-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f8af-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f8af-110">See also</span></span>
- [<span data-ttu-id="1f8af-111">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="1f8af-111">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [<span data-ttu-id="1f8af-112">複合図形を作成する</span><span class="sxs-lookup"><span data-stu-id="1f8af-112">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)
- [<span data-ttu-id="1f8af-113">PathGeometry を使用して図形を作成する</span><span class="sxs-lookup"><span data-stu-id="1f8af-113">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)

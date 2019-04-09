---
title: WPF での図形と基本描画の概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
ms.openlocfilehash: 1ce0e661d88b7c4d5719c4f11ef0912c5bacb587
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189134"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="51c3f-102">WPF での図形と基本描画の概要</span><span class="sxs-lookup"><span data-stu-id="51c3f-102">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="51c3f-103">このトピックを使用して描画する方法の概要を示します<xref:System.Windows.Shapes.Shape>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="51c3f-103">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="51c3f-104">A<xref:System.Windows.Shapes.Shape>の種類は、<xref:System.Windows.UIElement>画面に図形を描画することができます。</span><span class="sxs-lookup"><span data-stu-id="51c3f-104">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="51c3f-105">UI 要素であるため<xref:System.Windows.Shapes.Shape>オブジェクトは内で使用できる<xref:System.Windows.Controls.Panel>要素とほとんどのコントロール。</span><span class="sxs-lookup"><span data-stu-id="51c3f-105">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="51c3f-106">グラフィックスとレンダリング サービスへのアクセスの複数のレイヤーを提供します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-106">offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="51c3f-107">最上位のレイヤー<xref:System.Windows.Shapes.Shape>オブジェクトは、簡単に使用し、レイアウトへの参加など、多くの便利な機能を提供、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]イベント システム。</span><span class="sxs-lookup"><span data-stu-id="51c3f-107">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  

<a name="shapes"></a>   
## <a name="shape-objects"></a><span data-ttu-id="51c3f-108">図形オブジェクト</span><span class="sxs-lookup"><span data-stu-id="51c3f-108">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="51c3f-109">すぐに使用できるさまざまな<xref:System.Windows.Shapes.Shape>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="51c3f-109">provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="51c3f-110">すべての図形オブジェクトの継承、<xref:System.Windows.Shapes.Shape>クラス。</span><span class="sxs-lookup"><span data-stu-id="51c3f-110">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="51c3f-111">使用可能な図形オブジェクトには、 <xref:System.Windows.Shapes.Ellipse>、 <xref:System.Windows.Shapes.Line>、 <xref:System.Windows.Shapes.Path>、 <xref:System.Windows.Shapes.Polygon>、 <xref:System.Windows.Shapes.Polyline>、および<xref:System.Windows.Shapes.Rectangle>します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-111">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <xref:System.Windows.Shapes.Shape> <span data-ttu-id="51c3f-112">オブジェクトは、次の一般的なプロパティを共有します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-112">objects share the following common properties.</span></span>  
  
-   <xref:System.Windows.Shapes.Shape.Stroke%2A><span data-ttu-id="51c3f-113">:図形のアウトラインを描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-113">: Describes how the shape's outline is painted.</span></span>  
  
-   <xref:System.Windows.Shapes.Shape.StrokeThickness%2A><span data-ttu-id="51c3f-114">:図形のアウトラインの太さについて説明します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-114">: Describes the thickness of the shape's outline.</span></span>  
  
-   <xref:System.Windows.Shapes.Shape.Fill%2A><span data-ttu-id="51c3f-115">:図形の内部を描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-115">: Describes how the interior of the shape is painted.</span></span>  
  
-   <span data-ttu-id="51c3f-116">デバイス非依存ピクセル単位で計測される座標と頂点を指定するデータ プロパティ。</span><span class="sxs-lookup"><span data-stu-id="51c3f-116">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="51c3f-117">派生するため<xref:System.Windows.UIElement>、図形オブジェクトは、パネルおよびほとんどのコントロール内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="51c3f-117">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="51c3f-118"><xref:System.Windows.Controls.Canvas>パネルはその子オブジェクトの絶対配置をサポートするため、複雑な描画の作成に特に適しています。</span><span class="sxs-lookup"><span data-stu-id="51c3f-118">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="51c3f-119"><xref:System.Windows.Shapes.Line>クラスでは、2 点を結ぶ線を描画することができます。</span><span class="sxs-lookup"><span data-stu-id="51c3f-119">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="51c3f-120">直線の座標およびストローク プロパティを指定するいくつかの方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-120">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="51c3f-121">次の図は、レンダリングされた<xref:System.Windows.Shapes.Line>します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-121">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="51c3f-122">![線の図](./media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="51c3f-122">![Line illustration](./media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="51c3f-123">ですが、<xref:System.Windows.Shapes.Line>クラスは、提供、<xref:System.Windows.Shapes.Shape.Fill%2A>プロパティを設定することも何も起こりませんため、<xref:System.Windows.Shapes.Line>領域がありません。</span><span class="sxs-lookup"><span data-stu-id="51c3f-123">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="51c3f-124">もう 1 つの一般的な図形は、<xref:System.Windows.Shapes.Ellipse>します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-124">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="51c3f-125">作成、<xref:System.Windows.Shapes.Ellipse>図形を定義することで<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="51c3f-125">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="51c3f-126">円を描画するには指定、<xref:System.Windows.Shapes.Ellipse>が<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>値が等しい。</span><span class="sxs-lookup"><span data-stu-id="51c3f-126">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="51c3f-127">次の図は、レンダリングの例を示します<xref:System.Windows.Shapes.Ellipse>します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-127">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="51c3f-128">![楕円の図](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="51c3f-128">![Ellipse illustration](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a><span data-ttu-id="51c3f-129">パスとジオメトリの使用</span><span class="sxs-lookup"><span data-stu-id="51c3f-129">Using Paths and Geometries</span></span>  
 <span data-ttu-id="51c3f-130"><xref:System.Windows.Shapes.Path>クラスでは、曲線および複雑な図形を描画することができます。</span><span class="sxs-lookup"><span data-stu-id="51c3f-130">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="51c3f-131">これらの曲線および図形を使用して記述<xref:System.Windows.Media.Geometry>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="51c3f-131">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="51c3f-132">使用する、 <xref:System.Windows.Shapes.Path>、作成する、<xref:System.Windows.Media.Geometry>に設定して、<xref:System.Windows.Shapes.Path>オブジェクトの<xref:System.Windows.Shapes.Path.Data%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="51c3f-132">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="51c3f-133">さまざまな<xref:System.Windows.Media.Geometry>から選択するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="51c3f-133">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="51c3f-134"><xref:System.Windows.Media.LineGeometry>、 <xref:System.Windows.Media.RectangleGeometry>、および<xref:System.Windows.Media.EllipseGeometry>クラスは、比較的単純な図形をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-134">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="51c3f-135">複雑な図形を作成または曲線を作成、使用して、<xref:System.Windows.Media.PathGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-135">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="51c3f-136">PathGeometry と PathSegment</span><span class="sxs-lookup"><span data-stu-id="51c3f-136">PathGeometry and PathSegments</span></span>  
 <xref:System.Windows.Media.PathGeometry> <span data-ttu-id="51c3f-137">オブジェクトは、1 つまたは複数の構成要素は<xref:System.Windows.Media.PathFigure>オブジェクト。 各<xref:System.Windows.Media.PathFigure>異なる"図"または図形を表します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-137">objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="51c3f-138">各<xref:System.Windows.Media.PathFigure>自体は 1 つ以上ので構成されます<xref:System.Windows.Media.PathSegment>それぞれ図や図形の接続されている部分を表すオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="51c3f-138">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="51c3f-139">セグメントの種類は、次を含める: <xref:System.Windows.Media.LineSegment>、 <xref:System.Windows.Media.BezierSegment>、および<xref:System.Windows.Media.ArcSegment>します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-139">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="51c3f-140">次の例では、 <xref:System.Windows.Shapes.Path> 2 次ベジエ曲線の描画に使用します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-140">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="51c3f-141">レンダリングされた図形を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-141">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="51c3f-142">![パスの図](./media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="51c3f-142">![Path illustration](./media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="51c3f-143">詳細については<xref:System.Windows.Media.PathGeometry>およびその他、<xref:System.Windows.Media.Geometry>クラスを参照してください、[ジオメトリの概要](geometry-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-143">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="51c3f-144">省略された XAML 構文</span><span class="sxs-lookup"><span data-stu-id="51c3f-144">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="51c3f-145">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]、記述する特別な省略構文を使用することも、<xref:System.Windows.Shapes.Path>します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="51c3f-146">次の例では、省略された構文を使用して複雑な図形を描画します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-146">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="51c3f-147">次の図は、レンダリングされた<xref:System.Windows.Shapes.Path>します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-147">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="51c3f-148">![パスの図](./media/shape-ovw-path.PNG "shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="51c3f-148">![Path illustration](./media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="51c3f-149"><xref:System.Windows.Shapes.Path.Data%2A>属性文字列の先頭の座標システムで、パスの開始点を確立、M で示される"moveto"コマンドが、<xref:System.Windows.Controls.Canvas>します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-149">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <xref:System.Windows.Shapes.Path> <span data-ttu-id="51c3f-150">データのパラメーターは大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-150">data parameters are case-sensitive.</span></span> <span data-ttu-id="51c3f-151">大文字の M では、現在の新しい点の絶対位置を示します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-151">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="51c3f-152">小文字の m は、相対座標を示します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-152">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="51c3f-153">最初のセグメントは、2 つの制御点 (100,25) と (400,350) を使用して描画される、始点が (100,200) で終点が (400,175) の 3 次ベジエ曲線です。</span><span class="sxs-lookup"><span data-stu-id="51c3f-153">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="51c3f-154">このセグメントは、C のコマンドで示される、<xref:System.Windows.Shapes.Path.Data%2A>属性の文字列。</span><span class="sxs-lookup"><span data-stu-id="51c3f-154">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="51c3f-155">ここでも、大文字の C は絶対パスを示し、小文字の c は相対パスを示します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-155">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="51c3f-156">2 番目のセグメントは、絶対水平 "lineto" コマンド H で始まります。このコマンドは、前のサブパスの終点 (400,175) から新しい終点 (280,175) まで描画される直線を指定します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-156">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="51c3f-157">指定された値は、水平"lineto"コマンドであるため、 *x*-を調整します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-157">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="51c3f-158">完全なパスの構文を参照してください、<xref:System.Windows.Shapes.Path.Data%2A>参照と[PathGeometry を使用して図形を作成](how-to-create-a-shape-by-using-a-pathgeometry.md)です。</span><span class="sxs-lookup"><span data-stu-id="51c3f-158">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a><span data-ttu-id="51c3f-159">図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="51c3f-159">Painting Shapes</span></span>  
 <xref:System.Windows.Media.Brush> <span data-ttu-id="51c3f-160">オブジェクトが図形の描画に使用される<xref:System.Windows.Shapes.Shape.Stroke%2A>と<xref:System.Windows.Shapes.Shape.Fill%2A>します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-160">objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="51c3f-161">次の例、ストロークおよび塗りつぶしの<xref:System.Windows.Shapes.Ellipse>が指定されています。</span><span class="sxs-lookup"><span data-stu-id="51c3f-161">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="51c3f-162">ブラシ プロパティの有効な入力は、キーワードまたは 16 進数のカラー値のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="51c3f-162">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="51c3f-163">使用可能なカラー キーワードの詳細については、のプロパティを参照してください、<xref:System.Windows.Media.Colors>クラス、<xref:System.Windows.Media>名前空間。</span><span class="sxs-lookup"><span data-stu-id="51c3f-163">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
```xaml
<Canvas Background="LightGray">   
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
```  
  
 <span data-ttu-id="51c3f-164">次の図は、レンダリングされた<xref:System.Windows.Shapes.Ellipse>します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-164">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="51c3f-165">![楕円](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="51c3f-165">![An ellipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="51c3f-166">または、プロパティ要素構文を使用して明示的に作成することができます、<xref:System.Windows.Media.SolidColorBrush>純色で図形を描画するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="51c3f-166">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
```xaml
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"   
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 <span data-ttu-id="51c3f-167">レンダリングされた図形を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-167">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="51c3f-168">![SolidColorBrush の図](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="51c3f-168">![SolidColorBrush illustration](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="51c3f-169">図形のストロークまたは塗りつぶしをグラデーション、イメージ、パターンなどで塗りつぶすこともできます。</span><span class="sxs-lookup"><span data-stu-id="51c3f-169">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="51c3f-170">詳細については、次を参照してください。、[純色およびグラデーション概要](painting-with-solid-colors-and-gradients-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-170">For more information, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a><span data-ttu-id="51c3f-171">伸縮可能な図形</span><span class="sxs-lookup"><span data-stu-id="51c3f-171">Stretchable Shapes</span></span>  
 <span data-ttu-id="51c3f-172"><xref:System.Windows.Shapes.Line>、 <xref:System.Windows.Shapes.Path>、 <xref:System.Windows.Shapes.Polygon>、 <xref:System.Windows.Shapes.Polyline>、および<xref:System.Windows.Shapes.Rectangle>クラスがすべて、<xref:System.Windows.Shapes.Shape.Stretch%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="51c3f-172">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="51c3f-173">このプロパティを決定する方法、<xref:System.Windows.Shapes.Shape>オブジェクトのコンテンツ (描画される図形) がいっぱいに拡大されます、<xref:System.Windows.Shapes.Shape>オブジェクトのレイアウト空間。</span><span class="sxs-lookup"><span data-stu-id="51c3f-173">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="51c3f-174">A<xref:System.Windows.Shapes.Shape>オブジェクトのレイアウト空間は、領域の量、<xref:System.Windows.Shapes.Shape>が割り当てられる、レイアウト システムでは、いずれかが原因、明示的な<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>設定のため、またはその<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>と<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>設定します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-174">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="51c3f-175">Windows Presentation Foundation でのレイアウトの詳細については、次を参照してください。[レイアウト](../advanced/layout.md)の概要。</span><span class="sxs-lookup"><span data-stu-id="51c3f-175">For additional information on layout in Windows Presentation Foundation, see [Layout](../advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="51c3f-176">プロパティには、次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-176">The Stretch property takes one of the following values:</span></span>  
  
-   <xref:System.Windows.Media.Stretch.None><span data-ttu-id="51c3f-177">:<xref:System.Windows.Shapes.Shape>オブジェクトのコンテンツは引き伸ばされません。</span><span class="sxs-lookup"><span data-stu-id="51c3f-177">: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
-   <xref:System.Windows.Media.Stretch.Fill><span data-ttu-id="51c3f-178">:<xref:System.Windows.Shapes.Shape>レイアウト空間を入力するオブジェクトのコンテンツは引き伸ばされます。</span><span class="sxs-lookup"><span data-stu-id="51c3f-178">: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="51c3f-179">縦横比は維持されません。</span><span class="sxs-lookup"><span data-stu-id="51c3f-179">Aspect ratio is not preserved.</span></span>  
  
-   <xref:System.Windows.Media.Stretch.Uniform><span data-ttu-id="51c3f-180">:<xref:System.Windows.Shapes.Shape>オブジェクトのコンテンツは元の縦横比を維持しながら、レイアウト空間を入力する可能な限り引き伸ばされます。</span><span class="sxs-lookup"><span data-stu-id="51c3f-180">: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
-   <xref:System.Windows.Media.Stretch.UniformToFill><span data-ttu-id="51c3f-181">:<xref:System.Windows.Shapes.Shape>オブジェクトの内容は、元の縦横比を維持しながら、レイアウト空間を完全に埋めるに引き伸ばされます。</span><span class="sxs-lookup"><span data-stu-id="51c3f-181">: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="51c3f-182">なお、ときに、<xref:System.Windows.Shapes.Shape>オブジェクトのコンテンツを引き伸ばす、<xref:System.Windows.Shapes.Shape>拡大した後はオブジェクトのアウトラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-182">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="51c3f-183">次の例では、 <xref:System.Windows.Shapes.Polygon> (1, 1) に (0, 1) に (0, 0) から非常に小さな三角形の描画に使用します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-183">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="51c3f-184"><xref:System.Windows.Shapes.Polygon>オブジェクトの<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>が 100 に設定し、その stretch プロパティを Fill に設定されます。</span><span class="sxs-lookup"><span data-stu-id="51c3f-184">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="51c3f-185">結果として、<xref:System.Windows.Shapes.Polygon>オブジェクトのコンテンツ (三角形) は拡大のスペースを埋めるに引き伸ばされます。</span><span class="sxs-lookup"><span data-stu-id="51c3f-185">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
```xaml
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
```

```csharp
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
```

<a name="transforms"></a>   
## <a name="transforming-shapes"></a><span data-ttu-id="51c3f-186">図形の変換</span><span class="sxs-lookup"><span data-stu-id="51c3f-186">Transforming Shapes</span></span>  
 <span data-ttu-id="51c3f-187"><xref:System.Windows.Media.Transform>クラスには、2 次元平面内の図形を変換するための手段が用意されています。</span><span class="sxs-lookup"><span data-stu-id="51c3f-187">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="51c3f-188">変換のさまざまな種類は、回転 (<xref:System.Windows.Media.RotateTransform>)、スケール (<xref:System.Windows.Media.ScaleTransform>)、傾斜 (<xref:System.Windows.Media.SkewTransform>)、および翻訳 (<xref:System.Windows.Media.TranslateTransform>)。</span><span class="sxs-lookup"><span data-stu-id="51c3f-188">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="51c3f-189">図形に適用される一般的な変換は回転です。</span><span class="sxs-lookup"><span data-stu-id="51c3f-189">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="51c3f-190">図形を回転するには、作成、<xref:System.Windows.Media.RotateTransform>指定とその<xref:System.Windows.Media.RotateTransform.Angle%2A>します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-190">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="51c3f-191"><xref:System.Windows.Media.RotateTransform.Angle%2A> 45 の要素を 45 度回転角度が 90 の要素を 90 度回転; まで、時計回り時計回りします。</span><span class="sxs-lookup"><span data-stu-id="51c3f-191">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="51c3f-192">設定、<xref:System.Windows.Media.RotateTransform.CenterX%2A>と<xref:System.Windows.Media.RotateTransform.CenterY%2A>プロパティ要素を回転、位置を制御する場合。</span><span class="sxs-lookup"><span data-stu-id="51c3f-192">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="51c3f-193">これらのプロパティ値は、変換する要素の座標空間で表します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-193">These property values are expressed in the coordinate space of the element being transformed.</span></span> <xref:System.Windows.Media.RotateTransform.CenterX%2A> <span data-ttu-id="51c3f-194"><xref:System.Windows.Media.RotateTransform.CenterY%2A> 0 の既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-194">and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="51c3f-195">最後に、適用、<xref:System.Windows.Media.RotateTransform>要素にします。</span><span class="sxs-lookup"><span data-stu-id="51c3f-195">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="51c3f-196">レイアウトに影響する変換しない場合は、設定、図形の<xref:System.Windows.UIElement.RenderTransform%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="51c3f-196">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="51c3f-197">次の例では、<xref:System.Windows.Media.RotateTransform>図形の左上隅 (0, 0) の図形を 45 度回転するために使用します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-197">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="51c3f-198">次の例では、別の図形を 45 度回転していますが、この場合は (25,50) が回転の中心です。</span><span class="sxs-lookup"><span data-stu-id="51c3f-198">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="51c3f-199">上記 2 つの変換を適用すると、結果は次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="51c3f-199">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="51c3f-200">![中心点が異なる 45 度の回転](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="51c3f-200">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="51c3f-201">前の例では、単一の変換を各図形オブジェクトに適用しました。</span><span class="sxs-lookup"><span data-stu-id="51c3f-201">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="51c3f-202">図形 (またはその他の UI 要素) には、複数の変換を適用するには、使用、<xref:System.Windows.Media.TransformGroup>します。</span><span class="sxs-lookup"><span data-stu-id="51c3f-202">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51c3f-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="51c3f-203">See also</span></span>

- [<span data-ttu-id="51c3f-204">2D グラフィックスとイメージング</span><span class="sxs-lookup"><span data-stu-id="51c3f-204">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="51c3f-205">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="51c3f-205">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="51c3f-206">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="51c3f-206">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="51c3f-207">チュートリアル: 初めての WPF デスクトップ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="51c3f-207">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [<span data-ttu-id="51c3f-208">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="51c3f-208">Animation Overview</span></span>](animation-overview.md)

---
title: グラフィックス サービスの 3 つのカテゴリ
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2-D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: 2c2ddc76faaf0c15cc56345c607678985b9c4656
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576383"
---
# <a name="three-categories-of-graphics-services"></a><span data-ttu-id="499c9-102">グラフィックス サービスの 3 つのカテゴリ</span><span class="sxs-lookup"><span data-stu-id="499c9-102">Three Categories of Graphics Services</span></span>
<span data-ttu-id="499c9-103">Windows フォームでグラフィックスの提供は、次の 3 つの広範なカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="499c9-103">The graphics offerings in Windows Forms fall into the following three broad categories:</span></span>  
  
-   <span data-ttu-id="499c9-104">2 次元 (2-d) のベクター グラフィックス</span><span class="sxs-lookup"><span data-stu-id="499c9-104">Two-dimensional (2-D) vector graphics</span></span>  
  
-   <span data-ttu-id="499c9-105">イメージング</span><span class="sxs-lookup"><span data-stu-id="499c9-105">Imaging</span></span>  
  
-   <span data-ttu-id="499c9-106">タイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="499c9-106">Typography</span></span>  
  
## <a name="2-d-vector-graphics"></a><span data-ttu-id="499c9-107">2 次元ベクター グラフィックス</span><span class="sxs-lookup"><span data-stu-id="499c9-107">2-D Vector Graphics</span></span>  
 <span data-ttu-id="499c9-108">2 次元ベクター グラフィックスはプリミティブです。直線、曲線、および図表; など座標系のポイントのセットによって指定されています。</span><span class="sxs-lookup"><span data-stu-id="499c9-108">Two-dimensional vector graphics are primitives; such as lines, curves, and figures; that are specified by sets of points on a coordinate system.</span></span> <span data-ttu-id="499c9-109">たとえば、直線がその 2 つのエンドポイントで指定され、四角形の左上隅にあると、幅と高さを定義する数値の 1 組の位置を示す点で指定します。</span><span class="sxs-lookup"><span data-stu-id="499c9-109">For example, a straight line is specified by its two endpoints, and a rectangle is specified by a point giving the location of its upper-left corner and a pair of numbers giving its width and height.</span></span> <span data-ttu-id="499c9-110">単純なパスは、直線で接続されている点の配列によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="499c9-110">A simple path is specified by an array of points that are connected by straight lines.</span></span> <span data-ttu-id="499c9-111">ベジエ スプラインは、4 つのコントロール ポイントで指定された高度な曲線です。</span><span class="sxs-lookup"><span data-stu-id="499c9-111">A Bézier spline is a sophisticated curve specified by four control points.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="499c9-112">クラスとプリミティブ自体に関する情報を格納する構造体、プリミティブを描画する方法についての情報を格納するクラスおよび実際に描画を実行するクラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="499c9-112">provides classes and structures that store information about the primitives themselves, classes that store information about how the primitives will be drawn, and classes that actually do the drawing.</span></span> <span data-ttu-id="499c9-113">など、<xref:System.Drawing.Rectangle>構造体に格納する四角形のサイズと場所、<xref:System.Drawing.Pen>クラスは、線の色、線の幅、および線のスタイルに関する情報を格納し、<xref:System.Drawing.Graphics>クラスには、線、四角形、パスを描画するためのメソッドとその他の数値。</span><span class="sxs-lookup"><span data-stu-id="499c9-113">For example, the <xref:System.Drawing.Rectangle> structure stores the location and size of a rectangle; the <xref:System.Drawing.Pen> class stores information about line color, line width, and line style; and the <xref:System.Drawing.Graphics> class has methods for drawing lines, rectangles, paths, and other figures.</span></span> <span data-ttu-id="499c9-114">あるいくつかも<xref:System.Drawing.Brush>方法に関する情報を格納するクラスの終了図形とパスが色やパターンで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="499c9-114">There are also several <xref:System.Drawing.Brush> classes that store information about how closed figures and paths will be filled with colors or patterns.</span></span>  
  
 <span data-ttu-id="499c9-115">メタファイルには、一連のグラフィック コマンドには、ベクター イメージを記録できます。</span><span class="sxs-lookup"><span data-stu-id="499c9-115">You can record a vector image, which is a sequence of graphics commands, in a metafile.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="499c9-116">提供、<xref:System.Drawing.Imaging.Metafile>記録、表示、およびメタファイルを保存するためのクラス。</span><span class="sxs-lookup"><span data-stu-id="499c9-116">provides the <xref:System.Drawing.Imaging.Metafile> class for recording, displaying, and saving metafiles.</span></span> <span data-ttu-id="499c9-117"><xref:System.Drawing.Imaging.MetafileHeader>と<xref:System.Drawing.Imaging.MetaHeader>クラス、メタファイル ヘッダーに格納されたデータを検査することができます。</span><span class="sxs-lookup"><span data-stu-id="499c9-117">With the <xref:System.Drawing.Imaging.MetafileHeader> and <xref:System.Drawing.Imaging.MetaHeader> classes, you can inspect the data stored in a metafile header.</span></span>  
  
## <a name="imaging"></a><span data-ttu-id="499c9-118">イメージング</span><span class="sxs-lookup"><span data-stu-id="499c9-118">Imaging</span></span>  
 <span data-ttu-id="499c9-119">特定の種類の画像は、困難または不可能なベクター グラフィックスの手法で表示されます。</span><span class="sxs-lookup"><span data-stu-id="499c9-119">Certain kinds of pictures are difficult or impossible to display with the techniques of vector graphics.</span></span> <span data-ttu-id="499c9-120">たとえば、ツール バー ボタンの画像やアイコンとして表示される画像は、直線と曲線のコレクションとして指定する困難です。</span><span class="sxs-lookup"><span data-stu-id="499c9-120">For example, the pictures on toolbar buttons and the pictures that appear as icons are difficult to specify as collections of lines and curves.</span></span> <span data-ttu-id="499c9-121">混雑した野球場の高解像度デジタル写真はベクター手法を作成するさらに難しくなります。</span><span class="sxs-lookup"><span data-stu-id="499c9-121">A high-resolution digital photograph of a crowded baseball stadium is even more difficult to create with vector techniques.</span></span> <span data-ttu-id="499c9-122">このタイプのイメージはビットマップで、画面上の個々 のドットの色を表す数値の配列として格納されます。</span><span class="sxs-lookup"><span data-stu-id="499c9-122">Images of this type are stored as bitmaps, which are arrays of numbers that represent the colors of individual dots on the screen.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="499c9-123">提供、<xref:System.Drawing.Bitmap>を表示する、操作、およびビットマップの保存のクラス。</span><span class="sxs-lookup"><span data-stu-id="499c9-123">provides the <xref:System.Drawing.Bitmap> class for displaying, manipulating, and saving bitmaps.</span></span>  
  
## <a name="typography"></a><span data-ttu-id="499c9-124">タイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="499c9-124">Typography</span></span>  
 <span data-ttu-id="499c9-125">文字体裁は、さまざまなフォント、サイズ、およびスタイル内のテキストの表示です。</span><span class="sxs-lookup"><span data-stu-id="499c9-125">Typography is the display of text in a variety of fonts, sizes, and styles.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="499c9-126">この複雑なタスクの広範なサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="499c9-126">provides extensive support for this complex task.</span></span> <span data-ttu-id="499c9-127">新機能の 1 つ[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]サブピクセル アンチ エイリアスのテキストの表示、LCD 画面滑らかに表示します。</span><span class="sxs-lookup"><span data-stu-id="499c9-127">One of the new features in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is subpixel antialiasing, which gives text rendered on an LCD screen a smoother appearance.</span></span>  
  
 <span data-ttu-id="499c9-128">Windows フォームがテキストを描画するオプションを提供するさらに、[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]機能でその<xref:System.Windows.Forms.TextRenderer>クラス。</span><span class="sxs-lookup"><span data-stu-id="499c9-128">In addition, Windows Forms offers the option to draw text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] capabilities in its <xref:System.Windows.Forms.TextRenderer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="499c9-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="499c9-129">See also</span></span>
- [<span data-ttu-id="499c9-130">グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="499c9-130">Graphics Overview</span></span>](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)
- [<span data-ttu-id="499c9-131">GDI+ マネージド コードについて</span><span class="sxs-lookup"><span data-stu-id="499c9-131">About GDI+ Managed Code</span></span>](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)
- [<span data-ttu-id="499c9-132">マネージド グラフィックス クラスの使用</span><span class="sxs-lookup"><span data-stu-id="499c9-132">Using Managed Graphics Classes</span></span>](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)

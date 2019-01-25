---
title: '方法: タイル イメージを持つ図形'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: f2edde7e78f996d4a7bfbc636210f315c0718f6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693215"
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="d5b43-102">方法: タイル イメージを持つ図形</span><span class="sxs-lookup"><span data-stu-id="d5b43-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="d5b43-103">フロアをカバーする他の横にあるタイルを配置すると同様、(タイル) 図形の塗りつぶし、四角形のイメージを互いの横にある配置できます。</span><span class="sxs-lookup"><span data-stu-id="d5b43-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="d5b43-104">形状の内部を並べて表示するには、テクスチャ ブラシを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5b43-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="d5b43-105">構築する際に、<xref:System.Drawing.TextureBrush>オブジェクトのコンス トラクターに渡す引数の 1 つは、<xref:System.Drawing.Image>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5b43-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="d5b43-106">テクスチャ ブラシを使用して、図形の内部を描画するときにこのイメージのコピーを繰り返し、図形が入力されます。</span><span class="sxs-lookup"><span data-stu-id="d5b43-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="d5b43-107">ラップ モード プロパティ、<xref:System.Drawing.TextureBrush>方法、画像には、四角形グリッドでこれが繰り返されるオブジェクトを決定します。</span><span class="sxs-lookup"><span data-stu-id="d5b43-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="d5b43-108">行うことができます、グリッド内のタイルがすべて同じ方向、または反転させる 1 つのグリッド位置から、次に、イメージを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d5b43-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="d5b43-109">反転は、水平、垂直、またはその両方です。</span><span class="sxs-lookup"><span data-stu-id="d5b43-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="d5b43-110">次の例では、さまざまな種類の反転を並べて表示します。</span><span class="sxs-lookup"><span data-stu-id="d5b43-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="d5b43-111">イメージを並べて表示</span><span class="sxs-lookup"><span data-stu-id="d5b43-111">To tile an image</span></span>  
  
-   <span data-ttu-id="d5b43-112">この例では、次の 75 × 75 イメージを使用して、200 × 200 四角形を並べて表示します。</span><span class="sxs-lookup"><span data-stu-id="d5b43-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 <span data-ttu-id="d5b43-113">![タイル 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span><span class="sxs-lookup"><span data-stu-id="d5b43-113">![Tile 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span></span>  
  
-   <span data-ttu-id="d5b43-114">次の図は、四角形がイメージに並べて表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d5b43-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="d5b43-115">すべてのタイルが同じ方向; があることに注意してください。反転はありません。</span><span class="sxs-lookup"><span data-stu-id="d5b43-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 <span data-ttu-id="d5b43-116">![タイル 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span><span class="sxs-lookup"><span data-stu-id="d5b43-116">![Tile 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="d5b43-117">水平方向に並べて表示するときにイメージを反転するには</span><span class="sxs-lookup"><span data-stu-id="d5b43-117">To flip an image horizontally while tiling</span></span>  
  
-   <span data-ttu-id="d5b43-118">この例では、同じ 75 × 75 イメージを使用して、200 × 200 四角形を入力します。</span><span class="sxs-lookup"><span data-stu-id="d5b43-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="d5b43-119">ラップ モードは、イメージを水平方向に反転に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d5b43-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="d5b43-120">次の図は、四角形がイメージに並べて表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d5b43-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="d5b43-121">次の特定の行に 1 つのタイルから移動すると、イメージ水平方向に反転に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d5b43-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 <span data-ttu-id="d5b43-122">![タイル 3 の](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span><span class="sxs-lookup"><span data-stu-id="d5b43-122">![Tile 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="d5b43-123">垂直方向に並べて表示するときにイメージを反転するには</span><span class="sxs-lookup"><span data-stu-id="d5b43-123">To flip an image vertically while tiling</span></span>  
  
-   <span data-ttu-id="d5b43-124">この例では、同じ 75 × 75 イメージを使用して、200 × 200 四角形を入力します。</span><span class="sxs-lookup"><span data-stu-id="d5b43-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="d5b43-125">ラップ モードは、イメージを垂直方向に反転に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d5b43-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="d5b43-126">並べて表示するとき、イメージを水平および垂直方向に反転するには</span><span class="sxs-lookup"><span data-stu-id="d5b43-126">To flip an image horizontally and vertically while tiling</span></span>  
  
-   <span data-ttu-id="d5b43-127">この例では、同じ 75 × 75 イメージを使用して、200 × 200 四角形を並べて表示します。</span><span class="sxs-lookup"><span data-stu-id="d5b43-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="d5b43-128">ラップ モードは、イメージを水平および垂直方向に反転に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d5b43-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="d5b43-129">次の図は、四角形がイメージと、並べて表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d5b43-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="d5b43-130">次の特定の行に 1 つのタイルから移動する、イメージは水平方向に反転させる、イメージが垂直方向に反転させるように、特定の列に 1 つのタイルから移動するに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d5b43-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 <span data-ttu-id="d5b43-131">![5 をタイル](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span><span class="sxs-lookup"><span data-stu-id="d5b43-131">![Tile 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="d5b43-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5b43-132">See also</span></span>
- [<span data-ttu-id="d5b43-133">ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="d5b43-133">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)

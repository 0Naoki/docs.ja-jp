---
title: '方法: イメージ テクスチャによって図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: bf1e09548ff9bc4eb650048eb21a9c300f3f6405
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601780"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="68638-102">方法: イメージ テクスチャによって図形を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="68638-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="68638-103">使用してテクスチャを使用して、閉じた形状を入力することができます、<xref:System.Drawing.Image>クラスおよび<xref:System.Drawing.TextureBrush>クラス。</span><span class="sxs-lookup"><span data-stu-id="68638-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68638-104">例</span><span class="sxs-lookup"><span data-stu-id="68638-104">Example</span></span>  
 <span data-ttu-id="68638-105">次の例では、イメージを使用して楕円を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="68638-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="68638-106">コードを構築します、<xref:System.Drawing.Image>オブジェクト、し、そのアドレスを渡す<xref:System.Drawing.Image>オブジェクトへの引数として、<xref:System.Drawing.TextureBrush.%23ctor%2A>コンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="68638-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="68638-107">3 番目のステートメントは、イメージを縮小し、4 番目のステートメントがスケーリングされたイメージの繰り返しコピーで楕円を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="68638-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="68638-108">次のコードで、<xref:System.Drawing.TextureBrush.Transform%2A>プロパティに描画前に、イメージに適用される変換が含まれています。</span><span class="sxs-lookup"><span data-stu-id="68638-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="68638-109">元のイメージが 640 ピクセルの幅と高さが 480 ピクセルであると仮定します。</span><span class="sxs-lookup"><span data-stu-id="68638-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="68638-110">変換では、水平および垂直方向のスケーリング値を設定して、イメージを 75 × 75 に縮小します。</span><span class="sxs-lookup"><span data-stu-id="68638-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68638-111">次の例では、イメージのサイズが 75 × 75、および楕円サイズは 150 × 250。</span><span class="sxs-lookup"><span data-stu-id="68638-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="68638-112">イメージは、入力は楕円より小さいため、楕円は、イメージを並べて表示されます。</span><span class="sxs-lookup"><span data-stu-id="68638-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="68638-113">意味するイメージまで繰り返されます水平および垂直に形状の境界をタイルに到達します。</span><span class="sxs-lookup"><span data-stu-id="68638-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="68638-114">タイルの詳細については、次を参照してください。[方法。イメージに図形をタイル](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md)します。</span><span class="sxs-lookup"><span data-stu-id="68638-114">For more information about tiling, see [How to: Tile a Shape with an Image](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="68638-115">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="68638-115">Compiling the Code</span></span>  
 <span data-ttu-id="68638-116">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="68638-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68638-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="68638-117">See also</span></span>
- [<span data-ttu-id="68638-118">ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="68638-118">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)

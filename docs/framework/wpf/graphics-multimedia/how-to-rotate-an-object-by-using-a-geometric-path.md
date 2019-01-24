---
title: '方法: ジオメトリック パスを使用してオブジェクトを回転させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: cd8aaee7563d684e70dc29f1c293b091c1e6cff9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661491"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="2d40b-102">方法: ジオメトリック パスを使用してオブジェクトを回転させる</span><span class="sxs-lookup"><span data-stu-id="2d40b-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="2d40b-103">この例では回転 (ピボット) 方法によって定義されたジオメトリック パスに沿ってオブジェクトを<xref:System.Windows.Media.PathGeometry>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2d40b-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d40b-104">例</span><span class="sxs-lookup"><span data-stu-id="2d40b-104">Example</span></span>  
 <span data-ttu-id="2d40b-105">次の例は、3 つ<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>四角形をジオメトリ パスに沿って移動するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2d40b-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
-   <span data-ttu-id="2d40b-106">最初の<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>をアニメーション化、<xref:System.Windows.Media.RotateTransform>いる四角形に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2d40b-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="2d40b-107">アニメーションは、角度の値を生成します。</span><span class="sxs-lookup"><span data-stu-id="2d40b-107">The animation generates angle values.</span></span> <span data-ttu-id="2d40b-108">これにより、四角形がパスの輪郭に沿って回転 (ピボット) します。</span><span class="sxs-lookup"><span data-stu-id="2d40b-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
-   <span data-ttu-id="2d40b-109">その他の 2 つのオブジェクトをアニメーション化する、<xref:System.Windows.Media.TranslateTransform.X%2A>と<xref:System.Windows.Media.TranslateTransform.Y%2A>の値を<xref:System.Windows.Media.TranslateTransform>いる四角形に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2d40b-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="2d40b-110">これにより、四角形が、パスに沿って水平方向と垂直方向に移動します。</span><span class="sxs-lookup"><span data-stu-id="2d40b-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="2d40b-111">ジオメトリック パスを使用してオブジェクトを回転することもできますが、使用する、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>オブジェクトし、設定、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="2d40b-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="2d40b-112">詳細と例では、次を参照してください。[ジオメトリック パス (行列アニメーション) を使用してオブジェクトを回転させる](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d40b-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="2d40b-113">サンプル全体については、次を参照してください。[パス アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160028)します。</span><span class="sxs-lookup"><span data-stu-id="2d40b-113">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d40b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d40b-114">See also</span></span>
- [<span data-ttu-id="2d40b-115">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="2d40b-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="2d40b-116">パス アニメーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="2d40b-116">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
- [<span data-ttu-id="2d40b-117">パス アニメーションに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="2d40b-117">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)

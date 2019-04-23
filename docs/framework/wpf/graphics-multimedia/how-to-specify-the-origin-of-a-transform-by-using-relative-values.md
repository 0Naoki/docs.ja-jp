---
title: '方法: 変換の原点を相対値で指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
ms.openlocfilehash: 48b3b0df8dab8516873495a996074eae57ffe00f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082959"
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a><span data-ttu-id="e423d-102">方法: 変換の原点を相対値で指定する</span><span class="sxs-lookup"><span data-stu-id="e423d-102">How to: Specify the Origin of a Transform by Using Relative Values</span></span>
<span data-ttu-id="e423d-103">この例の原点を指定する相対値を使用する方法を示しています、<xref:System.Windows.UIElement.RenderTransform%2A>に適用される、<xref:System.Windows.FrameworkElement>します。</span><span class="sxs-lookup"><span data-stu-id="e423d-103">This example shows how to use relative values to specify the origin of a <xref:System.Windows.UIElement.RenderTransform%2A> that is applied to a <xref:System.Windows.FrameworkElement>.</span></span>  
  
 <span data-ttu-id="e423d-104">回転、拡大縮小、または傾斜するときに、<xref:System.Windows.FrameworkElement>を使用して、<xref:System.Windows.UIElement.RenderTransform%2A>プロパティの既定の設定では、要素の左上隅に、変換が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e423d-104">When you rotate, scale, or skew a <xref:System.Windows.FrameworkElement> by using the <xref:System.Windows.UIElement.RenderTransform%2A> property, the default setting applies the transform to the upper-left corner of the element.</span></span> <span data-ttu-id="e423d-105">要素の中心から回転、拡大縮小、または傾斜させる場合は、要素の中心に変換の中心を設定して補正することができます。</span><span class="sxs-lookup"><span data-stu-id="e423d-105">If you want to rotate, scale, or skew from the center of the element, you can compensate by setting the center of the transform to the center of the element.</span></span> <span data-ttu-id="e423d-106">ただし、そのソリューションでは、要素のサイズがわかっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e423d-106">However, that solution requires that you know the size of the element.</span></span> <span data-ttu-id="e423d-107">設定する要素の中心に変換を適用する簡単な方法は、その<xref:System.Windows.UIElement.RenderTransformOrigin%2A>プロパティを (0.5, 0.5)、変換自体に中心の値を設定する代わりにします。</span><span class="sxs-lookup"><span data-stu-id="e423d-107">An easier way of applying a transform to the center of an element is to set its <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to (0.5, 0.5), instead of setting a center value on the transform itself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e423d-108">例</span><span class="sxs-lookup"><span data-stu-id="e423d-108">Example</span></span>  
 <span data-ttu-id="e423d-109">次の例では、<xref:System.Windows.Media.RotateTransform>を回転する、<xref:System.Windows.Controls.Button>時計回りに 45 度。</span><span class="sxs-lookup"><span data-stu-id="e423d-109">The following example uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise.</span></span> <span data-ttu-id="e423d-110">この例では中心を指定していないので、ボタンは、左上隅の点 (0, 0) の周りを回転します。</span><span class="sxs-lookup"><span data-stu-id="e423d-110">Because the example does not specify a center, the button rotates about the point (0, 0), which is its upper-left corner.</span></span> <span data-ttu-id="e423d-111"><xref:System.Windows.Media.RotateTransform>に適用される、<xref:System.Windows.UIElement.RenderTransform%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e423d-111">The <xref:System.Windows.Media.RotateTransform> is applied to the <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="e423d-112">次の図は、それに続く例の変換結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="e423d-112">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="e423d-113">![RenderTransform を使用して変換されたボタン](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span><span class="sxs-lookup"><span data-stu-id="e423d-113">![A button transformed using RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span></span>  
<span data-ttu-id="e423d-114">RenderTransform プロパティを使用して時計回りに 45 度回転</span><span class="sxs-lookup"><span data-stu-id="e423d-114">A 45 degree clockwise rotation by using the RenderTransform property</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 <span data-ttu-id="e423d-115">次の例を使用しても、<xref:System.Windows.Media.RotateTransform>を回転する、 <xref:System.Windows.Controls.Button> 45 度時計回り。 ただし、この例の設定、<xref:System.Windows.UIElement.RenderTransformOrigin%2A>するボタンの (0.5, 0.5)。</span><span class="sxs-lookup"><span data-stu-id="e423d-115">The following example also uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise; however, this example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> of the button to (0.5, 0.5).</span></span> <span data-ttu-id="e423d-116">その結果、回転は、左上隅ではなくボタンの中心に適用されています。</span><span class="sxs-lookup"><span data-stu-id="e423d-116">As a result, the rotation is applied to the center of the button instead of to the upper-left corner.</span></span>  
  
 <span data-ttu-id="e423d-117">次の図は、それに続く例の変換結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="e423d-117">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="e423d-118">![中心の周りに変換されたボタン](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span><span class="sxs-lookup"><span data-stu-id="e423d-118">![A button transformed about its center](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span></span>  
<span data-ttu-id="e423d-119">RenderTransformOrigin が (0.5, 0.5) の RenderTransform を使用した 45 度の回転</span><span class="sxs-lookup"><span data-stu-id="e423d-119">A 45 degree rotation by using the RenderTransform property with a RenderTransformOrigin of (0.5, 0.5)</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 <span data-ttu-id="e423d-120">変換の詳細については<xref:System.Windows.FrameworkElement>、オブジェクトを参照してください、[変換の概要](transforms-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="e423d-120">For more information about transforming <xref:System.Windows.FrameworkElement> objects, see the [Transforms Overview](transforms-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e423d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="e423d-121">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="e423d-122">変換の概要</span><span class="sxs-lookup"><span data-stu-id="e423d-122">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="e423d-123">方法トピック</span><span class="sxs-lookup"><span data-stu-id="e423d-123">How-to Topics</span></span>](transformations-how-to-topics.md)

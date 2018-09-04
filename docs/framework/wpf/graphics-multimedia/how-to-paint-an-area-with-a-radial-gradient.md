---
title: '方法 : 放射状グラデーションを使用して領域を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 75c28cd19ec0423589b6485884842468b89b5e8c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526792"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="08825-102">方法 : 放射状グラデーションを使用して領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="08825-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="08825-103">この例は、使用する方法を示します、<xref:System.Windows.Media.RadialGradientBrush>放射状グラデーションを使用して領域を描画するクラス。</span><span class="sxs-lookup"><span data-stu-id="08825-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08825-104">例</span><span class="sxs-lookup"><span data-stu-id="08825-104">Example</span></span>  
 <span data-ttu-id="08825-105">次の例では、<xref:System.Windows.Media.RadialGradientBrush>四角形を淡い緑、青、赤黄色から遷移放射状のグラデーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="08825-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="08825-106">次の図は、前の例のグラデーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="08825-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="08825-107">グラデーションの終了位置が強調されています。</span><span class="sxs-lookup"><span data-stu-id="08825-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="08825-108">![放射状グラデーションでのグラデーション境界](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="08825-108">![Gradient stops in a radial gradient](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08825-109">このトピックの例では、コントロール ポイントを設定するための既定の座標系を使用します。</span><span class="sxs-lookup"><span data-stu-id="08825-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="08825-110">既定の座標系は境界ボックスに対して相対的です: 0、境界ボックスの 0% を示し、1 は境界ボックスの 100% を示します。</span><span class="sxs-lookup"><span data-stu-id="08825-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="08825-111">この座標系を設定して変更することができます、<xref:System.Windows.Media.GradientBrush.MappingMode%2A>プロパティ値を<xref:System.Windows.Media.BrushMappingMode.Absolute>します。</span><span class="sxs-lookup"><span data-stu-id="08825-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="08825-112">絶対座標系は、境界ボックスに相対しません。</span><span class="sxs-lookup"><span data-stu-id="08825-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="08825-113">値は、ローカル空間に直接変換されます。</span><span class="sxs-lookup"><span data-stu-id="08825-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="08825-114">追加<xref:System.Windows.Media.RadialGradientBrush>例についてを参照してください、[ブラシのサンプル](https://go.microsoft.com/fwlink/?LinkID=159973)します。</span><span class="sxs-lookup"><span data-stu-id="08825-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="08825-115">グラデーションおよびその他の種類のブラシの詳細については、次を参照してください。[純色およびグラデーション概要](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="08825-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>

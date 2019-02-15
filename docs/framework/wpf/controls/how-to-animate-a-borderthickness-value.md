---
title: '方法: BorderThickness 値をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 96467fd013ddd2b2e215520384da2000aec68866
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56304220"
---
# <a name="how-to-animate-a-borderthickness-value"></a><span data-ttu-id="cd893-102">方法: BorderThickness 値をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="cd893-102">How to: Animate a BorderThickness Value</span></span>
<span data-ttu-id="cd893-103">この例を使用して境界線の太さに変更をアニメーション化する方法を示しています、<xref:System.Windows.Media.Animation.ThicknessAnimation>クラス。</span><span class="sxs-lookup"><span data-stu-id="cd893-103">This example shows how to animate changes to the thickness of a border by using the <xref:System.Windows.Media.Animation.ThicknessAnimation> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd893-104">例</span><span class="sxs-lookup"><span data-stu-id="cd893-104">Example</span></span>  
 <span data-ttu-id="cd893-105">次の例を使用して境界線の太さをアニメーション化<xref:System.Windows.Media.Animation.ThicknessAnimation>します。</span><span class="sxs-lookup"><span data-stu-id="cd893-105">The following example animates the thickness of a border by using <xref:System.Windows.Media.Animation.ThicknessAnimation>.</span></span> <span data-ttu-id="cd893-106">この例では、<xref:System.Windows.Controls.Border.BorderThickness%2A>プロパティの<xref:System.Windows.Controls.Border>します。</span><span class="sxs-lookup"><span data-stu-id="cd893-106">The example uses the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 <span data-ttu-id="cd893-107">サンプル全体については、次を参照してください。[アニメーション サンプル ギャラリー](https://go.microsoft.com/fwlink/?LinkID=159969)します。</span><span class="sxs-lookup"><span data-stu-id="cd893-107">For the complete sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd893-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd893-108">See also</span></span>
- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [<span data-ttu-id="cd893-109">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="cd893-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="cd893-110">アニメーションとタイミングに関するトピック</span><span class="sxs-lookup"><span data-stu-id="cd893-110">Animation and Timing How-to Topics</span></span>](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="cd893-111">キー フレームを使用して境界線の太さをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="cd893-111">Animate the Thickness of a Border by Using Key Frames</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)

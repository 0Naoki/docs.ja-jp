---
title: '方法: 反復サイクル中にアニメーション値を累積する'
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: 4b739883322751e2df86e13bfd07249abdb10a08
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146017"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a><span data-ttu-id="9cb28-102">方法: 反復サイクル中にアニメーション値を累積する</span><span class="sxs-lookup"><span data-stu-id="9cb28-102">How to: Accumulate Animation Values During Repeat Cycles</span></span>
<span data-ttu-id="9cb28-103">この例は、使用する方法を示します、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>プロパティを反復サイクル中にアニメーション値を累積します。</span><span class="sxs-lookup"><span data-stu-id="9cb28-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate animation values across repeating cycles.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cb28-104">例</span><span class="sxs-lookup"><span data-stu-id="9cb28-104">Example</span></span>  
 <span data-ttu-id="9cb28-105">使用して、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>反復サイクル中、アニメーションの底の値を累積するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9cb28-105">Use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate base values of an animation across repeating cycles.</span></span> <span data-ttu-id="9cb28-106">9 回繰り返すアニメーションを設定する場合など (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> ="9 x") 10 から 15 までアニメーション化するプロパティを設定して (から 10 を = = 15)、プロパティは、15 ~ 20 2 つ目のサイクル中に、最初のサイクル中に 10 から 15 までアニメーション化、20 ~ 25 と 3 番目のサイクル中にから。</span><span class="sxs-lookup"><span data-stu-id="9cb28-106">For example, if you set an animation to repeat 9 times (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") and you set the property to animate between 10 and 15 (From = 10 To = 15), the property animates from 10 to 15 during the first cycle, from 15 to 20 during the second cycle, from 20 to 25 during the third cycle, and so on.</span></span> <span data-ttu-id="9cb28-107">そのため、各アニメーション サイクルは、その基本値として前のアニメーション サイクルからの終了値を使用します。</span><span class="sxs-lookup"><span data-stu-id="9cb28-107">Hence, each animation cycle uses the ending animation value from the previous animation cycle as its base value.</span></span>  
  
 <span data-ttu-id="9cb28-108">使用することができます、`IsCumulative`最も基本的なアニメーションとほとんどのキー フレーム アニメーションのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9cb28-108">You can use the `IsCumulative` property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="9cb28-109">詳細については、次を参照してください。[アニメーションの概要](animation-overview.md)と[キー フレーム アニメーションの概要](key-frame-animations-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="9cb28-109">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="9cb28-110">次の例では、次の 4 つの四角形の幅をアニメーション化してこの動作を示します。</span><span class="sxs-lookup"><span data-stu-id="9cb28-110">The following example shows this behavior by animating the width of four rectangles.</span></span> <span data-ttu-id="9cb28-111">例:</span><span class="sxs-lookup"><span data-stu-id="9cb28-111">The example:</span></span>  
  
-   <span data-ttu-id="9cb28-112">最初の四角形をアニメーション化<xref:System.Windows.Media.Animation.DoubleAnimation>設定と、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="9cb28-112">Animates the first rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="9cb28-113">2 番目の四角形をアニメーション化<xref:System.Windows.Media.Animation.DoubleAnimation>設定と、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>プロパティの既定値を`false`します。</span><span class="sxs-lookup"><span data-stu-id="9cb28-113">Animates the second rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to the default value of `false`.</span></span>  
  
-   <span data-ttu-id="9cb28-114">含む 3 番目の四角形をアニメーション化<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>設定と、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="9cb28-114">Animates the third rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="9cb28-115">含む最後の四角形をアニメーション化<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>設定と、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="9cb28-115">Animates the last rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `false`.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9cb28-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cb28-116">See also</span></span>

- [<span data-ttu-id="9cb28-117">アニメーションの出力値をアニメーションの開始値に追加する</span><span class="sxs-lookup"><span data-stu-id="9cb28-117">Add an Animation Output Value to an Animation Starting Value</span></span>](how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [<span data-ttu-id="9cb28-118">アニメーションを反復する</span><span class="sxs-lookup"><span data-stu-id="9cb28-118">Repeat an Animation</span></span>](how-to-repeat-an-animation.md)
- [<span data-ttu-id="9cb28-119">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="9cb28-119">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="9cb28-120">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="9cb28-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="9cb28-121">方法トピック</span><span class="sxs-lookup"><span data-stu-id="9cb28-121">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)

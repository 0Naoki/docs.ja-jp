---
title: イージング関数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
ms.openlocfilehash: 038d9423ddae6f16165ed0618beab8391c462ac9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2018
ms.locfileid: "43461710"
---
# <a name="easing-functions"></a><span data-ttu-id="52e5c-102">イージング関数</span><span class="sxs-lookup"><span data-stu-id="52e5c-102">Easing Functions</span></span>
<span data-ttu-id="52e5c-103">イージング関数を使うと、独自の数式をアニメーションに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="52e5c-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="52e5c-104">たとえば、オブジェクトをリアルにバウンドさせたり、バネに乗っているように動作させたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="52e5c-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="52e5c-105">キー フレーム アニメーションや From/To/By アニメーションを使ってこれらの効果を近似することもできますが、大量の作業が必要であり、アニメーションは数式を使うほど正確ではありません。</span><span class="sxs-lookup"><span data-stu-id="52e5c-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="52e5c-106">継承することによって、独自のカスタム イージング関数を作成するだけでなく<xref:System.Windows.Media.Animation.EasingFunctionBase>、ランタイムによって提供されるいくつかのイージング関数のいずれかを使用して、一般的な効果を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="52e5c-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
-   <span data-ttu-id="52e5c-107"><xref:System.Windows.Media.Animation.BackEase>: 取り消されますアニメーションの動き若干指定されたパスのアニメーションを開始する前に。</span><span class="sxs-lookup"><span data-stu-id="52e5c-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
-   <span data-ttu-id="52e5c-108"><xref:System.Windows.Media.Animation.BounceEase>: バウンド効果を作成します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
-   <span data-ttu-id="52e5c-109"><xref:System.Windows.Media.Animation.CircleEase>: 円関数を使って加速および減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
-   <span data-ttu-id="52e5c-110"><xref:System.Windows.Media.Animation.CubicEase>: 式を使って加速および減速するアニメーションを作成します。 *f*(*t*) = *t*<sup>3</sup>します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
-   <span data-ttu-id="52e5c-111"><xref:System.Windows.Media.Animation.ElasticEase>: スプリングが伸び縮みし静止するまでのようなアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
-   <span data-ttu-id="52e5c-112"><xref:System.Windows.Media.Animation.ExponentialEase>: 指数の式を使って加速および減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
-   <span data-ttu-id="52e5c-113"><xref:System.Windows.Media.Animation.PowerEase>: 式を使って加速および減速するアニメーションを作成します。 *f*(*t*) = *t*<sup>p</sup> p は、 <xref:System.Windows.Media.Animation.PowerEase.Power%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="52e5c-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
-   <span data-ttu-id="52e5c-114"><xref:System.Windows.Media.Animation.QuadraticEase>: 式を使って加速および減速するアニメーションを作成します。 *f*(*t*) = *t*<sup>2</sup>します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
-   <span data-ttu-id="52e5c-115"><xref:System.Windows.Media.Animation.QuarticEase>: 式を使って加速および減速するアニメーションを作成します。 *f*(*t*) = *t*<sup>4</sup>します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
-   <span data-ttu-id="52e5c-116"><xref:System.Windows.Media.Animation.QuinticEase>: 作成、数式を使って加速および減速するアニメーション*f*(*t*) = *t*<sup>5</sup>します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
-   <span data-ttu-id="52e5c-117"><xref:System.Windows.Media.Animation.SineEase>: 正弦公式を使って加速および減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="52e5c-118">アニメーションにイージング関数を適用するには、使用、`EasingFunction`アニメーションのプロパティがアニメーションに適用するイージング関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="52e5c-119">次の例では、適用、<xref:System.Windows.Media.Animation.BounceEase>イージング関数を<xref:System.Windows.Media.Animation.DoubleAnimation>バウンド効果を作成します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="52e5c-120">前の例では、イージング関数を From/To/By アニメーションに適用しました。</span><span class="sxs-lookup"><span data-stu-id="52e5c-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="52e5c-121">キー フレーム アニメーションにこれらのイージング関数を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="52e5c-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="52e5c-122">次の例では、キー フレームとそれらに関連付けられたイージング関数を使って、四角形が上方に縮まり、遅くなり、下方に延び (落下するように)、停止するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="52e5c-123">使用することができます、<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>イージング関数の動作方法は、変更するプロパティがアニメーションの補間方法を変更します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="52e5c-124">3 つの値を与えることができますがある<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="52e5c-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
-   <span data-ttu-id="52e5c-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: 補間では、イージング関数に関連付けられた数式に従います。</span><span class="sxs-lookup"><span data-stu-id="52e5c-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="52e5c-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: 補間では、イージング関数に関連付けられた数式の出力を引いた値 100% の補間に従います。</span><span class="sxs-lookup"><span data-stu-id="52e5c-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="52e5c-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: 補間を使用して<xref:System.Windows.Media.Animation.EasingMode.EaseIn>アニメーションの前半と<xref:System.Windows.Media.Animation.EasingMode.EaseOut>後半。</span><span class="sxs-lookup"><span data-stu-id="52e5c-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="52e5c-128">以下のグラフのさまざまな値を示す<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>場所*f*(*x*) アニメーションの進行状況を表すと*t*時間を表します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="52e5c-129">![BackEase EasingMode のグラフ。](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="52e5c-129">![BackEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="52e5c-130">![BounceEase EasingMode のグラフ。](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="52e5c-130">![BounceEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="52e5c-131">![CircleEase EasingMode のグラフ。](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="52e5c-131">![CircleEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="52e5c-132">![CubicEase EasingMode のグラフ。](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="52e5c-132">![CubicEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="52e5c-133">![異なる EasingMode の ElasticEase のグラフ。](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="52e5c-133">![ElasticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="52e5c-134">![異なる EasingMode の ExponentialEase のグラフ。](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="52e5c-134">![ExponentialEase graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="52e5c-135">![異なる EasingMode の QuarticEase のグラフ。](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="52e5c-135">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="52e5c-136">![異なる EasingMode の QuadraticEase のグラフ。](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="52e5c-136">![QuadraticEase with graphs of different easingmodes](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="52e5c-137">![異なる EasingMode の QuarticEase のグラフ。](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="52e5c-137">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="52e5c-138">![異なる EasingMode の QuinticEase のグラフ。](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="52e5c-138">![QuinticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="52e5c-139">![異なる EasingMode 値の SineEase](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="52e5c-139">![SineEase for different EasingMode values](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52e5c-140">使用することができます<xref:System.Windows.Media.Animation.PowerEase>と同じ動作を作成する<xref:System.Windows.Media.Animation.CubicEase>、 <xref:System.Windows.Media.Animation.QuadraticEase>、 <xref:System.Windows.Media.Animation.QuarticEase>、および<xref:System.Windows.Media.Animation.QuinticEase>を使用して、<xref:System.Windows.Media.Animation.PowerEase.Power%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="52e5c-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="52e5c-141">たとえば、使用する<xref:System.Windows.Media.Animation.PowerEase>の代わりに<xref:System.Windows.Media.Animation.CubicEase>を指定、 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 3 の値。</span><span class="sxs-lookup"><span data-stu-id="52e5c-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="52e5c-142">継承することによって、独自のカスタム イージング関数を作成するだけでなく、実行時に含まれるイージング関数を使用して、<xref:System.Windows.Media.Animation.EasingFunctionBase>します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="52e5c-143">次の例では、簡単なカスタム イージング関数を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="52e5c-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="52e5c-144">イージング関数の動作をオーバーライドすることで、独自の数値演算ロジックを追加することができます、<xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="52e5c-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]

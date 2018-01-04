---
title: "方法 : 反復サイクル中にアニメーション値を累積する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96a91856cdfcf1ca7ae87e8e571306170feecb7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>方法 : 反復サイクル中にアニメーション値を累積する
この例を使用する方法を示しています、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>反復サイクル全体でアニメーションの値を累積するプロパティです。  
  
## <a name="example"></a>例  
 使用して、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>反復サイクル全体でアニメーションの基本値を蓄積するプロパティです。 たとえば、9 回繰り返して、アニメーションを設定する場合 (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> "9 x"=) 10 から 15 までアニメーション化するプロパティを設定して (= 10 = 15)、プロパティにアニメーションを付ける 10 から 15 サイクル中に、最初、15、2 つ目のサイクルの 20 ~、25 の間に、3 つ目のサイクルの 20 です。 そのため、各アニメーション サイクルは、その基本値として前のアニメーション サイクルの終了値を使用します。  
  
 使用することができます、`IsCumulative`最も基本的なアニメーションとほとんどのキー フレーム アニメーションのプロパティです。 詳細については、次を参照してください。[アニメーションの概要](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)と[キー フレーム アニメーションの概要](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)です。  
  
 次の例では、次の 4 つの四角形の幅をアニメーション化によってこの動作を示します。 例:  
  
-   最初の四角形をアニメーション化<xref:System.Windows.Media.Animation.DoubleAnimation>設定と、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>プロパティを`true`です。  
  
-   含む 2 つ目の四角形をアニメーション化<xref:System.Windows.Media.Animation.DoubleAnimation>設定と、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>プロパティの既定値を`false`です。  
  
-   含む 3 つ目の四角形をアニメーション化<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>設定と、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A>プロパティを`true`です。  
  
-   含む最後の四角形をアニメーション化<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>設定と、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A>プロパティを`false`です。  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>参照  
 [アニメーションの出力値をアニメーションの開始値に追加する](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)  
 [アニメーションを反復する](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)  
 [アニメーションの概要](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [キー フレーム アニメーションの概要](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [方法トピック](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)

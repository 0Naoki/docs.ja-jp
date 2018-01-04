---
title: "方法 : アニメーションの継続時間を設定する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e8d15a1b8432b3dae5bee73396bdec9fc9d50f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-duration-for-an-animation"></a>方法 : アニメーションの継続時間を設定する
A<xref:System.Windows.Media.Animation.Timeline>を表す時間のセグメントとそのセグメントの長さは、タイムラインのによって決まります<xref:System.Windows.Duration>です。 ときに、<xref:System.Windows.Media.Animation.Timeline>が最後に達するとその継続時間の再生は停止します。 場合、<xref:System.Windows.Media.Animation.Timeline>が子タイムラインも再生を停止します。 アニメーションの場合、<xref:System.Windows.Duration>アニメーションにかかる時間の遷移の終了値をその開始値からを指定します。  
  
 指定することができます、 <xref:System.Windows.Duration> 、有限の特定の時間または特別な値を持つ<xref:System.Windows.Duration.Automatic%2A>または<xref:System.Windows.Duration.Forever%2A>です。 アニメーションの継続時間は常にある時間の値、アニメーションが定義されている、有限の長さを持つ必要がありますので、それ以外の場合、アニメーションはかわからないターゲット値の間で移行する方法です。 コンテナー タイムライン (<xref:System.Windows.Media.Animation.TimelineGroup>オブジェクト) など<xref:System.Windows.Media.Animation.Storyboard>と<xref:System.Windows.Media.Animation.ParallelTimeline>の既定の時間が指定されて<xref:System.Windows.Duration.Automatic%2A>、つまり、これらは、最後の子が停止したときに自動的に終了します。  
  
 次の例、幅、高さ、および塗りつぶしの色、<xref:System.Windows.Shapes.Rectangle>がアニメーション化します。 期間は、アニメーション効果をアニメーションの見かけ上の速度を制御するコンテナ タイムラインの存続期間を持つ子タイムラインの期間のオーバーライドなどに、アニメーションとコンテナーのタイムラインに設定されます。  
  
## <a name="example"></a>例  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.Duration>  
 [アニメーションの概要](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)

---
title: '方法: タイムラインの速度を変更せずにクロックの速度を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
ms.openlocfilehash: 19e6874b9b472cb4a5f716677f99af03f2b73b10
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358276"
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a><span data-ttu-id="6e2e7-102">方法: タイムラインの速度を変更せずにクロックの速度を変更する</span><span class="sxs-lookup"><span data-stu-id="6e2e7-102">How to: Change the Speed of a Clock Without Changing the Speed of Its Timeline</span></span>
<span data-ttu-id="6e2e7-103">A<xref:System.Windows.Media.Animation.ClockController>オブジェクトの<xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>プロパティでは、速度を変更することができます、<xref:System.Windows.Media.Animation.Clock>を変えることがなく、<xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>のクロックの<xref:System.Windows.Media.Animation.Timeline>します。</span><span class="sxs-lookup"><span data-stu-id="6e2e7-103">A <xref:System.Windows.Media.Animation.ClockController> object's <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> property enables you to change the speed of a <xref:System.Windows.Media.Animation.Clock> without altering the <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> of the clock's <xref:System.Windows.Media.Animation.Timeline>.</span></span> <span data-ttu-id="6e2e7-104">次の例では、<xref:System.Windows.Media.Animation.ClockController>を対話的に変更するために使用、<xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>クロックの。</span><span class="sxs-lookup"><span data-stu-id="6e2e7-104">In the following example, a <xref:System.Windows.Media.Animation.ClockController> is used to interactively modify the <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> of a clock.</span></span> <span data-ttu-id="6e2e7-105"><xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated>イベントと、クロックの<xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A>プロパティを使用して、クロックの現在のグローバル速度を表示するたびに、対話型<xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>が変更されました。</span><span class="sxs-lookup"><span data-stu-id="6e2e7-105">The <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> event and the clock's <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> property are used to display the clock's current global speed each time its interactive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> is changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e2e7-106">例</span><span class="sxs-lookup"><span data-stu-id="6e2e7-106">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]

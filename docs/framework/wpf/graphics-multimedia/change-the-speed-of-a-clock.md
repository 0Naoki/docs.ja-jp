---
title: "方法 : タイムラインの速度を変更せずにクロックの速度を変更する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 98cfa63eac4bc697c5412616de71395624408c63
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a>方法 : タイムラインの速度を変更せずにクロックの速度を変更する
A<xref:System.Windows.Media.Animation.ClockController>オブジェクトの<xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>プロパティでは、速度を変更することができます、<xref:System.Windows.Media.Animation.Clock>を変更せず、<xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>の時計の<xref:System.Windows.Media.Animation.Timeline>します。 次の例で、<xref:System.Windows.Media.Animation.ClockController>対話的に変更することは、<xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>時計のです。 <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated>イベントと、クロックの<xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A>プロパティは、クロックの現在のグローバル速度を表示に使用されるたびに、対話による<xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>が変更されました。  
  
## <a name="example"></a>例  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]

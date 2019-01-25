---
title: '方法: イベントの発生時に要素に変換を適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
ms.openlocfilehash: 3862ffcb8e0dcabd2de67c495204470ac9fa6c14
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726391"
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a>方法: イベントの発生時に要素に変換を適用する
この例は、適用する方法を示します、<xref:System.Windows.Media.ScaleTransform>イベントが発生します。 ここで示される概念は、他の種類の変換を適用する場合に使用するものと同じです。 使用可能な種類の変換の詳細については、次を参照してください。、<xref:System.Windows.Media.Transform>クラスまたは[変換の概要](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)します。  
  
 要素に変換を適用するには、次の 2 つの方法があります。  
  
-   操作を行う場合*いない*レイアウトに影響を使用して変換する、<xref:System.Windows.UIElement.RenderTransform%2A>要素のプロパティ。  
  
-   レイアウトに影響する変換をする場合は、使用、<xref:System.Windows.FrameworkElement.LayoutTransform%2A>要素のプロパティ。  
  
 次の例では、適用、<xref:System.Windows.Media.ScaleTransform>を<xref:System.Windows.UIElement.RenderTransform%2A>ボタンのプロパティ。 マウスがボタンの上に移動したときに、<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>と<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>のプロパティ、<xref:System.Windows.Media.ScaleTransform>に設定されている`2`、ボタンのサイズが大きくなります。 オフにする、ボタン、マウスが移動したときに<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>と<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>に設定されて`1`、ボタンの元のサイズに戻ります。  
  
## <a name="example"></a>例  
 [!code-xaml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [変換の概要](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
- [方法トピック](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
- [ルーティング イベントの概要](../../../../docs/framework/wpf/advanced/routed-events-overview.md)

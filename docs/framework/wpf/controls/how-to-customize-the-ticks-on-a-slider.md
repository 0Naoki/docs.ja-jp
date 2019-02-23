---
title: '方法: スライダーの目盛りをカスタマイズする'
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 0317668bf4f6721af698e1a8b966493b2c127012
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746650"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a>方法: スライダーの目盛りをカスタマイズする
この例は、作成する方法を示します、<xref:System.Windows.Controls.Slider>目盛りがあるコントロール。  
  
## <a name="example"></a>例  
 <xref:System.Windows.Controls.Primitives.TickBar>表示を設定すると、<xref:System.Windows.Controls.Slider.TickPlacement%2A>プロパティ以外の値を<xref:System.Windows.Controls.Primitives.TickPlacement.None>、これは、既定値。  
  
 次の例は、作成する方法を示します、<xref:System.Windows.Controls.Slider>で、<xref:System.Windows.Controls.Primitives.TickBar>ことが表示されますが目盛り。 <xref:System.Windows.Controls.Slider.TickPlacement%2A>と<xref:System.Windows.Controls.Slider.TickFrequency%2A>プロパティは、目盛りとそれらの間の間隔の場所を定義します。 移動すると、 <xref:System.Windows.Controls.Primitives.Thumb>、ツール ヒントの値を表示する、<xref:System.Windows.Controls.Slider>します。 <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A>プロパティは、ツールヒントが表示される場所を定義します。 <xref:System.Windows.Controls.Primitives.Thumb>ため目盛りの場所に対応して動き<xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A>に設定されている`true`します。  
  
 次の例は、使用する方法を示します、<xref:System.Windows.Controls.Slider.Ticks%2A>マークに沿った目盛りを作成するプロパティ、<xref:System.Windows.Controls.Slider>間隔は不規則です。  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- [方法: スライダーをプロパティの値にバインドします。](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))

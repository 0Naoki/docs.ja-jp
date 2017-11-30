---
title: "方法 : StackPanel を作成する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b5ba089c671fe54afe1c97da0a7bd786949cb5c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-stackpanel"></a>方法 : StackPanel を作成する
この例を作成する方法を示しています、<xref:System.Windows.Controls.StackPanel>です。  
  
## <a name="example"></a>例  
 A<xref:System.Windows.Controls.StackPanel>指定した方向に要素をスタックすることができます。 定義されているプロパティを使用して<xref:System.Windows.Controls.StackPanel>、コンテンツ フローできます両方垂直方向には、これは既定の設定、または水平方向にします。  
  
 5 は、次の例が垂直方向に積み上げ<xref:System.Windows.Controls.TextBlock>制御する場合に、それぞれ異なる<xref:System.Windows.Controls.Border>と<xref:System.Windows.Controls.Border.Background%2A>を使用して<xref:System.Windows.Controls.StackPanel>です。 指定されて子要素<xref:System.Windows.FrameworkElement.Width%2A>stretch を親ウィンドウです。 ただし、子要素がある、指定した<xref:System.Windows.FrameworkElement.Width%2A>、ウィンドウ内で中央揃えで配置しません。  
  
 既定のスタック方向、<xref:System.Windows.Controls.StackPanel>は縦方向です。 コントロールのコンテンツ フローに、<xref:System.Windows.Controls.StackPanel>を使用して、<xref:System.Windows.Controls.StackPanel.Orientation%2A>プロパティです。 使用して、水平方向の配置を制御することができます、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>プロパティです。  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Controls.StackPanel>  
 [パネルの概要](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [方法トピック](../../../../docs/framework/wpf/controls/stackpanel-how-to-topics.md)

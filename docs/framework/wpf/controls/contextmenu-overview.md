---
title: ContextMenu の概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: e862f02e736cb8507dde5036700d751f8af0a226
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552871"
---
# <a name="contextmenu-overview"></a>ContextMenu の概要
<xref:System.Windows.Controls.ContextMenu>クラスは、特定のコンテキストを使用して、機能を公開する要素を表します<xref:System.Windows.Controls.Menu>です。 通常、ユーザーが公開する、<xref:System.Windows.Controls.ContextMenu>で、[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]をマウスのボタンを右クリックします。 このトピックでは、<xref:System.Windows.Controls.ContextMenu>要素で使用する方法の例を示します[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]とコード。  
  
  
  
<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a>ContextMenu コントロール  
 A<xref:System.Windows.Controls.ContextMenu>は特定のコントロールにアタッチされています。 <xref:System.Windows.Controls.ContextMenu>要素では、コマンドまたはなどで、特定のコントロールに関連付けられているオプションを指定する項目の一覧をユーザーに提示することができます、<xref:System.Windows.Controls.Button>です。 ユーザーがコントロールを右クリックすると、メニューが表示されます。 通常をクリックすると、<xref:System.Windows.Controls.MenuItem>サブメニューを開くかにより、アプリケーションは、コマンドを実行します。  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a>ContextMenu の作成  
 次の例を作成する方法を示して、<xref:System.Windows.Controls.ContextMenu>サブメニューのあります。 <xref:System.Windows.Controls.ContextMenu>ボタン コントロールに関連付けられているコントロール。  
  
 [!code-xaml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a>ContextMenu へのスタイルの適用  
 コントロールを使用して<xref:System.Windows.Style>の動作と外観を大幅に変更することができます、<xref:System.Windows.Controls.ContextMenu>カスタム コントロールを記述することがなくです。 視覚プロパティの設定に加えて、コントロールの一部にスタイルを適用することもできます。 たとえば、コントロールの一部の動作を変更するには、プロパティを使用して、または、パーツを追加したりのレイアウトを変更、<xref:System.Windows.Controls.ContextMenu>です。 次の例では、いくつかの方法でスタイルを追加して<xref:System.Windows.Controls.ContextMenu>コントロール。  
  
 最初の例では、`SimpleSysResources` という名前のスタイルを定義し、スタイルで現在のシステム設定を使用する方法を示します。 例では、<xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A>として、<xref:System.Windows.Controls.Control.Background%2A>色と<xref:System.Windows.SystemColors.MenuTextBrushKey%2A>として、<xref:System.Windows.Controls.Control.Foreground%2A>の色、<xref:System.Windows.Controls.ContextMenu>です。  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 次の例では、<xref:System.Windows.Trigger>の外観を変更する要素、<xref:System.Windows.Controls.Menu>上で発生したイベントに応答、<xref:System.Windows.Controls.ContextMenu>です。 ユーザーが、メニューの外観にマウスを移動するときに、<xref:System.Windows.Controls.ContextMenu>項目を変更します。  
  
```xaml  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.Menu>  
 <xref:System.Windows.Controls.MenuItem>  
 [ContextMenu](../../../../docs/framework/wpf/controls/contextmenu.md)  
 [ContextMenu のスタイルとテンプレート](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md)  
 [WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053)

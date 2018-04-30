---
title: 'パフォーマンスの最適化 : その他の推奨事項'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Terminal Services rendering [WPF]
- opacity [WPF]
- hit-test objects [WPF]
- ScrollBarVisibility enumeration [WPF]
- brushes [WPF], performance
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: afe0e93706089e1893d46316b33c2568df83ffd3
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2018
---
# <a name="optimizing-performance-other-recommendations"></a>パフォーマンスの最適化 : その他の推奨事項
<a name="introduction"></a> このトピックでは、「[WPF アプリケーションのパフォーマンスの最適化](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)」セクションのトピックで説明されている推奨事項を補足するパフォーマンスに関する推奨事項について取り上げます。  
  
 このトピックは、次のセクションで構成されています。  
  
-   [ブラシの Opacity と要素の Opacity](#Opacity)  
  
-   [オブジェクトへの移動](#Navigation_Objects)  
  
-   [大きな 3D サーフェイスのヒット テスト](#Hit_Testing)  
  
-   [CompositionTarget.Rendering イベント](#CompositionTarget_Rendering_Event)  
  
-   [ScrollBarVisibility=Auto は使用しない](#Avoid_Using_ScrollBarVisibility)  
  
-   [Font Cache サービスの構成による起動時間の短縮](#FontCache)  
  
<a name="Opacity"></a>   
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a>ブラシの Opacity と要素の Opacity  
 使用すると、<xref:System.Windows.Media.Brush>を設定する、<xref:System.Windows.Shapes.Shape.Fill%2A>または<xref:System.Windows.Shapes.Shape.Stroke%2A>、要素のことをお勧めを設定する、<xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType>値の設定ではなく、要素の<xref:System.Windows.UIElement.Opacity%2A>プロパティです。 要素の変更<xref:System.Windows.UIElement.Opacity%2A>プロパティが生成されることができます[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]を一時的な画面を作成します。  
  
<a name="Navigation_Objects"></a>   
## <a name="navigation-to-object"></a>オブジェクトへの移動  
 <xref:System.Windows.Navigation.NavigationWindow>から派生したオブジェクト<xref:System.Windows.Window>および集計することによって、主に、コンテンツ ナビゲーションのサポートを備えた拡張<xref:System.Windows.Navigation.NavigationService>およびジャーナルです。 クライアント領域を更新する<xref:System.Windows.Navigation.NavigationWindow>いずれかを指定することによって、[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]またはオブジェクト。 この両方の方法を次のサンプルに示します。  
  
 [!code-csharp[Performance#PerformanceSnippet14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 各<xref:System.Windows.Navigation.NavigationWindow>オブジェクトには、journal ウィンドウで、ユーザーのナビゲーション履歴を記録します。 履歴の目的の 1 つは、ユーザーが自分の来た道を戻れるようにすることです。  
  
 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] を使用して移動した場合、履歴には [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] の参照のみが格納されます。 したがって、ページに戻るたびにそのページが動的に再構築されることになり、ページの複雑さによってはかなりの時間がかかることもあります。 この場合、履歴の格納の負荷は低い反面、ページの再構築にかかる時間が長くなる可能性があります。  
  
 オブジェクトを使用して移動した場合は、オブジェクトのビジュアル ツリー全体が履歴に格納されます。 したがって、ページに戻るたびにページを再構築する必要はなく、ページがすぐに描画されます。 この場合、履歴の格納の負荷は高くなりますが、ページの再構築にかかる時間は短くて済みます。  
  
 使用すると、<xref:System.Windows.Navigation.NavigationWindow>オブジェクト、ジャーナリング サポートと、アプリケーションのパフォーマンスがどのように影響しているか注意する必要があります。 詳細については、「[ナビゲーションの概要](../../../../docs/framework/wpf/app-development/navigation-overview.md)」を参照してください。  
  
<a name="Hit_Testing"></a>   
## <a name="hit-testing-on-large-3d-surfaces"></a>大きな 3D サーフェイスのヒット テスト  
 大きな 3D サーフェイスのヒット テストは、CPU 消費の面でパフォーマンスへの影響が非常に大きくなります。 3D サーフェイスがアニメーション化されている場合には特にその傾向が強くなります。 そのようなサーフェイスでヒット テストを行う必要がない場合は、ヒット テストを無効にしてください。 派生したオブジェクト<xref:System.Windows.UIElement>できます無効にするヒット テストの設定によって、<xref:System.Windows.UIElement.IsHitTestVisible%2A>プロパティを`false`です。  
  
<a name="CompositionTarget_Rendering_Event"></a>   
## <a name="compositiontargetrendering-event"></a>CompositionTarget.Rendering イベント  
 <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType>イベントにより[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]継続的にアニメーション化します。 このイベントを使用する場合は、毎回デタッチしてください。  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>   
## <a name="avoid-using-scrollbarvisibilityauto"></a>ScrollBarVisibility=Auto は使用しない  
 可能な限り回避を使用して、<xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType>値を`HorizontalScrollBarVisibility`と`VerticalScrollBarVisibility`プロパティです。 これらのプロパティが定義されている<xref:System.Windows.Controls.RichTextBox>、 <xref:System.Windows.Controls.ScrollViewer>、および<xref:System.Windows.Controls.TextBox>オブジェクトとの添付プロパティとして、<xref:System.Windows.Controls.ListBox>オブジェクト。 代わりに、設定<xref:System.Windows.Controls.ScrollBarVisibility>に<xref:System.Windows.Controls.ScrollBarVisibility.Disabled>、 <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>、または<xref:System.Windows.Controls.ScrollBarVisibility.Visible>です。  
  
 <xref:System.Windows.Controls.ScrollBarVisibility.Auto>値は、ケースの空き領域が少ないと、スクロール バーは、必要な場合にのみ表示されます。 たとえば、ある可能性がありますを使用してこの<xref:System.Windows.Controls.ScrollBarVisibility>値と、<xref:System.Windows.Controls.ListBox>はなく 30 の項目の<xref:System.Windows.Controls.TextBox>何百もの行のテキスト。  
  
<a name="FontCache"></a>   
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a>Font Cache サービスの構成による起動時間の短縮  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Font Cache サービスは、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] アプリケーション間でフォント データを共有します。 このサービスがまだ実行されていない場合は、実行する最初の [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] アプリケーションによって開始されます。 使用している場合[!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]の初回起動時時間を短縮する「自動 (遅延開始)」の「手動」(既定値) からの"Windows Presentation Foundation (WPF) フォント Cache 3.0.0.0"サービスを設定することができます[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]アプリケーションです。  
  
## <a name="see-also"></a>関連項目  
 [アプリケーション パフォーマンスの計画](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [ハードウェアの活用](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [レイアウトとデザイン](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2D グラフィックスとイメージング](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [オブジェクトの動作](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [アプリケーション リソース](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [[テキスト]](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [データ バインディング](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [アニメーションのヒントとテクニック](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)

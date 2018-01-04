---
title: "パフォーマンスの最適化 : レイアウトとデザイン"
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
- layout [WPF], optimizing performance
- design considerations [WPF]
- layout pass [WPF]
ms.assetid: 005f4cda-a849-448b-916b-38d14d9a96fe
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df87170b05f830916ef2f77fd4cb5a4abab42faa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="optimizing-performance-layout-and-design"></a>パフォーマンスの最適化 : レイアウトとデザイン
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションの設計によっては、レイアウトの計算やオブジェクト参照の検証で不要なオーバーヘッドが発生して、パフォーマンスに影響が及ぶことがあります。 オブジェクトの作成 (特に実行時の作成) はアプリケーションのパフォーマンス特性に影響する可能性があります。  
  
 このトピックでは、このようなパフォーマンスに関する推奨事項について説明します。  
  
## <a name="layout"></a>レイアウト  
 「レイアウト パス」という用語は、測定と配置のメンバーのプロセスを説明します、 <xref:System.Windows.Controls.Panel>-派生したオブジェクトのコレクションの子、およびそれらの画面を描画します。 レイアウト パスは数学的に増大するプロセスで、コレクション内の子の数が多くなれば、必要な計算の数も多くなります。 たとえば、たびに、子<xref:System.Windows.UIElement>コレクション内のオブジェクトがその位置を変更、レイアウト システムによって新しいパスをトリガーする可能性があります。 オブジェクトの特性とレイアウトの動作の間には密接な関係があるため、レイアウト システムを呼び出すことができるイベントの種類を把握することが重要です。 レイアウト パスの不要な呼び出しをできるだけ減らすことで、アプリケーションのパフォーマンスを向上させることができます。  
  
 レイアウト システムは、コレクションの子メンバーごとに、測定パスと配置パスという 2 つのパスを実行します。 各子オブジェクトのオーバーライドされた実装を提供する、<xref:System.Windows.UIElement.Measure%2A>と<xref:System.Windows.UIElement.Arrange%2A>は独自の特定のレイアウト動作を提供するためのメソッドです。 簡単に言うと、レイアウトは、要素のサイズ測定、配置、画面上への描画を繰り返す再帰的なシステムです。  
  
-   子<xref:System.Windows.UIElement>オブジェクトでは、測定の中核となるプロパティを持つ最初からレイアウト プロセスを開始します。  
  
-   オブジェクトの<xref:System.Windows.FrameworkElement>など、サイズに関連するプロパティ<xref:System.Windows.FrameworkElement.Width%2A>、 <xref:System.Windows.FrameworkElement.Height%2A>、および<xref:System.Windows.FrameworkElement.Margin%2A>、評価されます。  
  
-   <xref:System.Windows.Controls.Panel>-など特定のロジックが適用される、<xref:System.Windows.Controls.DockPanel.Dock%2A>のプロパティ、 <xref:System.Windows.Controls.DockPanel>、または<xref:System.Windows.Controls.StackPanel.Orientation%2A>のプロパティ、<xref:System.Windows.Controls.StackPanel>です。  
  
-   すべての子オブジェクトが測定された後、コンテンツが配置されます。  
  
-   子オブジェクトのコレクションが画面に描画されます。  
  
 以下のアクションが発生すると、再びレイアウト パス プロセスが呼び出されます。  
  
-   子オブジェクトがコレクションに追加された場合。  
  
-   A<xref:System.Windows.FrameworkElement.LayoutTransform%2A>は子オブジェクトに適用します。  
  
-   <xref:System.Windows.UIElement.UpdateLayout%2A>子オブジェクトのメソッドが呼び出されます。  
  
-   測定パスや配置パスに影響を与えるものとしてメタデータでマークされている依存関係プロパティの値が変更された場合。  
  
### <a name="use-the-most-efficient-panel-where-possible"></a>可能な場合は最も効率的なパネルを使用する  
 レイアウトの動作に直接基づくレイアウト処理の複雑さ、 <xref:System.Windows.Controls.Panel>-使用する要素を派生します。 たとえば、<xref:System.Windows.Controls.Grid>または<xref:System.Windows.Controls.StackPanel>コントロールより多くの機能が用意されています、<xref:System.Windows.Controls.Canvas>コントロール。 はるかに多くの機能が用意されていますが、その代償として、パフォーマンスへの負荷も高くなります。 ただし、機能を必要としない場合、<xref:System.Windows.Controls.Grid>コントロールが提供するなどの低コストの代替手段を使用する必要があります、<xref:System.Windows.Controls.Canvas>またはカスタムのパネルです。  
  
 詳細については、「[Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md)」を参照してください。  
  
### <a name="update-rather-than-replace-a-rendertransform"></a>RenderTransform は置き換えずに更新する  
 更新することができます、<xref:System.Windows.Media.Transform>の値と置き換えるのではなく、<xref:System.Windows.UIElement.RenderTransform%2A>プロパティです。 アニメーションを含むシナリオでは特にこれが当てはまります。 既存の更新によって<xref:System.Windows.Media.Transform>、不要なレイアウト計算を開始するを回避します。  
  
### <a name="build-your-tree-top-down"></a>ツリーはトップダウンで作成する  
 論理ツリーのノードが追加または削除されると、ノードの親とそのすべての子でプロパティの無効化が行われます。 このため、常にトップダウンの作成パターンに従って、検証済みのノードで無駄に無効化が行われないようにする必要があります。 次の表は、ツリーをボトムアップ ツリー 150 レベルの深さを 1 つは、ここではなく上から下へのビルドの実行速度の差<xref:System.Windows.Controls.TextBlock>と<xref:System.Windows.Controls.DockPanel>レベルごとにします。  
  
|**動作**|**ツリーの作成 (ミリ秒)**|**レンダリング-ツリーの作成を含む (ミリ秒)**|  
|----------------|---------------------------------|-------------------------------------------------|  
|ボトムアップ|366|454|  
|トップダウン|11|96|  
  
 ツリーをトップダウンで作成する方法を次のコード例に示します。  
  
 [!code-csharp[Performance#PerformanceSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet1)]
 [!code-vb[Performance#PerformanceSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet1)]  
  
 論理ツリーについて詳しくは、「[WPF のツリー](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [WPF アプリケーションのパフォーマンスの最適化](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [アプリケーション パフォーマンスの計画](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [ハードウェアの活用](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [2D グラフィックスとイメージング](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [オブジェクトの動作](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [アプリケーション リソース](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [[テキスト]](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [データ バインディング](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [パフォーマンスに関するその他の推奨事項](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
 [レイアウト](../../../../docs/framework/wpf/advanced/layout.md)

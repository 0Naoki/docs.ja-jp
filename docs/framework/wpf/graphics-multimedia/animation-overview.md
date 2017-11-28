---
title: "アニメーションの概要"
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
- Storyboards [WPF], animations
- animations [WPF], overview
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
caps.latest.revision: "73"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15eeb27d493cd1138b0d3d41b55a57228a226a11
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2017
---
# <a name="animation-overview"></a>アニメーションの概要
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]強力な一連の魅力的なユーザー インターフェイスやドキュメントを作成するグラフィックスおよびレイアウトの機能を提供します。 アニメーションを使うと、魅力的なユーザー インターフェイスをさらに豪華で使いやすいものにすることができます。 背景色をアニメーション化や、アニメーションを適用するだけで<xref:System.Windows.Media.Transform>、大幅な画面の遷移を作成したり、便利な視覚的な手掛かりを提供します。  
  
 この概要について説明する、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アニメーションおよびタイミング システムです。 アニメーションに焦点を[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ストーリー ボードを使用して、オブジェクトです。  

<a name="introducinganimations"></a>   
## <a name="introducing-animations"></a>アニメーションの概要  
 アニメーションは、それぞれが直前のイメージと少しずつ異なる一連のイメージをすばやく繰り返すことで生み出される錯覚です。 脳は、イメージのグループを 1 つの変化するシーンとして認識します。 映画では、この錯覚は 1 秒あたりに多数の写真またはフレームを記録するカメラを使って生み出されます。 フレームを映写機で再生すると、見る人には動く画像として映ります。  
  
 コンピューター上のアニメーションも同様です。 たとえば、四角形の描画をビューからフェードアウトするプログラムは次のように動作する可能性があります。  
  
-   プログラムがタイマーを作成します。  
  
-   設定された間隔でプログラムがタイマーをチェックして経過時間を確認します。  
  
-   プログラムは、タイマーをチェックするたびに、経過時間に基づいて四角形の現在の不透明度値を計算します。  
  
-   プログラムは、新しい値で四角形を更新し、再描画します。  
  
 前のバージョン[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]、[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]開発者が作成およびタイミング システムを管理または特別なカスタム ライブラリを使用する必要があります。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]マネージ コードによって公開される効率的なタイミング システムを含むと[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]に深く統合されていると、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]フレームワークです。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アニメーションを使うと、コントロールやその他のグラフィカル オブジェクトを簡単にアニメーション化できます。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] は、タイミング システムの管理と画面の効率的な再描画をすべてバックグラウンドで処理します。 効果を実現するしくみではなく、作り出す効果に重点を置くことのできるタイミング クラスが提供されます。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] では、クラスが継承できるアニメーションの基底クラスを公開しているため、独自のアニメーションを簡単に作成して、カスタマイズされたアニメーションを生成することもできます。 これらのカスタム アニメーションは、標準のアニメーション クラスのパフォーマンス上のメリットの多くを得ます。  
  
<a name="thewpftimingsystem"></a>   
## <a name="wpf-property-animation-system"></a>WPF プロパティ アニメーション システム  
 タイミング システムに関するいくつかの重要な概念を理解している場合[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アニメーションが簡単に使用できます。 最も重要なは、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]、個々 のプロパティにアニメーションを適用することでオブジェクトをアニメーション化します。 たとえば、framework 要素が拡張するために、アニメーション化する、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティです。 アニメーション化するのにはビューからフェード オブジェクト、その<xref:System.Windows.UIElement.Opacity%2A>プロパティです。  
  
 プロパティにアニメーション機能を持たせるには、次の 3 つの要件を満たす必要があります。  
  
-   依存関係プロパティである必要があります。  
  
-   継承するクラスに属している必要がある必要があります<xref:System.Windows.DependencyObject>を実装し、<xref:System.Windows.Media.Animation.IAnimatable>インターフェイスです。  
  
-   互換性のあるアニメーションの種類が使用可能である必要があります。 (場合[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供しない、独自に作成することができます。 参照してください、[カスタム アニメーションの概要](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md))。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]持つ多くのオブジェクトを含む<xref:System.Windows.Media.Animation.IAnimatable>プロパティです。 などのコントロール<xref:System.Windows.Controls.Button>と<xref:System.Windows.Controls.TabControl>、さらに<xref:System.Windows.Controls.Panel>と<xref:System.Windows.Shapes.Shape>オブジェクトから継承<xref:System.Windows.DependencyObject>です。 これらのプロパティの大部分は依存関係プロパティです。  
  
 アニメーションは、スタイルやコントロール テンプレートなど、ほぼ任意の場所で使用できます。 アニメーションはビジュアルである必要はありません。このセクションで説明している条件を満たしていれば、ユーザー インターフェイスの一部ではないオブジェクトをアニメーション化できます。  
  
<a name="storyboardwalkthrough"></a>   
## <a name="example-make-an-element-fade-in-and-out-of-view"></a>例: ビューで要素のフェードインとフェードアウトを行う  
 この例を使用する方法を示しています、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]依存関係プロパティの値をアニメーション化するアニメーション。 使用して、 <xref:System.Windows.Media.Animation.DoubleAnimation>、生成されるアニメーションの型である<xref:System.Double>値をアニメーション化する、<xref:System.Windows.UIElement.Opacity%2A>のプロパティ、<xref:System.Windows.Shapes.Rectangle>です。 その結果、<xref:System.Windows.Shapes.Rectangle>フェードインおよびフェードアウトします。  
  
 この例の最初の部分を作成、<xref:System.Windows.Shapes.Rectangle>要素。 以下の手順は、アニメーションを作成し、四角形に適用する方法を示して<xref:System.Windows.UIElement.Opacity%2A>プロパティです。
  
 作成する方法を次に示します、<xref:System.Windows.Shapes.Rectangle>内の要素、 <xref:System.Windows.Controls.StackPanel> XAML でします。  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]  
  
 作成する方法を次に示します、<xref:System.Windows.Shapes.Rectangle>内の要素、<xref:System.Windows.Controls.StackPanel>のコードにします。  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]  
  
<a name="opacity_animation_step1"></a>   
### <a name="part-1-create-a-doubleanimation"></a>パート 1: DoubleAnimation を作成する  
 アニメーション化するにはフェードインおよびフェードアウト要素を作成する方法、<xref:System.Windows.UIElement.Opacity%2A>プロパティです。 <xref:System.Windows.UIElement.Opacity%2A>プロパティの型は<xref:System.Double>、double 型の値を生成するアニメーションを作成する必要があります。 A<xref:System.Windows.Media.Animation.DoubleAnimation>は、このような 1 つのアニメーション。 A <xref:System.Windows.Media.Animation.DoubleAnimation> 2 つの倍精度値間の遷移を作成します。 設定した開始値を指定するには、その<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>プロパティです。 設定した終了値を指定するには、その<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>プロパティです。  
  
1.  不透明度の値`1.0`完全に不透明なオブジェクトとの不透明度の値は、`0.0`完全に非表示になります。 アニメーション切り替え`1.0`に`0.0`を設定するその<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>プロパティを`1.0`とその<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>プロパティを`0.0`です。 作成する方法を次に示します、 <xref:System.Windows.Media.Animation.DoubleAnimation> XAML でします。  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]  
  
     作成する方法を次に示します、<xref:System.Windows.Media.Animation.DoubleAnimation>のコードにします。  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]  
  
2.  次に、指定する必要があります、<xref:System.Windows.Media.Animation.Timeline.Duration%2A>です。 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>アニメーションの開始値から、送信先の値に移行する所要時間を指定します。 設定する方法を次に示します、 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> XAML で 5 秒にします。  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]  
  
     設定する方法を次に示します、<xref:System.Windows.Media.Animation.Timeline.Duration%2A>コード内で 5 秒にします。  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]  
  
3.  上記のコードではから移行されるアニメーションを示しました`1.0`に`0.0`、それが原因で、ターゲット要素から完全に不透明な完全に非表示にフェードアウトします。 一度フェードインが消えた後に要素をクリックすると、<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>するアニメーションのプロパティ`true`です。 アニメーションを無限に繰り返しますするためには、次のように設定します。 その<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>プロパティを<xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>です。設定する方法を次に示します、<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>と<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>XAML でのプロパティです。  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]  
  
     設定する方法を次に示します、<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>と<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>コードでのプロパティです。  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]  
  
<a name="opacity_animation_step2"></a>   
### <a name="part-2-create-a-storyboard"></a>パート 2: ストーリーボードを作成する  
 作成するオブジェクトをアニメーションを適用する、<xref:System.Windows.Media.Animation.Storyboard>を使用して、<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>と<xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A>添付プロパティ オブジェクトを指定してアニメーション化するプロパティです。  
  
1.  作成、<xref:System.Windows.Media.Animation.Storyboard>し、その子として、アニメーションを追加します。 作成する方法を次に示します、 <xref:System.Windows.Media.Animation.Storyboard> XAML でします。  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]    
  
     作成する、<xref:System.Windows.Media.Animation.Storyboard>コードでは、宣言、<xref:System.Windows.Media.Animation.Storyboard>クラス レベルの変数です。  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]  
  
     初期化して、<xref:System.Windows.Media.Animation.Storyboard>し、その子として、アニメーションを追加します。  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]  
  
2.  <xref:System.Windows.Media.Animation.Storyboard>がここでは、アニメーションを適用します。 使用して、<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType>添付プロパティをアニメーション化するオブジェクトを指定します。 次のターゲットの名前を設定する方法を示しています、<xref:System.Windows.Media.Animation.DoubleAnimation>に`MyRectangle`XAML でします。  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]  
  
     ターゲットの名前を設定する方法を次に示します、<xref:System.Windows.Media.Animation.DoubleAnimation>に`MyRectangle`のコードにします。  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]  
  
3.  使用して、<xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A>添付プロパティをアニメーション化するプロパティを指定します。 アニメーションを構成する方法を次に示しますターゲットに、<xref:System.Windows.UIElement.Opacity%2A>のプロパティ、 <xref:System.Windows.Shapes.Rectangle> XAML でします。
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]  
  
     アニメーションを構成する方法を次に示しますターゲットに、<xref:System.Windows.UIElement.Opacity%2A>のプロパティ、<xref:System.Windows.Shapes.Rectangle>のコードにします。  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]  
  
 詳細については<xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A>構文と例については、次を参照してください。、[ストーリー ボードの概要](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)です。  
  
<a name="opacity_animation_step3"></a>   
### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>パート 3 (XAML): ストーリーボードをトリガーに関連付ける  
 最も簡単な方法を適用し、開始、<xref:System.Windows.Media.Animation.Storyboard>で[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]イベント トリガーを使用することです。 このセクションの内容に関連付ける方法を示しています、 <xref:System.Windows.Media.Animation.Storyboard> XAML でのトリガーを持つ。  
  
1.  作成、<xref:System.Windows.Media.Animation.BeginStoryboard>オブジェクトし、ストーリー ボードを関連付けます。 A<xref:System.Windows.Media.Animation.BeginStoryboard>の種類は、<xref:System.Windows.TriggerAction>を適用し、開始、<xref:System.Windows.Media.Animation.Storyboard>です。  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]  
  
2.  作成、<xref:System.Windows.EventTrigger>を追加し、<xref:System.Windows.Media.Animation.BeginStoryboard>にその<xref:System.Windows.EventTrigger.Actions%2A>コレクション。 設定、<xref:System.Windows.EventTrigger.RoutedEvent%2A>のプロパティ、<xref:System.Windows.EventTrigger>を開始するルーティング イベントを<xref:System.Windows.Media.Animation.Storyboard>です。 (ルーティング イベントの詳細については、次を参照してください、[ルーティング イベントの概要](../../../../docs/framework/wpf/advanced/routed-events-overview.md)。)。  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]  
  
3.  追加、<xref:System.Windows.EventTrigger>を<xref:System.Windows.FrameworkElement.Triggers%2A>四角形のコレクション。  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]  
  
<a name="opacity_animation_step3code"></a>   
### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>パート 3 (コード): ストーリーボードをイベント ハンドラーに関連付ける  
 最も簡単な方法を適用し、開始、<xref:System.Windows.Media.Animation.Storyboard>コードでは、イベント ハンドラーを使用します。 このセクションの内容に関連付ける方法を示しています、<xref:System.Windows.Media.Animation.Storyboard>をコードでイベント ハンドラー。  
  
1.  登録、<xref:System.Windows.FrameworkElement.Loaded>四角形のイベントです。  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]  
  
2.  イベント ハンドラーを宣言します。 イベント ハンドラーで使用して、<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>ストーリー ボードを適用する方法です。  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]  
  
### <a name="complete-example"></a>コード例全体  
 Xaml ビューとの間のフェードインする四角形を作成する方法を次に示します。  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]  
  
 ビューでフェードインおよびフェードアウトする四角形をコードで作成する方法を次に示します。  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]  
  
<a name="animationtypes"></a>   
## <a name="animation-types"></a>アニメーションの種類  
 アニメーションはプロパティの値を生成するため、異なるプロパティの型ごとに異なるアニメーションの種類が存在します。 受け取るプロパティをアニメーション化する、 <xref:System.Double>、ように、 <xref:System.Windows.FrameworkElement.Width%2A> 、要素のプロパティを生成するアニメーションを使用して<xref:System.Double>値。 受け取るプロパティをアニメーション化する、 <xref:System.Windows.Point>、生成されるアニメーションを使用して<xref:System.Windows.Point>値、およびなどです。 プロパティの種類の数のためには、いくつかのアニメーション クラス、<xref:System.Windows.Media.Animation>名前空間。 幸いにも、それらは厳密な名前付け規則に従っているため、簡単に区別できます。  
  
-   \<*型*> アニメーション  
  
     これらは "From/To/By" または "基本" アニメーションと呼ばれ、開始値と宛先値の間をアニメーション化するか、開始値にオフセット値を加算することでアニメーション化します。  
  
    -   開始値を指定するには、アニメーションの From プロパティを設定します。  
  
    -   終了値を指定するには、アニメーションの To プロパティを設定します。  
  
    -   オフセット値を指定するには、アニメーションの By プロパティを設定します。  
  
     これらのアニメーションは最も簡単に使用できるため、この概要の例ではこれらを使っています。 From/を/、アニメーションは From/To/By アニメーションの概要で詳細に説明します。  
  
-   \<*型*> AnimationUsingKeyFrames  
  
     キー フレーム アニメーションは、任意の数のターゲット値を指定でき、補間方法も制御できるため、From/To/By アニメーションよりも強力です。 一部の型は、キー フレーム アニメーションでのみアニメーション化できます。 キー フレーム アニメーションがで詳しく説明されている、[キー フレーム アニメーションの概要](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)です。  
  
-   \<*型*> AnimationUsingPath  
  
     パス アニメーションでは、アニメーション値を生成するためにジオメトリック パスを使用できます。  
  
-   \<*型*> AnimationBase  
  
     これを実装するときにアニメーション化する抽象クラス、 \<*型*> 値。 このクラスの基底クラスとして機能\<*型*> アニメーションと\<*型*> AnimationUsingKeyFrames クラスです。 これらのクラスは、ユーザー独自のカスタム アニメーションを作成する場合にのみ直接扱う必要があります。 それ以外の場合を使用して、 \<*型*> アニメーションまたはキーフレーム\<*型*> アニメーション。  
  
 ほとんどの場合、使用する、 \<*型*> アニメーションなどのクラス、<xref:System.Windows.Media.Animation.DoubleAnimation>と<xref:System.Windows.Media.Animation.ColorAnimation>です。  
  
 次の表は、いくつかの一般的なアニメーションの種類と、そこで使われるいくつかのプロパティを示しています。  
  
|プロパティの型|対応する基本 (From/To/By) アニメーション|対応するキー フレーム アニメーション|対応するパス アニメーション|使用例|  
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|なし|アニメーション化する、<xref:System.Windows.Media.SolidColorBrush.Color%2A>の<xref:System.Windows.Media.SolidColorBrush>または<xref:System.Windows.Media.GradientStop>です。|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|アニメーション化する、<xref:System.Windows.FrameworkElement.Width%2A>の<xref:System.Windows.Controls.DockPanel>または<xref:System.Windows.FrameworkElement.Height%2A>の<xref:System.Windows.Controls.Button>です。|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|アニメーション化する、<xref:System.Windows.Media.EllipseGeometry.Center%2A>の位置、<xref:System.Windows.Media.EllipseGeometry>です。|  
|<xref:System.String>|なし|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|なし|アニメーション化する、<xref:System.Windows.Controls.TextBlock.Text%2A>の<xref:System.Windows.Controls.TextBlock>または<xref:System.Windows.Controls.ContentControl.Content%2A>の<xref:System.Windows.Controls.Button>です。|  
  
<a name="animationsaretimelines"></a>   
### <a name="animations-are-timelines"></a>アニメーションはタイムラインである  
 アニメーションのすべての型から継承、<xref:System.Windows.Media.Animation.Timeline>クラスです。 このため、すべてのアニメーションがタイムラインの特化された型。 A<xref:System.Windows.Media.Animation.Timeline>時間のセグメントを定義します。 指定することができます、*タイミング動作*タイムライン: その<xref:System.Windows.Media.Animation.Timeline.Duration%2A>、何回かについては、繰り返しと偶数の速度は時間の進行します。  
  
 アニメーションがあるため、<xref:System.Windows.Media.Animation.Timeline>時間のセグメントを表すこともできます。 ただしその時間の指定したセグメントで進行状況に合わせて出力値がアニメーションによっても計算 (または<xref:System.Windows.Media.Animation.Timeline.Duration%2A>)。 アニメーションは、進行時、つまり "再生" 時に、関連付けられているプロパティを更新します。  
  
 頻繁に使用するタイミング プロパティは 3 つ<xref:System.Windows.Media.Animation.Timeline.Duration%2A>、 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>、および<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>です。  
  
#### <a name="the-duration-property"></a>Duration プロパティ  
 既に述べたように、タイムラインは時間のセグメントを表します。 そのセグメントの長によって決定されます、<xref:System.Windows.Media.Animation.Timeline.Duration%2A>通常を使用して指定されると、タイムラインの<xref:System.Windows.Duration.TimeSpan%2A>値。 タイムラインがその期間の最後に達すると、イテレーションが完了します。  
  
 アニメーションを使用してその<xref:System.Windows.Media.Animation.Timeline.Duration%2A>プロパティを現在の値を決定します。 指定しない場合、<xref:System.Windows.Media.Animation.Timeline.Duration%2A>値、既定では 1 秒間を使用して、アニメーションを実行します。  
  
 次の構文の簡略化されたバージョンを示しています、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]属性の構文、<xref:System.Windows.Media.Animation.Timeline.Duration%2A>プロパティです。  
  
*時* `:` *分* `:` *秒*
  
 次の表にいくつか示します<xref:System.Windows.Duration>設定とその結果として得られる値です。  
  
|設定|結果の値|  
|-------------|---------------------|  
|0:0:5.5|5.5 秒。|  
|0:30:5.5|30 分 5.5 秒。|  
|1:30:5.5|1 時間 30 分 5.5 秒。|  
  
 指定する方法の 1 つ、<xref:System.Windows.Duration>コードでは使用する、<xref:System.TimeSpan.FromSeconds%2A>メソッドを作成、<xref:System.TimeSpan>を宣言し、新しい<xref:System.Windows.Duration>が使用している構造体<xref:System.TimeSpan>です。  
  
 詳細については<xref:System.Windows.Duration>値と完全な[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]構文を参照してください、<xref:System.Windows.Duration>構造体。  
  
#### <a name="autoreverse"></a>AutoReverse  
 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>プロパティは、旧バージョンと再生の末尾に達した後は、タイムラインにかどうかを指定します、<xref:System.Windows.Media.Animation.Timeline.Duration%2A>です。 このアニメーションのプロパティを設定した場合`true`の末尾に達した後、アニメーションを反転させますその<xref:System.Windows.Media.Animation.Timeline.Duration%2A>、開始値に戻す終了値から再生します。 このプロパティは、既定では、`false`です。  
  
#### <a name="repeatbehavior"></a>RepeatBehavior  
 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>プロパティは、タイムラインの再生回数を指定します。 既定では、タイムラインがのイテレーション数をある`1.0`つまり、1 つを再生する時間し、はまったく繰り返されません。  
  
 これらのプロパティおよびその他の詳細については、次を参照してください。、[タイミング動作の概要](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)です。  
  
<a name="applyanimationstoproperty"></a>   
## <a name="applying-an-animation-to-a-property"></a>プロパティにアニメーションを適用する  
 これまでのセクションでは、さまざまな種類のアニメーションとそれらのタイミング プロパティについて説明しました。 このセクションでは、アニメーション化するプロパティにアニメーションを適用する方法を示します。 <xref:System.Windows.Media.Animation.Storyboard>オブジェクトは、プロパティにアニメーションを適用する 1 つの方法を提供します。 A<xref:System.Windows.Media.Animation.Storyboard>は、*コンテナ タイムライン*が含まれているアニメーションの対象とする情報を提供します。  
  
### <a name="targeting-objects-and-properties"></a>ターゲットとするオブジェクトとプロパティ  
 <xref:System.Windows.Media.Animation.Storyboard>クラスを提供、<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>と<xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A>アタッチされるプロパティです。 アニメーションでこれらのプロパティを設定して、アニメーション化する内容をアニメーションに指示します。 ただし、アニメーションがオブジェクトをターゲット指定するには、通常その前にオブジェクの名前を指定する必要があります。  
  
 名前が割り当てられて、<xref:System.Windows.FrameworkElement>に名の割り当てとは異なります、<xref:System.Windows.Freezable>オブジェクト。 ほとんどのコントロールとパネルはフレームワーク要素ですが、ブラシ、変換、ジオメトリなどのほとんどの純粋なグラフィカル オブジェクトは Freezable オブジェクトです。 ないことを確認するかどうか、型の場合、<xref:System.Windows.FrameworkElement>または<xref:System.Windows.Freezable>を参照してください、**継承階層**のリファレンス ドキュメントのセクションでします。  
  
-   させる、<xref:System.Windows.FrameworkElement>をアニメーションのターゲット名を指定することを設定してその<xref:System.Windows.FrameworkElement.Name%2A>プロパティです。 コードでは、行う必要がありますも、<xref:System.Windows.FrameworkElement.RegisterName%2A>はページが所属すると、要素名を登録します。  
  
-   させる、<xref:System.Windows.Freezable>オブジェクトをアニメーションのターゲットで[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を使用する、 [X:name ディレクティブ](../../../../docs/framework/xaml-services/x-name-directive.md)名前を指定します。 コードでは、使用する、<xref:System.Windows.FrameworkElement.RegisterName%2A>が所属する ページで、オブジェクトを登録します。  
  
 次のセクションの名前付けの内の要素の例を示します[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]とコード。 名前付けとターゲット設定の詳細については、次を参照してください。、[ストーリー ボードの概要](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)です。  
  
### <a name="applying-and-starting-storyboards"></a>ストーリーボードの適用と開始  
 ストーリー ボードを起動する[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]、関連付けること、<xref:System.Windows.EventTrigger>です。 <xref:System.Windows.EventTrigger>は、指定したイベントが発生したときに実行するアクションを記述するオブジェクト。 これらのアクションのいずれかを指定できます、<xref:System.Windows.Media.Animation.BeginStoryboard>アクションで、ストーリー ボードの起動に使用します。 イベント トリガーは、アプリケーションが特定のイベントに応答する方法を指定できるようにするため、概念はイベント ハンドラーに似ています。 イベント ハンドラーとは異なりイベント トリガーはで完全に記述できる[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; 他のコードは必要ありません。  
  
 開始する、<xref:System.Windows.Media.Animation.Storyboard>コードでは、使用することができます、<xref:System.Windows.EventTrigger>か使用して、<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>のメソッド、<xref:System.Windows.Media.Animation.Storyboard>クラスです。  
  
<a name="controllingstoryboards"></a>   
## <a name="interactively-control-a-storyboard"></a>ストーリーボードを対話的に制御する  
 前の例でを起動する方法、<xref:System.Windows.Media.Animation.Storyboard>イベントが発生します。 対話形式で制御することができます、<xref:System.Windows.Media.Animation.Storyboard>開始後に: 一時停止、再開、停止、塗りつぶし期間に進める、シーク、および削除できます、<xref:System.Windows.Media.Animation.Storyboard>です。 対話的に制御する方法を示す例および詳細について、<xref:System.Windows.Media.Animation.Storyboard>を参照してください、[ストーリー ボードの概要](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)です。  
  
<a name="fillbehaviorsection"></a>   
## <a name="what-happens-after-an-animation-ends"></a>アニメーションの終了後の動作  
 <xref:System.Windows.Media.Animation.FillBehavior>プロパティは、これが終了すると、タイムラインの動作を指定します。 既定では、タイムラインが開始<xref:System.Windows.Media.Animation.ClockState.Filling>終了します。 あるアニメーション<xref:System.Windows.Media.Animation.ClockState.Filling>最終的な出力値を保持します。  
  
 <xref:System.Windows.Media.Animation.DoubleAnimation>前の例で終わらないためその<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>プロパティに設定されている<xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>です。 次の例では、類似のアニメーションを使って四角形をアニメーション化します。 前の例とは異なり、<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>と<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>このアニメーションのプロパティは、既定値のままにします。 したがって、アニメーションは 5 秒間で 1 から 0 まで進行し、停止します。  
  
 [!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]  
  
 [!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
 [!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]  
  
 その<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>が、これは既定値から変更されていない<xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>アニメーションを保持、最終的な値は 0 で、これが終了するとします。 したがって、 <xref:System.Windows.UIElement.Opacity%2A> 0 アニメーションの終了後に、四角形は残りの終了します。 設定した場合、 <xref:System.Windows.UIElement.Opacity%2A> 、別の値に四角形のコードが何の効果アニメーションがまだに影響を与えるため、<xref:System.Windows.UIElement.Opacity%2A>プロパティです。  
  
 コードでアニメーションのプロパティの制御を回復する方法の 1 つを使用して、<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>メソッド null を指定して、<xref:System.Windows.Media.Animation.AnimationTimeline>パラメーター。 例および詳細については、次を参照してください。 [、プロパティの後にアニメーション化するように設定にストーリー ボード](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md)です。  
  
 なお、プロパティ値を設定するには、<xref:System.Windows.Media.Animation.ClockState.Active>または<xref:System.Windows.Media.Animation.ClockState.Filling>アニメーションは効果がない、プロパティの値は変更します。 詳細については、次を参照してください。、[アニメーションおよびタイミング システムの概要](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)です。  
  
<a name="databindingAndAnimatingAnimationsSection"></a>   
## <a name="data-binding-and-animating-animations"></a>アニメーションのデータ バインディングとアニメーション化  
 ほとんどのアニメーションのプロパティは、データ バインドまたはアニメーション化します。たとえば、アニメーション化できます、<xref:System.Windows.Media.Animation.Timeline.Duration%2A>のプロパティ、<xref:System.Windows.Media.Animation.DoubleAnimation>です。 ただし、タイミング システムの動作が原因で、データ バインドまたはアニメーション化されたアニメーションは他のデータ バインドまたはアニメーション化されたオブジェクトと同様には動作しません。 その動作を理解するには、アニメーションをプロパティに適用する意味を理解することが役立ちます。  
  
 アニメーション化する方法を示しました前のセクションの例を参照してください、<xref:System.Windows.UIElement.Opacity%2A>四角形のです。 そのイベント トリガーが適用される前の例で、四角形が読み込まれるときに、<xref:System.Windows.Media.Animation.Storyboard>です。 タイミング システムのコピーを作成する、<xref:System.Windows.Media.Animation.Storyboard>およびそのアニメーション。 これらのコピーが固定されている (読み取り専用に変更) と<xref:System.Windows.Media.Animation.Clock>そこからオブジェクトが作成されます。 これらのクロックは、ターゲット プロパティをアニメーション化する実際の作業を実行します。  
  
 タイミング システム用の時計の作成、<xref:System.Windows.Media.Animation.DoubleAnimation>オブジェクトとで指定されているプロパティに適用し、<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>と<xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A>の<xref:System.Windows.Media.Animation.DoubleAnimation>です。 タイミング システムにクロックを適用するこの例では、 <xref:System.Windows.UIElement.Opacity%2A> 「続きとしてです」というオブジェクトのプロパティ。  
  
 クロックはの作成もされますが、<xref:System.Windows.Media.Animation.Storyboard>時計は、任意のプロパティには適用されません。 その目的は、その子のクロックに作成される、時計を制御する、<xref:System.Windows.Media.Animation.DoubleAnimation>です。  
  
 アニメーションがデータ バインディングまたはアニメーションの変更を反映するためには、そのクロックを再生成する必要があります。 クロックは、自動的には再生成されません。 アニメーションの変更を反映するために、そのストーリー ボードを再適用を使用して、<xref:System.Windows.Media.Animation.BeginStoryboard>または<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>メソッドです。 これらのメソッドのいずれかを使うと、アニメーションが再起動されます。 コードでは、使用することができます、<xref:System.Windows.Media.Animation.Storyboard.Seek%2A>ストーリー ボードをシフトするメソッドが前の位置にバックアップします。  
  
 データの例には、アニメーションがバインドされているを参照してください[キー スプライン アニメーション サンプル](http://go.microsoft.com/fwlink/?LinkID=160011)です。 詳細については、アニメーションおよびタイミング システムのしくみについては、次を参照してください。[アニメーションおよびタイミング システムの概要](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)です。  
  
<a name="otherWaysToAnimateSection"></a>   
## <a name="other-ways-to-animate"></a>その他のアニメーション化方法  
 この概要の例では、ストーリーボードを使ってアニメーション化する方法を示します。 コードを使う場合は、その他のいくつかの方法でアニメーション化できます。 詳細については、次を参照してください。、[プロパティ アニメーションの技術概要](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)です。  
  
<a name="animation_samples"></a>   
## <a name="animation-samples"></a>アニメーションのサンプル  
 以下のサンプルは、アプリケーションへのアニメーションの追加を開始するのに役立つ場合があります。  
  
-   [アニメーションのターゲット値 (From、To、および By) のサンプル](http://go.microsoft.com/fwlink/?LinkID=159988)  
  
     さまざまな From/To/By 設定を示します。  
  
-   [アニメーションのタイミング動作のサンプル](http://go.microsoft.com/fwlink/?LinkID=159970)  
  
     アニメーションのタイミング動作を制御するさまざまな方法を示します。 このサンプルは、アニメーションの宛先値をデータ バインドする方法も示しています。  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>関連トピック  
  
|タイトル|説明|  
|-----------|-----------------|  
|[アニメーションとタイミング システムの概要](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)|タイミング システムを使用する方法について説明します、<xref:System.Windows.Media.Animation.Timeline>と<xref:System.Windows.Media.Animation.Clock>クラスで、アニメーションを作成することです。|  
|[アニメーションのヒントとテクニック](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)|パフォーマンスなど、アニメーションでの問題を解決するための役に立つヒントの一覧を示します。|  
|[カスタム アニメーションの概要](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)|アニメーション システムをキー フレーム、アニメーション クラス、またはフレームごとのコールバックで拡張する方法について説明します。|  
|From/To/By アニメーションの概要|2 つの値の間を遷移するアニメーションを作成する方法について説明します。|  
|[キー フレーム アニメーションの概要](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)|補間メソッドを制御する機能など、複数のターゲット値を持つアニメーションを作成する方法について説明します。|  
|[イージング関数](../../../../docs/framework/wpf/graphics-multimedia/easing-functions.md)|数式をアニメーションに適用してバウンスなどの現実的な動作を実現する方法について説明します。|  
|[パス アニメーションの概要](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)|複雑なパスに沿ってオブジェクトを移動または回転する方法について説明します。|  
|[プロパティ アニメーションの手法の概要](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)|ストーリーボード、ローカル アニメーション、クロック、フレームごとのアニメーションを使ったプロパティのアニメーションについて説明します。|  
|[ストーリーボードの概要](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)|複数のタイムラインを持つストーリーボードを使って複雑なアニメーションを作成する方法について説明します。|  
|[タイミング動作の概要](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)|について説明します、<xref:System.Windows.Media.Animation.Timeline>型およびアニメーションで使用されるプロパティです。|  
|[タイミング イベントの概要](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)|使用できるイベントについて説明します、<xref:System.Windows.Media.Animation.Timeline>と<xref:System.Windows.Media.Animation.Clock>など、タイムラインのポイントでコードを実行するためのオブジェクトを開始、一時停止、再開、スキップ、または停止します。|  
|[方法トピック](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)|アプリケーションでアニメーションとタイムラインを使うためのコード例を示します。|  
|[クロックに関する「方法」トピック](../../../../docs/framework/wpf/graphics-multimedia/clocks-how-to-topics.md)|使用するためのコード例を示します、<xref:System.Windows.Media.Animation.Clock>アプリケーションのオブジェクト。|  
|[キー フレームに関する「方法」トピック](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)|アプリケーションでキー フレーム アニメーションを使うためのコード例を示します。|  
|[パス アニメーションに関する「方法」トピック](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)|アプリケーションでパス アニメーションを使うためのコード例を示します。|  
  
<a name="reference"></a>   
## <a name="reference"></a>参照  
 <xref:System.Windows.Media.Animation.Timeline>  
  
 <xref:System.Windows.Media.Animation.Storyboard>  
  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
  
 <xref:System.Windows.Media.Animation.Clock>

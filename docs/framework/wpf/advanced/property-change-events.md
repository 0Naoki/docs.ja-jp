---
title: "プロパティ変更イベント"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency properties [WPF], change events
- property value changes [WPF]
- change events [WPF], property
- events [WPF], change in property values
- creating property triggers [WPF]
- property change events [WPF], types of
- property change events [WPF]
- property triggers [WPF]
- identifying changed property events [WPF]
- property triggers [WPF], definition of
ms.assetid: 0a7989df-9674-4cc1-bc50-5d8ef5d9c055
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46a11b072731daf420e35bc9c9cfd7d4fced1fe5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="property-change-events"></a>プロパティ変更イベント
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] では、プロパティ値の変更に応答して発生するさまざまなイベントが定義されています。 通常、プロパティは依存関係プロパティです。 イベント自体は、ルーティング イベントのこともあれば、標準の [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] イベントのこともあります。 要素ツリーを通じて適切にルーティングされるプロパティ変更もあれば、プロパティが変更されたオブジェクトにのみ関係するプロパティ変更もあるため、イベントの定義はシナリオによって異なります。  
  
## <a name="identifying-a-property-change-event"></a>プロパティ変更イベントの識別  
 シグネチャ パターンまたは名前付けパターンに基づいてプロパティ変更を報告するすべてのイベントが、プロパティ変更イベントとして明示的に識別されるわけではありません。 通常、[!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] ドキュメント内のイベントの説明では、イベントがプロパティ値の変更に直接結び付くものであるかどうかが示されており、プロパティとイベントのクロス リファレンスが提供されます。  
  
### <a name="routedpropertychanged-events"></a>RoutedPropertyChanged イベント  
 特定のイベントでは、プロパティ変更イベントで明示的に使用されるイベント データ型とデリゲートを使用します。 イベントのデータ型は<xref:System.Windows.RoutedPropertyChangedEventArgs%601>、デリゲートと<xref:System.Windows.RoutedPropertyChangedEventHandler%601>です。 イベント データもデリゲートも、ジェネリック型パラメーターを使用します。これは、ハンドラーを定義するときに、変更するプロパティの実際の型を指定するために使用されるものです。 イベント データには、2 つのプロパティが含まれている<xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>と<xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>もし、渡される型引数としてイベント データ。  
  
 名前の "Routed" 部分は、プロパティ変更イベントがルーティング イベントして登録されていることを示しています。 プロパティ変更イベントのルーティングには、子要素 (コントロールの複合部分) のプロパティが値を変更した場合に、コントロールのトップ レベルがプロパティ変更イベントを受信できるというメリットがあります。 インスタンスが組み込まれているコントロールを作成する場合があります、<xref:System.Windows.Controls.Primitives.RangeBase>などを制御する<xref:System.Windows.Controls.Slider>です。 場合の値、<xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>スライダー一部のプロパティを変更することができますの一部ではなく、親コントロールは、その変更を処理します。  
  
 古い値と新しい値があるため、このイベント ハンドラーがプロパティ値の検証コントロールとして使用される可能性があります。 しかし、プロパティ変更イベントの多くは、このような目的で設計されているわけではありません。 通常、値の提供は、他のロジック領域のコードでその値を処理するために行われますが、イベント ハンドラー内から値を実際に変更することはお勧めできません。また、ハンドラーの実装方法によっては、意図しない再帰が生じることもあります。  
  
 プロパティがカスタムの依存関係プロパティの場合、またはを使用する派生クラスでインスタンス化コードが定義されている場合は、優れたメカニズムに組み込まれているプロパティの変更を追跡するため、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]プロパティ システム:プロパティ システム コールバック<xref:System.Windows.CoerceValueCallback>と<xref:System.Windows.PropertyChangedCallback>です。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] プロパティ システムを使用して検証および強制型変換を行う方法の詳細については、「[依存関係プロパティのコールバックと検証](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)」および「[カスタム依存関係プロパティ](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)」を参照してください。  
  
### <a name="dependencypropertychanged-events"></a>DependencyPropertyChanged イベント  
 プロパティ変更イベントのシナリオの一部である型の別のペアが<xref:System.Windows.DependencyPropertyChangedEventArgs>と<xref:System.Windows.DependencyPropertyChangedEventHandler>です。 これらのプロパティ変更のイベントはルーティングされません。これらは、標準の [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] イベントです。 <xref:System.Windows.DependencyPropertyChangedEventArgs>レポートの種類から派生しないため、異常なイベント データは、<xref:System.EventArgs>です。<xref:System.Windows.DependencyPropertyChangedEventArgs>は構造体、クラスではありません。  
  
 使用するイベント<xref:System.Windows.DependencyPropertyChangedEventArgs>と<xref:System.Windows.DependencyPropertyChangedEventHandler>よりも若干より一般的な`RoutedPropertyChanged`イベント。 これらの型を使用するイベントの例は<xref:System.Windows.UIElement.IsMouseCapturedChanged>します。  
  
 同様に<xref:System.Windows.RoutedPropertyChangedEventArgs%601>、<xref:System.Windows.DependencyPropertyChangedEventArgs>もプロパティの古いマスター_キーと新しい値を報告します。 そのため、値を適用して行う操作に関して同じ注意が当てはまります。イベントに応答して送信元で値を再度変更することは、一般的にはお勧めできません。  
  
## <a name="property-triggers"></a>プロパティ トリガー  
 プロパティ変更イベントに密接に関係する概念がプロパティ トリガーです。 プロパティ トリガーはスタイルまたはテンプレート内に作成され、プロパティ トリガーが割り当てられるプロパティの値に基づく条件付きの動作を作成できます。  
  
 プロパティ トリガーのプロパティは、依存関係プロパティでなければなりません。 これは、読み取り専用の依存関係プロパティにすることができます (多くの場合そのようになっています)。 コントロールによって公開される依存関係プロパティが、プロパティ トリガーになるように部分的に設計されている場合、プロパティ名が "Is" で始まっていることで見分けられます。 この名前付けがされたプロパティは、多くの場合、読み取り専用のブール型の依存関係プロパティです。このプロパティの主要なシナリオは、リアルタイム UI に影響を及ぼす可能性があるためにプロパティ トリガーの候補である、レポート コントロール ステートです。  
  
 これらのプロパティの一部は、専用のプロパティ変更イベントも持ちます。 プロパティのインスタンス、<xref:System.Windows.UIElement.IsMouseCaptured%2A>プロパティ変更イベントを持つ<xref:System.Windows.UIElement.IsMouseCapturedChanged>します。 入力システムが調整値で、プロパティ自体が読み取り専用、および入力システムを発生させます<xref:System.Windows.UIElement.IsMouseCapturedChanged>リアルタイム変更のたびにします。  
  
 プロパティ トリガーを使用してプロパティの変更に対処する場合は、本当のプロパティ変更イベントに比べ、いくつかの制限があります。  
  
 プロパティ トリガーは、完全一致ロジックを通じて動作します。 プロパティと、トリガーが処理する特定の値を示す値を指定します。次に例を示します: `<Setter Property="IsMouseCaptured" Value="true"> ... </Setter>`。 この制限のため、ほとんどのプロパティ トリガーの使用は、ブール型のプロパティか、専用の列挙値を使用するプロパティが対象です。この場合、有効な値の範囲は、各ケースに対応するトリガーを定義するために十分な程度管理することができます。 または、プロパティ トリガーは、項目のカウントがゼロに達した場合など、特別な値に対してのみ存在する可能性があります。プロパティ値がゼロから再び変更するケースに対処するトリガーはありません (すべてのケースに対応するトリガーではなく、コード イベント ハンドラー、または、値がゼロ以外のときにトリガー状態を再び元に戻す既定の動作が必要です)。  
  
 プロパティ トリガーの構文は、プログラミングの "if" ステートメントに似ています。 トリガー条件が true の場合、プロパティ トリガーの "本体" が "実行" されます。 プロパティ トリガーの "本体" はコードではなく、マークアップです。 そのマークアップが 1 つまたは複数の使用に限定<xref:System.Windows.Setter>位置スタイルまたはテンプレートが適用されているその他のオブジェクトのプロパティを設定する要素。  
  
 さまざまな使用可能な値を持つプロパティ トリガーの"if"条件をオフセットするが、既定値を使用してその同じプロパティ値を設定することをお勧め、<xref:System.Windows.Setter>です。 これにより、<xref:System.Windows.Trigger>包含 set アクセス操作子が優先トリガーの条件が true の場合、および<xref:System.Windows.Setter>を内ではありません、<xref:System.Windows.Trigger>トリガーの条件が false されるたびに、優先順位になります。  
  
 プロパティ トリガーは、通常、1 つ以上の外観プロパティが、同じ要素の別のプロパティの状態に基づいて変更されるシナリオに適しています。  
  
 プロパティ トリガーの詳細については、「[スタイルとテンプレート](../../../../docs/framework/wpf/controls/styling-and-templating.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [ルーティング イベントの概要](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [依存関係プロパティの概要](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)

---
title: UI オートメーションによる Document コントロール型のサポート
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Document
- Document control type
- UI Automation, Document control type
ms.assetid: a79d594b-1ca0-4543-8dac-afd2c645201d
ms.openlocfilehash: ebdf3ccc1c3a4966d89ddbe3616acd45c244a080
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71041720"
---
# <a name="ui-automation-support-for-the-document-control-type"></a>UI オートメーションによる Document コントロール型のサポート
> [!NOTE]
> このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。 の最新情報[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]については[、「Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 このトピックでは、Document コントロール型の [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] サポートに関する情報を提供します。 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]でのコントロール型とは、コントロールが <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> プロパティを使用するために満たす必要がある一連の条件のことです。 これらの条件には、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリー構造、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] のプロパティ値、およびコントロール パターンに関する特定のガイドラインが含まれます。  
  
 ドキュメント コントロールを使用すると、ユーザーは複数ページのテキストを表示して操作できます。 書式設定されていない単純なテキスト行しかサポートしない編集コントロールとは異なり、ドキュメント コントロールは、さまざまなスタイルおよび書式を使用したテキストをホストできます。  
  
 以降のセクションで、Document コントロール型に必要な [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリー構造、プロパティ、コントロール パターン、およびイベントを定義します。 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] の要件は、 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]、 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]、または [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]であるかどうかに関係なく、すべてのドキュメント コントロールに適用されます。  
  
## <a name="required-ui-automation-tree-structure"></a>必須の UI オートメーション ツリー構造  
 次の表に、ドキュメント コントロールに関連する [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーのコントロール ビューとコンテンツ ビューを示し、それぞれのビューに含めることができる内容について説明します。 ツリーの[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]詳細については、「 [UI オートメーションツリーの概要](ui-automation-tree-overview.md)」を参照してください。  
  
|コントロール ビュー|コンテンツ ビュー|  
|------------------|------------------|  
|ドキュメント<br /><br /> -変化|ドキュメント<br /><br /> -変化|  
  
## <a name="required-ui-automation-properties"></a>必須の UI オートメーション プロパティ  
 次の表に、ドキュメント コンロトールに特に関連する値または定義を持つ [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] プロパティを示します。 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]プロパティの詳細については、「[クライアントの UI オートメーションのプロパティ](ui-automation-properties-for-clients.md)」を参照してください。  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] プロパティ|[値]|メモ|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|「ノート」をご覧ください。|このプロパティの値は、アプリケーションのすべてのコントロールで一意である必要があります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|「ノート」をご覧ください。|コントロール全体を格納する最も外側の四角形。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|「ノート」をご覧ください。|ドキュメントにはクリック可能なポイントがあり、そのポイントをクリックすると、ドキュメント コンテナー内のいずれかの要素のドキュメントがフォーカスを受け取ります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|ドキュメント|この値は、すべての UI フレームワークで同じです。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|ドキュメント コントロールは、常に [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーのコンテンツ ビューに組み込まれます。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|ドキュメント コントロールは、常に [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーのコントロール ビューに組み込まれます。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|「ノート」をご覧ください。|コントロールがキーボード フォーカスを受け取ることができる場合は、このプロパティをサポートする必要があります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|「ノート」をご覧ください。|このプロパティの値は、ドキュメント コントロールのラベルでなければなりません。 通常、ドキュメントのタイトルが使用されます。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|「ドキュメント」|Document コントロール型に対応する、ローカライズされた文字列。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|「ノート」をご覧ください。|通常、ドキュメント コントロールの名前は、読み込み元のファイル名から取得されます。 この名前は多くの場合、そのコントロールを格納するウィンドウまたはフレームのタイトルに表示されます。|  
  
## <a name="required-ui-automation-control-patterns"></a>必須の UI オートメーション コントロール パターン  
 次の表に、ドキュメント コントロールでサポートする必要がある [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] コントロール パターンを示します。 コントロール パターンについて詳しくは、「 [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md)」をご覧ください。  
  
|コントロール パターン|サポート|メモ|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|依存|ドキュメント コントロールは、ビューポートのスパンを超えてスパンできます。 コントロールのコンテンツがスクロール可能な場合は、Scroll コントロール パターンをサポートする必要があります。|  
|<xref:System.Windows.Automation.Provider.ITextProvider>|必須|ドキュメント コントロールは、ビューポートのスパンを超えてスパンできます。 コントロールのコンテンツがスクロール可能な場合は、Scroll コントロール パターンをサポートする必要があります。|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|しない|通常、ドキュメント コントロールのコンテンツは複数のページにまたがるため、ドキュメント コントロールはこのコントロール パターンをサポートしません。 UI オートメーション クライアントは、 <xref:System.Windows.Automation.TextPattern> を使用してドキュメントに関するテキスト情報を取得する必要があります。|  
  
## <a name="required-ui-automation-events"></a>必須の UI オートメーション イベント  
 次の表に、すべてのドキュメント コントロールでサポートされなければならない [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] イベントを示します。 イベントについて詳しくは、「 [UI Automation Events Overview](ui-automation-events-overview.md)」をご覧ください。  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] イベント|サポート|メモ|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|必要|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|必須|なし|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|依存|コントロールが Selection コントロール パターンをサポートする場合は、このイベントをサポートする必要があります。|  
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent>|必須|なし|  
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent>|必須|なし|  
|<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> プロパティ変更イベント。|しない|なし|  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Automation.ControlType.Document>
- [UI オートメーション コントロール型の概要](ui-automation-control-types-overview.md)
- [UI オートメーションの概要](ui-automation-overview.md)

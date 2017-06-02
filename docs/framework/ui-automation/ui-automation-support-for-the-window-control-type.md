---
title: "UI Automation Support for the Window Control Type | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UI Automation, Window control type"
  - "Window control type"
  - "control types, Window"
ms.assetid: 53be78a6-cdcc-4af3-a464-5927d19c54e8
caps.latest.revision: 19
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 19
---
# UI Automation Support for the Window Control Type
> [!NOTE]
>  このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージ <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] の最新情報については、「[Windows Automation API: UI オートメーション](http://go.microsoft.com/fwlink/?LinkID=156746)」をご覧ください。  
  
 このトピックでは、Window コントロール型の [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] サポートについて説明します。[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]でのコントロール型とは、コントロールが <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> プロパティを使用するために満たす必要がある一連の条件のことです。 条件には、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリー構造、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] プロパティの値、コントロール パターンに関する特定のガイドラインが含まれます。  
  
 ウィンドウ コントロールは、子オブジェクト \(タイトル バー、クライアント、その他のオブジェクトなど\) が含まれているウィンドウ フレームで構成されます。  
  
 以下のセクションの [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] の要件は、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]、[!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]、[!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] のいずれの場合でも、Window コントロール型を実装するすべてのコントロールに適用されます。  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## 必須の UI オートメーション ツリー構造  
 次の表に、ウィンドウ コントロールに関連する [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーのコントロール ビューとコンテンツ ビューを示し、それぞれのビューに含めることができる内容について説明します。[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーについて詳しくは、「[UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)」をご覧ください。  
  
|コントロール ビュー|コンテンツ ビュー|  
|----------------|---------------|  
|ウィンドウ|ウィンドウ|  
  
<a name="Required_UI_Automation_Properties"></a>   
## 必須の UI オートメーション プロパティ  
 次の表に、ウィンドウ コントロールに特に関連する値または定義を持つ [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] プロパティを示します。[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] プロパティについて詳しくは、「[UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)」をご覧ください。  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] プロパティ|値|ノート|  
|---------------------------------------------------------------------------------|-------|---------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|「ノート」をご覧ください。|このプロパティの値は、アプリケーションのすべてのコントロールで一意である必要があります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|「ノート」をご覧ください。|コントロール全体を格納する最も外側の四角形。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|「ノート」をご覧ください。|ウィンドウ コントロールにはクリック可能なポイントがなければならず、これをクリックすることによってウィンドウが選択、または選択解除された状態になります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|\[Window\]|この値は、すべての UI フレームワークで同じです。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|ウィンドウ コントロールは、常にコンテンツである必要があります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|ウィンドウ コントロールは、常にコントロールである必要があります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|「ノート」をご覧ください。|コントロールがキーボード フォーカスを受け取ることができる場合は、このプロパティをサポートする必要があります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`null`|ウィンドウ コントロールには、静的な Window ラベルがありません。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"window"|Window コントロール型に対応する、ローカライズされた文字列。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|「ノート」をご覧ください。|ウィンドウ コントロールには、主要なウィンドウ要素が常に含まれています。この要素は、ユーザーがその項目の最もセマンティックな識別子として関連付けるであろうものに関連しています。|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## 必須の UI オートメーション コントロール パターン  
 次の表に、ウィンドウ コントロールでサポートする必要がある [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] コントロール パターンの一覧を示します。 コントロール パターンについて詳しくは、「[UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)」をご覧ください。  
  
|コントロール パターン|Support|ノート|  
|-----------------|-------------|---------|  
|<xref:System.Windows.Automation.Provider.IDockProvider>|条件|ウィンドウがドッキングできる場合は、サポートする必要があります。|  
|<xref:System.Windows.Automation.Provider.ITransformProvider>|必要|ウィンドウが画面上で移動、サイズ変更、または回転できるようにします。|  
|<xref:System.Windows.Automation.Provider.IWindowProvider>|必要|ウィンドウで特定の操作ができるようにします。|  
  
<a name="Required_UI_Automation_Events"></a>   
## 必須の UI オートメーション イベント  
 次の表に、すべてのウィンドウ コントロールでサポートする必要がある [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] イベントを示します。 イベントについて詳しくは、「[UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md)」をご覧ください。  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] イベント|Support|ノート|  
|--------------------------------------------------------------------------------|-------------|---------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AsyncContentLoadedEvent>|必要|なし|  
|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|必要|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent>|必要|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|必要|なし|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> プロパティ変更イベント。|状況に依存|なし|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> プロパティ変更イベント。|状況に依存|なし|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> プロパティ変更イベント。|状況に依存|なし|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> プロパティ変更イベント。|状況に依存|なし|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> プロパティ変更イベント。|状況に依存|なし|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> プロパティ変更イベント。|状況に依存|なし|  
|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowClosedEvent>|必要|なし|  
|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowOpenedEvent>|必要|なし|  
|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowVisualStateProperty> プロパティ変更イベント。|状況に依存|なし|  
  
## 参照  
 <xref:System.Windows.Automation.ControlType.Window>   
 [UI Automation Control Types Overview](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)   
 [UI Automation Overview](../../../docs/framework/ui-automation/ui-automation-overview.md)
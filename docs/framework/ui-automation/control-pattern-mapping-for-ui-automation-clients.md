---
title: UI オートメーション クライアント向けコントロール パターンのマッピング
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: cfd8e5dbe34df7b947646c714a360cf56b0435a4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043857"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>UI オートメーション クライアント向けコントロール パターンのマッピング
> [!NOTE]
> このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。 の最新情報[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]については[、「Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 このトピックでは、コントロール型とそれに関連するコントロール パターンを示します。  
  
 次の表に、コントロール パターンを次のカテゴリに整理して示します。  
  
- サポートされています。 コントロールはこのコントロール パターンをサポートする必要があります。  
  
- 条件付きサポート。 コントロールは、その状態に応じてこのコントロール パターンをサポートする場合があります。  
  
- サポートされていません。 コントロールはこのコントロール パターンをサポートしません。カスタム コントロールは、このコントロール パターンをサポートする場合があります。  
  
> [!NOTE]
> 一部のコントロールは、その機能に応じて複数のコントロール パターンを条件付きでサポートします。 たとえば、メニュー項目コントロールは、メニュー コントロール内での機能に応じて、 <xref:System.Windows.Automation.InvokePattern>、 <xref:System.Windows.Automation.ExpandCollapsePattern>、 <xref:System.Windows.Automation.TogglePattern>、または <xref:System.Windows.Automation.SelectionItemPattern> コントロール パターンを条件付きでサポートします。  
  
<a name="control_mapping_clients"></a>   
## <a name="ui-automation-control-patterns-for-clients"></a>クライアントの UI オートメーション コントロール パターン  
  
|コントロール型|Supported|条件付きサポート|サポート非対象|  
|------------------|---------------|-------------------------|-------------------|  
|ボタン|なし|呼び出し、トグル、展開/折りたたみ|なし|  
|予定表|グリッド、テーブル|選択、スクロール|値|  
|チェック ボックス|切り替え|なし|なし|  
|コンボ ボックス|展開/折りたたみ|選択、値|スクロール|  
|データ グリッド|グリッド|スクロール、選択、テーブル|なし|  
|データ項目|選択項目|展開/折りたたみ、グリッド項目、スクロール項目、テーブル、トグル、値|なし|  
|ドキュメント|テキスト|スクロール、値|なし|  
|編集|なし|テキスト、範囲の値、値|なし|  
|グループ化|なし|展開/折りたたみ|なし|  
|ヘッダー|なし|変換|なし|  
|ヘッダー項目|なし|変換、呼び出し|なし|  
|ハイパーリンク|呼び出し|値|なし|  
|イメージ|なし|グリッド項目、テーブル項目|呼び出し、選択項目|  
|List|なし|グリッド、複数のビュー、スクロール、選択|テーブル|  
|リスト項目|選択項目|展開/折りたたみ、グリッド項目、呼び出し、スクロール項目、トグル、値|なし|  
|メニュー|なし|なし|なし|  
|メニュー バー|なし|展開/折りたたみ、ドック、変換|なし|  
|メニュー項目|なし|展開/折りたたみ、呼び出し、選択項目、トグル|なし|  
|ペイン|なし|ドック、 スクロール、変換|[Window]|  
|進行状況バー|なし|範囲の値、値|なし|  
|オプション ボタン|選択項目|なし|切り替え|  
|スクロール バー|なし|範囲値|スクロール|  
|区切り記号|なし|なし|なし|  
|スライダー|なし|範囲の値、選択、値|なし|  
|Spinner|なし|範囲の値、選択、値|なし|  
|分割ボタン|呼び出し、展開/折りたたみ|なし|なし|  
|ステータス バー|なし|グリッド|なし|  
|Tab|選択ツール|スクロール|なし|  
|タブ項目|選択項目|なし|呼び出し|  
|テーブル|グリッド、グリッド項目、テーブル、テーブル項目|なし|なし|  
|テキスト|なし|グリッド項目、テーブル項目、テキスト|値|  
|つまみ|変換|なし|なし|  
|タイトル バー|なし|なし|なし|  
|ツール バー|なし|ドック、展開/折りたたみ、変換|なし|  
|ツール ヒント|なし|テキスト、ウィンドウ|なし|  
|ツリー|なし|スクロール、選択|なし|  
|ツリー項目|展開/折りたたみ|呼び出し、スクロール項目、選択項目、トグル|なし|  
|ウィンドウ|変換、ウィンドウ|ドッキング|なし|  
  
> [!NOTE]
> 上記のサポート対象のコントロール パターンが存在せず、条件付きサポートのコントロール パターンが 1 つ以上存在するコントロール型では、それらの条件付きコントロール パターンのうちの 1 つが必ずサポートされます。  
  
## <a name="see-also"></a>関連項目

- [UI オートメーションの概要](ui-automation-overview.md)

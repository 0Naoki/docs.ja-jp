---
title: UI オートメーション要素のプロパティの取得
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: cb9e37c80c7bc32a29022ede0bffc06a0f6ac5b1
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2018
ms.locfileid: "47234943"
---
# <a name="get-ui-automation-element-properties"></a>UI オートメーション要素のプロパティの取得
> [!NOTE]
>  このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]に関する最新情報については[Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746)をご覧ください。  
  
 このトピックのプロパティを取得する方法を示しています、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]要素。  
  
### <a name="get-a-current-property-value"></a>現在のプロパティ値を取得します。  
  
1.  取得、<xref:System.Windows.Automation.AutomationElement>を取得するプロパティを持つ。  
  
2.  呼び出す<xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>、または取得、<xref:System.Windows.Automation.AutomationElement.Current%2A>プロパティ構造とそのメンバーの 1 つから値を取得します。  
  
### <a name="get-a-cached-property-value"></a>キャッシュされたプロパティ値を取得します。  
  
1.  取得、<xref:System.Windows.Automation.AutomationElement>を取得するプロパティを持つ。 プロパティが指定されている必要があります、<xref:System.Windows.Automation.CacheRequest>します。  
  
2.  呼び出す<xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>、または取得、<xref:System.Windows.Automation.AutomationElement.Cached%2A>プロパティ構造とそのメンバーの 1 つから値を取得します。  
  
## <a name="example"></a>例  
 次の例では、現在のプロパティを取得するさまざまな方法を示しています、<xref:System.Windows.Automation.AutomationElement>します。  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>関連項目  
 [クライアントの UI オートメーション プロパティ](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [UI オートメーションにおけるキャッシュの使用](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [UI オートメーション クライアントにおけるキャッシュ](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)

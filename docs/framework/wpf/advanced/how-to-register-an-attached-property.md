---
title: "方法 : 添付プロパティを登録する"
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
- attached properties [WPF], registering
- registering attached properties [WPF]
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aecb5d2f35b8532ad2ae7558af1a93243b0fd6df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-register-an-attached-property"></a>方法 : 添付プロパティを登録する
この例では、添付プロパティを登録する方法、および [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] とコードの両方でプロパティを使用できるようにパブリック アクセサーを提供する方法を示します。 添付プロパティは、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] で定義されている構文の概念です。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の型のほとんどの添付プロパティは、依存関係プロパティとしても実装されます。 依存関係プロパティを使用するには、いずれかで<xref:System.Windows.DependencyObject>型です。  
  
## <a name="example"></a>例  
 次の例を使用して、依存関係プロパティとして添付プロパティを登録する方法を示しています、<xref:System.Windows.DependencyProperty.RegisterAttached%2A>メソッドです。 プロバイダー クラスは、プロパティの既定のメタデータを提供するオプションを持っています。この既定値は、別のクラスに対してプロパティが使用されるときに適用されます (そのクラスがメタデータをオーバーライドしない場合)。 この例では、`IsBubbleSource` プロパティの既定値は `false` に設定されています。  
  
 添付プロパティ (依存関係プロパティとして登録されていなくても) のプロバイダー クラスは、`Set`*[AttachedPropertyName]* および `Get`*[AttachedPropertyName]* の名前付け規則に従う静的な get および set アクセサーを提供する必要があります。 これらのアクセサーは、機能している [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] リーダーがプロパティを [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の属性として認識し、適切な型を解決できるために必要です。  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.DependencyProperty>  
 [依存関係プロパティの概要](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [カスタム依存関係プロパティ](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [方法トピック](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)

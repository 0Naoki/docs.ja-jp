---
title: '方法: SystemFonts を使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: bf99d716c5c41b7604244022d2e58423594a9cf3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674873"
---
# <a name="how-to-use-systemfonts"></a>方法: SystemFonts を使用する
この例の静的なリソースを使用する方法を示しています、<xref:System.Windows.SystemFonts>クラスのスタイル設定やボタンをカスタマイズするためにします。  
  
## <a name="example"></a>例  
 システム リソースは、システム設定と一貫性のあるビジュアルを作成できるようにするために、いくつかのシステムによって決定される値を、リソースおよびプロパティの両方として公開します。 <xref:System.Windows.SystemFonts> 静的プロパティは、および実行時にこれらの値を動的にアクセスするために使用するリソース キーを参照するプロパティとしての両方のシステム フォント値を含むクラスです。 たとえば、<xref:System.Windows.SystemFonts.CaptionFontFamily%2A>は、<xref:System.Windows.SystemFonts>値と<xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>が対応するリソース キー。  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]のメンバーを使用する<xref:System.Windows.SystemFonts>として静的プロパティまたは (キーとして静的プロパティの値) を含む動的リソース参照のいずれか。 アプリケーションの実行時にフォント メトリックを自動的に更新する場合は、動的リソース参照を使用します。それ以外の場合は、静的な値参照を使用します。  
  
> [!NOTE]
>  リソース キーでは、プロパティ名に"Key"というサフィックスが付いています。  
  
 次の例のプロパティを使用してアクセスする方法を示しています。<xref:System.Windows.SystemFonts>のスタイル設定やボタンをカスタマイズするために静的な値として。 このマークアップの例を割り当てます<xref:System.Windows.SystemFonts>をボタンの値。  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 値を使用する<xref:System.Windows.SystemFonts>コードでは、静的な値または動的リソース参照のいずれかを使用する必要はありません。 代わりのキー以外のプロパティを使用して、<xref:System.Windows.SystemFonts>クラス。 キー以外のプロパティは、実行時の動作の静的プロパティとして定義[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]によってホストされている、システムがリアルタイムでプロパティを再評価および値のシステムのユーザーによる変更が適切に考慮します。 次の例では、ボタンのフォント設定を指定する方法を示します。  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.SystemFonts>
- [システム ブラシで領域を塗りつぶす](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [SystemParameters を使用する](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)
- [システム フォント キーを使用する](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)
- [方法トピック](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
- [x:Static のマークアップ拡張機能](../../../../docs/framework/xaml-services/x-static-markup-extension.md)
- [XAML リソース](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [DynamicResource マークアップ拡張](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)

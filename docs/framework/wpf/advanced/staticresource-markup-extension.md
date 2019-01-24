---
title: StaticResource のマークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
ms.openlocfilehash: 5d6c660dba1a351df4dafd756bcabd484b9afad6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554934"
---
# <a name="staticresource-markup-extension"></a>StaticResource のマークアップ拡張機能
いずれかの値を提供[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]定義済みのリソースへの参照を検索することで、プロパティの属性。 そのリソースの検索動作が読み込み時の検索は、現在のマークアップから以前に読み込まれたリソースは検索に似ています[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ページおよびその他のアプリケーションのソースととしてそのリソースの値が生成されます、実行時のオブジェクトのプロパティの値です。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>XAML オブジェクト要素の使用方法  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 値  
  
|||  
|-|-|  
|`key`|要求されたリソースのキー。 このキーはによって最初に割り当てられた、 [X:key ディレクティブ](../../../../docs/framework/xaml-services/x-key-directive.md)リソースのマークアップでは、作成されたまたはが指定されているかどうか、`key`パラメーターを呼び出すときに<xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>リソースは、コードで作成した場合。|  
  
## <a name="remarks"></a>Remarks  
  
> [!IMPORTANT]
>  A`StaticResource`定義されているリソースへの前方参照を読み取ろうとしないで内で構文的にさらに、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ファイル。 操作がサポートされていないと、前方参照しようとしていますが、読み込み時間のパフォーマンスの低下ような参照が失敗しない場合でも発生時に、内部ハッシュ テーブルを表す、<xref:System.Windows.ResourceDictionary>が検索されます。 最良の結果を前方参照を回避するように、リソース ディクショナリの構成を調整します。 前方参照を回避できない場合は、使用[DynamicResource マークアップ拡張機能](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)代わりにします。  
  
 指定した<xref:System.Windows.StaticResourceExtension.ResourceKey%2A>で識別される、既存のリソースに対応する必要があります、 [X:key ディレクティブ](../../../../docs/framework/xaml-services/x-key-directive.md)ページ、アプリケーション、使用可能なコントロールのテーマと外部のリソース、またはシステム リソースのいくつかのレベル。 リソース検索は、その順序で発生します。 静的および動的なリソースのリソースの検索の動作の詳細については、次を参照してください。 [XAML リソース](../../../../docs/framework/wpf/advanced/xaml-resources.md)します。  
  
 リソース キーは、任意の文字列で定義されている、 [XamlName の文法](../../../../docs/framework/xaml-services/xamlname-grammar.md)します。 リソース キーがなど、他のオブジェクトの種類を指定もできます、<xref:System.Type>します。 A<xref:System.Type>キーがどのコントロール スタイルを設定できます、テーマによって、暗黙的なスタイルのキーを使用する基本的な。 詳しくは、「[コントロールの作成の概要](../../../../docs/framework/wpf/controls/control-authoring-overview.md)」を参照してください。  
  
 リソースを参照するための代替の宣言型の手段は、 [DynamicResource マークアップ拡張機能](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)します。  
  
 属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。 `StaticResource` 識別子文字列の後に設定される文字列トークンは、基になる <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 拡張クラスの <xref:System.Windows.StaticResourceExtension> 値として割り当てられます。  
  
 `StaticResource` オブジェクト要素構文で使用できます。 この場合は、値を指定する、<xref:System.Windows.StaticResourceExtension.ResourceKey%2A>プロパティが必要です。  
  
 `StaticResource` は、<xref:System.Windows.StaticResourceExtension.ResourceKey%2A> プロパティをプロパティおよび値のペアとして指定する詳細出力属性使用でも使用できます。  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 詳細出力の使用は、複数の設定可能プロパティを持つ拡張機能や、一部のプロパティがオプションである場合に役立ちます。 `StaticResource` には、必須の設定可能プロパティが 1 つしか存在しないため、このような詳細出力の使用は一般的ではありません。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサの実装でこのマークアップ拡張機能の処理が定義されている、<xref:System.Windows.StaticResourceExtension>クラス。  
  
 `StaticResource` はマークアップ拡張機能です。 一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。 すべてのマークアップ拡張機能で[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を使用して、{および} される規則は、それぞれの属性構文内の文字を[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサを認識するマークアップ拡張機能が、属性を処理する必要があります。 詳細については、次を参照してください。[マークアップ拡張機能と WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)します。  
  
## <a name="see-also"></a>関連項目
- [スタイルとテンプレート](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [XAML の概要 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [マークアップ拡張機能と WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [XAML リソース](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [リソースとコード](../../../../docs/framework/wpf/advanced/resources-and-code.md)

---
title: "TextBox のスタイルとテンプレート"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d4fdb652876f2df049b71c18b0b79b7b435da8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="textbox-styles-and-templates"></a>TextBox のスタイルとテンプレート
このトピックは、のスタイルとテンプレートについて説明します、<xref:System.Windows.Controls.TextBox>コントロール。 既定値を変更することができます<xref:System.Windows.Controls.ControlTemplate>コントロールの外観を一意にします。 詳細については、「[Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)」を参照してください。  
  
## <a name="textbox-parts"></a>テキスト ボックスの部分  
 次の表に、名前付きのパーツの<xref:System.Windows.Controls.TextBox>コントロール。  
  
|パーツ|型|説明|  
|-|-|-|  
|PART_ContentHost|<xref:System.Windows.FrameworkElement>|視覚的要素を含むことができます、<xref:System.Windows.FrameworkElement>です。 テキスト、<xref:System.Windows.Controls.TextBox>はこの要素に表示されます。|  
  
## <a name="textbox-states"></a>テキスト ボックスの状態  
 次の表に、用ビジュアル状態、<xref:System.Windows.Controls.TextBox>コントロール。  
  
|VisualState 名|VisualStateGroup 名|説明|  
|----------------------|---------------------------|-----------------|  
|標準|CommonStates|既定の状態です。|  
|MouseOver|CommonStates|マウス ポインターがコントロール上に配置されます。|  
|無効|CommonStates|コントロールが無効になっています。|  
|ReadOnly|CommonStates|ユーザーが内のテキストを変更できない、<xref:System.Windows.Controls.TextBox>です。|  
|フォーカスされている|FocusStates|コントロールにフォーカスがあります。|  
|フォーカスされていない|FocusStates|コントロールにフォーカスがありません。|  
|有効|ValidationStates|コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。|  
  
## <a name="textbox-controltemplate-example"></a>TextBox ControlTemplate の例  
 次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.TextBox>コントロール。  
  
 [!code-xaml[ControlTemplateExamples#TextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 前の例では、次のリソースの 1 つ以上を使用します。  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 完全なサンプルについては、[Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041)を参照してください。  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [コントロールのスタイルとテンプレート](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [コントロールのカスタマイズ](../../../../docs/framework/wpf/controls/control-customization.md)  
 [スタイルとテンプレート](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)

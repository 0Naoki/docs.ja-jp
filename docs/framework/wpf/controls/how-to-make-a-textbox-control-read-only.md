---
title: '方法: TextBox コントロールを読み取り専用にする'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 1e9d333f22099d9593e58b4087f185b2988215ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517176"
---
# <a name="how-to-make-a-textbox-control-read-only"></a>方法: TextBox コントロールを読み取り専用にする
この例は、構成する方法を示します、<xref:System.Windows.Controls.TextBox>コントロールをユーザー入力または変更できません。  
  
## <a name="example"></a>例  
 内容を変更できないようにする、<xref:System.Windows.Controls.TextBox>設定、制御、<xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>属性を**true**します。  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>属性がユーザー入力のみに影響; 内のテキスト セットには影響しません、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]の説明、<xref:System.Windows.Controls.TextBox>コントロール、またはプログラムにより設定されたテキスト、<xref:System.Windows.Controls.TextBox.Text%2A>プロパティ。  
  
 既定値<xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>は**false**します。  
  
## <a name="see-also"></a>関連項目
- [TextBox の概要](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [RichTextBox の概要](../../../../docs/framework/wpf/controls/richtextbox-overview.md)

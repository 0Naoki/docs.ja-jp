---
title: "方法 : セットとして機能する Windows フォーム RadioButton コントロールをグループ化する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 37d8571624272f62c6ce327b0ed25e082c5cf713
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>方法 : セットとして機能する Windows フォーム RadioButton コントロールをグループ化する
Windows フォーム<xref:System.Windows.Forms.RadioButton>ユーザーがいるプロシージャまたはオブジェクトを 1 つのみを割り当てることが、2 つ以上の設定の間で選択できるようにデザインされています。 たとえば、一連の<xref:System.Windows.Forms.RadioButton>コントロールは、注文の配送業者をパッケージの選択を表示できますが、通信事業者の 1 つだけ使用します。 1 つだけしたがって<xref:System.Windows.Forms.RadioButton>一度に選択できる場合でも、機能グループの一部であります。  
  
 オプション ボタンをグループ化することによって、コンテナーの内部など、<xref:System.Windows.Forms.Panel>コントロール、<xref:System.Windows.Forms.GroupBox>コントロール、またはフォームです。 フォームになる 1 つのグループに直接追加されるすべてのオプション ボタンです。 別のグループを追加するには、パネルまたはグループ ボックス内に配置する必要があります。 パネルまたはグループ ボックスの詳細については、次を参照してください。 [Panel コントロールの概要](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)または[GroupBox コントロールの概要](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)です。  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>その他のセットとは無関係に関数をセットとして RadioButton コントロールをグループ化  
  
1.  ドラッグ、<xref:System.Windows.Forms.GroupBox>または<xref:System.Windows.Forms.Panel>から制御、 **Windows フォーム**タブで、**ツールボックス**フォーム上にします。  
  
2.  描画<xref:System.Windows.Forms.RadioButton>コントロールに対して、<xref:System.Windows.Forms.GroupBox>または<xref:System.Windows.Forms.Panel>コントロール。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.RadioButton>  
 [RadioButton コントロールの概要](../../../../docs/framework/winforms/controls/radiobutton-control-overview-windows-forms.md)  
 [Panel コントロールの概要](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [GroupBox コントロールの概要](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [CheckBox コントロールの概要](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [RadioButton コントロール](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)

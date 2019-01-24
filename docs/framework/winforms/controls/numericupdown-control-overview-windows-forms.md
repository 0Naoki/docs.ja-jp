---
title: NumericUpDown コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
ms.openlocfilehash: 95fab00555231f7605e9104e8264f88b0909785a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671435"
---
# <a name="numericupdown-control-overview-windows-forms"></a>NumericUpDown コントロールの概要 (Windows フォーム)
<xref:System.Windows.Forms.NumericUpDown>コントロールがテキスト ボックスの組み合わせと 1 対の矢印、値を調整する、ユーザーがクリックできるようになります。 コントロールは、表示し、固定の数値の選択肢の一覧から 1 つの数値を設定します。 ユーザーは、増加し、上下の矢印キーを押すか、コントロールのテキスト ボックスの一部で数値を入力して下矢印をクリックして、数を減らします。 上矢印キーをクリックすると、数値が最大方向を移動します。下方向キーをクリックすると、数値が最低限の方向が移動します。  
  
 では、汎用的な機能のためこのコントロールは、ミュージック プレーヤー アプリケーションのボリューム コントロールを作成する場合など、明白な選択肢では、が。 <xref:System.Windows.Forms.NumericUpDown>コントロールは、多くの Windows コントロール パネル アプリケーションで使用されます。  
  
## <a name="key-properties-and-methods"></a>キー プロパティとメソッド  
 コントロールのテキスト ボックスに表示する数値は 16 進数などの形式のさまざまなで指定できます。 詳細については、「[方法 :Windows フォームの NumericUpDown コントロールの書式を設定](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)します。 コントロールのプロパティは<xref:System.Windows.Forms.NumericUpDown.Value%2A>、 <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (既定値は 100)、 <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (既定値 0)、および<xref:System.Windows.Forms.NumericUpDown.Increment%2A>(既定値 1)。 <xref:System.Windows.Forms.NumericUpDown.Value%2A>プロパティ、コントロールで選択されている現在の数を設定します。 <xref:System.Windows.Forms.NumericUpDown.Increment%2A>プロパティは、ユーザーが上向きまたは下向きの矢印に数を調整する量を設定します。 コントロールからフォーカスが移動と、は、最小値と最大の数値に対して任意の型指定された入力が検証されます。 継続的に押す矢印または下向き矢印、数字、を通じてコントロールを移動する速度を上げることで、<xref:System.Windows.Forms.NumericUpDown.Accelerations%2A>プロパティ。 コントロールの主要なメソッドは<xref:System.Windows.Forms.NumericUpDown.UpButton%2A>と<xref:System.Windows.Forms.NumericUpDown.DownButton%2A>します。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown コントロール](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)
- [方法: Windows フォームの NumericUpDown コントロールの形式を設定します。](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)
- [TextBox コントロール](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)

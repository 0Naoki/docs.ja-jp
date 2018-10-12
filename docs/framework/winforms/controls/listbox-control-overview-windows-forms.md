---
title: ListBox コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: d4cb423a6f32778695abeae725da9755b610d209
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537565"
---
# <a name="listbox-control-overview-windows-forms"></a>ListBox コントロールの概要 (Windows フォーム)
Windows フォーム<xref:System.Windows.Forms.ListBox>コントロールには、ユーザーが 1 つまたは複数の項目を選択できる一覧が表示されます。 スクロール バーが自動的に追加する項目の合計数が表示できる数を超えた場合、<xref:System.Windows.Forms.ListBox>コントロール。 ときに、<xref:System.Windows.Forms.ListBox.MultiColumn%2A>プロパティに設定されている`true`、リスト ボックス項目を複数の列に表示して、水平スクロール バーが表示されます。 ときに、<xref:System.Windows.Forms.ListBox.MultiColumn%2A>プロパティに設定されている`false`、リスト ボックス項目を 1 つの列で表示して、垂直スクロール バーが表示されます。 ときに<xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A>に設定されている`true`項目の数に関係なく、スクロール バーが表示されます。 <xref:System.Windows.Forms.ListBox.SelectionMode%2A>プロパティは、一度に選択できるリスト項目の数を決定します。  
  
## <a name="ways-to-change-the-listbox-control"></a>ListBox コントロールを変更する方法  
 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>プロパティは、リスト ボックスで選択した最初の項目に対応する整数値を返します。 変更することで、選択した項目をプログラムで変更することができます、<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>コード内の値以外の場合は、リスト内の対応する項目は、Windows フォームで、強調表示されます。 項目が選択されていない場合、<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>値は-1。 一覧の最初の項目が選択されている場合、<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>値は 0 です。 複数の項目を選択すると、<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>値は、一覧の先頭に表示される選択したアイテムを反映します。 <xref:System.Windows.Forms.ListBox.SelectedItem%2A>プロパティは<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>文字列値では通常、アイテム自体が返されます。 <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A>プロパティには、一覧で、項目の数との値が反映されます、<xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A>プロパティは常に 1 つ以上の最も可能性のある<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>ので値<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>は 0 から始まる。  
  
 項目を追加または削除、<xref:System.Windows.Forms.ListBox>コントロールを使用して、 <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>、 <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>、<xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A>または<xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A>メソッドです。 使用して、リストに項目を追加することができます、<xref:System.Windows.Forms.ListBox.Items%2A>デザイン時プロパティです。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.ListBox>  
 [方法: Windows フォームの ComboBox、ListBox、または CheckedListBox コントロールに項目を追加または削除する](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールを並べ替える](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [方法: Windows フォームの ComboBox または ListBox コントロールをデータにバインドする](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [ComboBox コントロールの概要](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [CheckedListBox コントロールの概要](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [オプションのリストを表示するための Windows フォーム コントロール](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールのルックアップ テーブルを作成する](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)

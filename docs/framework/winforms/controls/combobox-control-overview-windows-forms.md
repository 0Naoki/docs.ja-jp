---
title: "ComboBox コントロールの概要 (Windows フォーム)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 801ebb97c6ee52ce52bbb8f96a07d55e68ca6f1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="combobox-control-overview-windows-forms"></a>ComboBox コントロールの概要 (Windows フォーム)
Windows フォーム<xref:System.Windows.Forms.ComboBox>ドロップダウン コンボ ボックスにデータを表示するコントロールを使用します。 既定では、<xref:System.Windows.Forms.ComboBox>コントロールは、2 つの部分が表示されます。 最上部には、ユーザーがリスト項目を入力できるテキスト ボックス。 2 番目の部分は、元のユーザーが選択できる 1 つの項目の一覧を表示するリスト ボックスです。 コンボ ボックスの他のスタイルの詳細については、次を参照してください。 [Windows フォーム ComboBox Instead of リスト ボックスを使用するときに](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)です。  
  
 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>プロパティは、選択した項目を対応する整数値を返します。 変更することで、選択した項目をプログラムで変更することができます、<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>コード内の値以外の場合は、リスト内の対応する項目は、コンボ ボックスのテキスト ボックスの部分に表示されます。 項目が選択されていない場合、<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>値は-1。 一覧の最初の項目が選択されている場合、<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>値は 0 です。 <xref:System.Windows.Forms.ComboBox.SelectedItem%2A>プロパティは<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>文字列値では通常、アイテム自体が返されます。 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A>プロパティには、一覧で、項目の数との値が反映されます、<xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A>プロパティは常に 1 つ以上の最も可能性のある<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>ので値<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>は 0 から始まる。  
  
 項目を追加または削除、<xref:System.Windows.Forms.ComboBox>コントロールを使用して、 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>、 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>、<xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A>または<xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A>メソッドです。 使用して、リストに項目を追加することができます、<xref:System.Windows.Forms.ComboBox.Items%2A>デザイナーのプロパティにします。  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.Forms.ComboBox>  
 [ListBox コントロールの概要](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [ListBox の代わりに Windows フォーム ComboBox を使用する場合](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [方法: Windows フォームの ComboBox、ListBox、または CheckedListBox コントロールに項目を追加または削除する](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールを並べ替える](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールの特定の項目にアクセスする](../../../../docs/framework/winforms/controls/access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)  
 [方法: Windows フォームの ComboBox または ListBox コントロールをデータにバインドする](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [オプションのリストを表示するための Windows フォーム コントロール](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールのルックアップ テーブルを作成する](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)

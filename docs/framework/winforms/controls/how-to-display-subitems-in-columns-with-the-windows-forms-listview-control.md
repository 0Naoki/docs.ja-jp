---
title: '方法: Windows フォーム ListView コントロールでの列にサブ項目を表示'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: bd41dda048aadc399c7f8ffe0926b010991d08a0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686752"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a>方法: Windows フォーム ListView コントロールでの列にサブ項目を表示
Windows フォーム<xref:System.Windows.Forms.ListView>コントロールは、追加のテキスト、または詳細ビュー内の各アイテムのサブ項目を表示できます。 最初の列には、項目のテキスト、たとえば、従業員数が表示されます。 2 番目、3 番目、および後続の列が 2 番目に、最初を表示し、後続の関連するサブ項目。  
  
### <a name="to-add-subitems-to-a-list-item"></a>リスト項目にサブ項目を追加するには  
  
1.  必要なすべての列を追加します。 最初の列は、項目の表示されるため<xref:System.Windows.Forms.ListView.Text%2A>プロパティ、サブ項目の数より 1 つ以上の列を必要です。 列を追加する方法の詳細については、次を参照してください。[方法。列を Windows フォーム ListView コントロールを追加する](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)します。  
  
2.  呼び出す、<xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A>メソッドによって返されるコレクションの<xref:System.Windows.Forms.ListViewItem.SubItems%2A>項目のプロパティ。 次のコード例では、リスト項目の部門と従業員の名前を設定します。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>関連項目
- [ListView コントロールの概要](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
- [方法: Windows フォーム ListView コントロールで項目追加および削除](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [方法: Windows フォーム ListView コントロールに列を追加します。](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)
- [方法: Windows フォーム ListView コントロールのアイコンを表示します。](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)
- [方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加します。](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)

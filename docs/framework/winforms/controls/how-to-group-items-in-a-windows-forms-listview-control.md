---
title: '方法 : Windows フォーム ListView コントロールの項目をグループ化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: 2847b95694eefec524bee9c95b5de91fa5a03f5d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865710"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>方法 : Windows フォーム ListView コントロールの項目をグループ化する
グループ化機能で、<xref:System.Windows.Forms.ListView>コントロール、グループ内のアイテムの関連する設定を表示できます。 これらのグループは、画面に含まれるグループのタイトルは水平方向のグループ ヘッダーで区切られます。 使用することができます<xref:System.Windows.Forms.ListView>グループ日付、または他の論理グループで、アルファベット順に項目をグループ化して簡単に大きい一覧を移動します。 次の図には、いくつかのグループ化された項目が表示されます。  
  
 ![ListView グループ](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
ListView の項目をグループ化  
  
 グループ化を有効にするには、最初にデザイナーで、またはプログラムでは、1 つまたは複数のグループを作成する必要があります。 グループが定義された後に割り当てることができます<xref:System.Windows.Forms.ListView>項目をグループにします。 移動することも項目 1 つのグループから別にプログラムを使用します。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> のみ使用可能なグループ[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]、アプリケーションを呼び出すと、<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>メソッド。 以前のオペレーティング システムでは、グループに関するすべてのコードが影響を与えません、グループは表示されません。 詳細については、「<xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>」を参照してください。  
  
### <a name="to-add-groups"></a>グループを追加するには  
  
1.  <xref:System.Windows.Forms.ListView.Groups%2A> コレクションの <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> メソッドを使用します。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>グループを削除するには  
  
1.  使用して、<xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>または<xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>のメソッド、<xref:System.Windows.Forms.ListView.Groups%2A>コレクション。  
  
     <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>メソッドは 1 つのグループを削除、<xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>メソッドは、一覧からすべてのグループを削除します。  
  
    > [!NOTE]
    >  グループを削除する場合はそのグループ内の項目は削除されません。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>項目をグループに割り当てるか、グループ間で項目を移動するには  
  
1.  設定、<xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType>個々 のアイテムのプロパティ。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [ListView コントロール](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [ListView コントロールの概要](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Windows XP の機能と Windows フォーム コントロール](https://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [方法: Windows フォーム ListView コントロールで項目を追加および削除する](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)

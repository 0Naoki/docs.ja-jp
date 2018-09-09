---
title: '方法 : デザイナーで Windows フォーム ListView コントロールを使って項目を追加および削除する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 0480c8980f0eba17229fff0c1e947cac5216fb9e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44225335"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>方法 : デザイナーで Windows フォーム ListView コントロールを使って項目を追加および削除する
Windows フォームに項目を追加するプロセス<xref:System.Windows.Forms.ListView>コントロールは、主にアイテムを指定して、プロパティを割り当てます。 追加またはリスト項目の削除は、いつでも実行できます。  
  
 次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.ListView>コントロール。 このようなプロジェクトの設定の詳細については、次を参照してください。[方法: Windows アプリケーション プロジェクトを作成](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)と[方法: Windows フォームにコントロールを追加](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)します。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。  
  
### <a name="to-add-or-remove-items-using-the-designer"></a>デザイナーを使用して項目を追加または削除  
  
1.  <xref:System.Windows.Forms.ListView> コントロールを選択します。  
  
2.  **プロパティ**ウィンドウで、をクリックして、**省略記号**(![VisualStudioEllipsesButton スクリーン ショット](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) ボタンを<xref:System.Windows.Forms.ListView.Items%2A>プロパティ。  
  
     **ListViewItem コレクション エディター**が表示されます。  
  
3.  項目を追加する をクリックして、**追加**ボタンをクリックします。 など、新しい項目のプロパティを設定することができますし、<xref:System.Windows.Forms.ListView.Text%2A>と<xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>プロパティ。  
  
4.  項目を削除するを選択し、クリックして、**削除**ボタンをクリックします。  
  
## <a name="see-also"></a>関連項目  
 [ListView コントロールの概要](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [方法: Windows フォーム ListView コントロールに列を追加する](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [方法: Windows フォーム ListView コントロールの列にサブ項目を表示する](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [方法: Windows フォーム ListView コントロールのアイコンを表示する](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加する](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [方法: Windows フォーム ListView コントロールの項目をグループ化する](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)

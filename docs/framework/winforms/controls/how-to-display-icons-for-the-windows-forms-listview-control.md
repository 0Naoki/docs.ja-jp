---
title: "方法 : Windows フォーム ListView コントロールのアイコンを表示する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d9a8bdc54f3f321b37bda897aac1f340f7a46aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a>方法 : Windows フォーム ListView コントロールのアイコンを表示する
Windows フォーム<xref:System.Windows.Forms.ListView>コントロールは、次の 3 つのイメージ リストのアイコンを表示できます。 リスト、詳細、および SmallIcon ビューで指定されたイメージ リストのイメージを表示する、<xref:System.Windows.Forms.ListView.SmallImageList%2A>プロパティです。 LargeIcon ビューで指定されたイメージ リストのイメージを表示する、<xref:System.Windows.Forms.ListView.LargeImageList%2A>プロパティです。 リスト ビューでは、追加で設定アイコンのセットを表示できますも、<xref:System.Windows.Forms.ListView.StateImageList%2A>プロパティを大きいアイコンまたは小さいアイコンの横にあります。 イメージ リストの詳細については、次を参照してください。 [ImageList コンポーネント](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)と[する方法: 追加または削除する Windows フォームの ImageList コンポーネントにイメージを](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)です。  
  
### <a name="to-display-images-in-a-list-view"></a>リスト ビュー内のイメージを表示するには  
  
1.  適切なプロパティを設定する —<xref:System.Windows.Forms.ListView.SmallImageList%2A>、 <xref:System.Windows.Forms.ListView.LargeImageList%2A>、または<xref:System.Windows.Forms.ListView.StateImageList%2A>— を既存<xref:System.Windows.Forms.ImageList>コンポーネントを使用する場合します。  
  
     デザイナーの [プロパティ] ウィンドウまたはコードでは、これらのプロパティを設定できます。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2.  設定、<xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>または<xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A>アイコンが関連付けられている各リスト項目のプロパティです。  
  
     コードでは、内、またはこれらのプロパティを設定することができます、 **ListViewItem コレクション エディター**です。 開くには、 **ListViewItem コレクション エディター**、省略記号ボタン (![VisualStudioEllipsesButton スクリーン ショット](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton"))、の横にある<xref:System.Windows.Forms.ListView.Items%2A>プロパティを**プロパティ**ウィンドウです。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a>関連項目  
 [ListView コントロールの概要](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [方法: Windows フォーム ListView コントロールで項目を追加および削除する](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [方法: Windows フォーム ListView コントロールに列を追加する](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加する](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [ImageList コンポーネント](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)

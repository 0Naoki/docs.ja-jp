---
title: "方法 : ListView の各項目の MouseDoubleClick イベントを処理する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3fef9655ab95328e027a303df57c3359a7676eac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>方法 : ListView の各項目の MouseDoubleClick イベントを処理する
内の項目のイベントを処理するために、 <xref:System.Windows.Controls.ListView>、それぞれにイベント ハンドラーを追加する必要があります<xref:System.Windows.Controls.ListViewItem>です。 ときに、<xref:System.Windows.Controls.ListView>がバインドされて、データ ソースを明示的に作成しない、 <xref:System.Windows.Controls.ListViewItem>、追加することで各項目のイベントを処理することができますが、<xref:System.Windows.EventSetter>のスタイルを<xref:System.Windows.Controls.ListViewItem>です。  
  
## <a name="example"></a>例  
 次の例では、データ バインドされた<xref:System.Windows.Controls.ListView>を作成し、<xref:System.Windows.Style>ごとに、イベント ハンドラーを追加する<xref:System.Windows.Controls.ListViewItem>です。  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 次の例のハンドル、<xref:System.Windows.Controls.Control.MouseDoubleClick>イベント。  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  バインドする最も一般的な<xref:System.Windows.Controls.ListView>ごとに、イベント ハンドラーを追加するスタイルを使用するデータ ソースに<xref:System.Windows.Controls.ListViewItem>以外のデータ バインドで<xref:System.Windows.Controls.ListView>明示的に作成するかどうかに関係なく、<xref:System.Windows.Controls.ListViewItem>です。  詳細については明示的および暗黙的に作成<xref:System.Windows.Controls.ListViewItem>コントロールを参照してください<xref:System.Windows.Controls.ItemsControl>です。  
  
## <a name="see-also"></a>参照  
 <xref:System.Xml.XmlElement>  
 [データ バインディングの概要](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [スタイルとテンプレート](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [XMLDataProvider と XPath クエリを使用して XML データにバインドする](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [ListView の概要](../../../../docs/framework/wpf/controls/listview-overview.md)

---
title: "方法 : データ CollectionView のオブジェクト間を移動する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f20881ed452f1ec78381d17a32b4cc2c77305e0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>方法 : データ CollectionView のオブジェクト間を移動する
ビューでは、並べ替え、フィルター処理、またはグループ化に応じて、さまざまな方法で表示する同じデータ収集を許可します。 ビューも、現在のレコード ポインター概念を提供して、ポインターを移動できます。 この例は、現在のオブジェクトを取得できるだけでなくで提供される機能を使用して、データ コレクション内のオブジェクト間を移動する方法を示します、<xref:System.Windows.Data.CollectionView>クラスです。  
  
## <a name="example"></a>例  
 この例では`myCollectionView`は、<xref:System.Windows.Data.CollectionView>ビューでバインドされたコレクションであるオブジェクト。  
  
 次の例では、`OnButton`のイベント ハンドラー、`Previous`と`Next`ユーザーにデータ コレクションを移動できるボタンは、アプリケーションでは、ボタンです。 注意してください、<xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A>と<xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A>プロパティを報告するかどうか、現在のレコード ポインターに来た、先頭と末尾のリストのそれぞれためを<xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A>と<xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A>として適切に呼び出すことができます。  
  
 <xref:System.Windows.Data.CollectionView.CurrentItem%2A>ビューのプロパティとしてキャスト、`Order`をコレクション内で、現在の発注品目を返します。  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>関連項目  
 [データ バインディングの概要](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [ビュー内のデータの並べ替え](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [ビュー内のデータをフィルター処理する](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [XAML でビューを使用してデータの並べ替えおよびグループ化を行う](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [方法トピック](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

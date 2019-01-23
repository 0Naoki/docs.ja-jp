---
title: '方法: 装飾を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: f34bdeb87d0bf34a998f9b2e2fb6c42aedec5063
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591683"
---
# <a name="how-to-implement-an-adorner"></a>方法: 装飾を実装する
この例では、最小限の装飾の実装を示します。  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 装飾自体にはレンダリング動作が備わっていないので、装飾のレンダリングは装飾の実装側の責任で行う必要がある点に、注意が必要です。   一般的なレンダリングの動作を実装する方法は、オーバーライドする、<xref:System.Windows.UIElement.OnRender%2A>メソッドと 1 つ以上を使用して<xref:System.Windows.Media.DrawingContext>(この例で示す) のように、必要に応じて、装飾のビジュアルを表示するオブジェクト。  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 抽象から継承するクラスを実装することで、カスタム装飾が作成された<xref:System.Windows.Documents.Adorner>クラス。  例を装飾するだけのものの角に丸みを<xref:System.Windows.UIElement>オーバーライドすることで円で、<xref:System.Windows.UIElement.OnRender%2A>メソッド。  
  
### <a name="code"></a>コード  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a>関連項目
- [装飾の概要](../../../../docs/framework/wpf/controls/adorners-overview.md)

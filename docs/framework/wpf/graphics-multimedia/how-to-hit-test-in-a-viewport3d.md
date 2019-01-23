---
title: '方法: Viewport3D でヒット テストを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 0906fc0da363f9b4022eea863ec1140c8eeb2da2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494241"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a>方法: Viewport3D でヒット テストを実行する
この例では、ヒット テストでの 3D ビジュアルの<xref:System.Windows.Controls.Viewport3D>します。  
  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 2D および 3D の情報を返します 3D のみの結果を確認するテスト結果を反復処理することができます。  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 <xref:System.Windows.Media.HitTestResultBehavior>次のコードでヒット テストの結果を処理する方法を決定します。  `UpdateResultInfo` `UpdateMaterial`はローカルに定義されたメソッド。  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## <a name="see-also"></a>関連項目
- [3-D のヒット テストのサンプル](https://go.microsoft.com/fwlink/?LinkID=159959)

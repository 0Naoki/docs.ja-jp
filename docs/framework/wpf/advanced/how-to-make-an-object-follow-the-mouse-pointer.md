---
title: '方法: オブジェクトをマウス ポインターに追従させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: 3e39b9459fbc94c9b7684ffd7c597363e46ad717
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541821"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>方法: オブジェクトをマウス ポインターに追従させる
この例では、マウス ポインターを画面に移動すると、オブジェクトのサイズを変更する方法を示します。  
  
 例では、含まれています、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ファイルを作成する、[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]および分離コード ファイルをイベント ハンドラーを作成します。  
  
## <a name="example"></a>例  
 次[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]を作成、[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]から構成される、<xref:System.Windows.Shapes.Ellipse>内の<xref:System.Windows.Controls.StackPanel>、イベントのイベント ハンドラーをアタッチします、<xref:System.Windows.UIElement.MouseMove>イベント。  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 次のコードを作成、<xref:System.Windows.UIElement.MouseMove>イベント ハンドラー。  マウス ポインターを置いたとき、高さと幅、<xref:System.Windows.Shapes.Ellipse>して増減されます。  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>関連項目
- [入力の概要](../../../../docs/framework/wpf/advanced/input-overview.md)

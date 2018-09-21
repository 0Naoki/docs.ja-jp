---
title: '方法 : Win32 ホスト コンテナーを使用してヒット テストを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: bb175e0f8aeb126b7f7fa85d5af1c4afcf5bea61
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2018
ms.locfileid: "46491939"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>方法 : Win32 ホスト コンテナーを使用してヒット テストを実行する
内のビジュアル オブジェクトを作成することができます、[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]ウィンドウで、ビジュアル オブジェクトのホスト ウィンドウ コンテナーを提供します。 格納されているビジュアル オブジェクト用のイベント処理機能を提供するには、ホスト ウィンドウ コンテナーのメッセージ フィルター ループに渡されるメッセージを処理します。 参照してください[チュートリアル: Win32 アプリケーションでのビジュアル オブジェクトのホスト](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)でのビジュアル オブジェクトをホストする方法の詳細について、[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]ウィンドウ。  
  
## <a name="example"></a>例  
 次のコードは、マウス イベント ハンドラーを設定する方法を示しています、[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]ビジュアル オブジェクトのホスト コンテナーとして使用されるウィンドウ。  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 次の例では、特定のマウス イベントをトラップするへの応答でヒット テストを設定する方法を示します。  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <xref:System.Windows.Interop.HwndSource>オブジェクトが表して[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]内でコンテンツを[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]ウィンドウ。 値、<xref:System.Windows.Interop.HwndSource.RootVisual%2A>のプロパティ、<xref:System.Windows.Interop.HwndSource>オブジェクトは、ビジュアル ツリー階層内の最上位ノードを表します。  
  
 Win32 ホスト コンテナーを使用するオブジェクトのヒット テストの完全なサンプルを参照してください[Win32 の相互運用性サンプルによるヒット テストの](https://go.microsoft.com/fwlink/?LinkID=159995)します。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Interop.HwndSource>  
 [ビジュアル層でのヒット テスト](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [チュートリアル : Win32 アプリケーションでのビジュアル オブジェクトのホスト](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)

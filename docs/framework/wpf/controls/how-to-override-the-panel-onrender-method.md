---
title: '方法: パネルの OnRender メソッドをオーバーライドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: c4539847368c1a5789e99ec92106d17077ed5943
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770839"
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="f1935-102">方法: パネルの OnRender メソッドをオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="f1935-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="f1935-103">この例は、オーバーライドする方法を示します、<xref:System.Windows.Controls.Panel.OnRender%2A>メソッドの<xref:System.Windows.Controls.Panel>レイアウト要素にカスタムのグラフィカルな効果を追加するためにします。</span><span class="sxs-lookup"><span data-stu-id="f1935-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1935-104">例</span><span class="sxs-lookup"><span data-stu-id="f1935-104">Example</span></span>  
 <span data-ttu-id="f1935-105">使用して、<xref:System.Windows.Controls.Panel.OnRender%2A>表示パネル要素にグラフィック効果を追加するにはメソッドです。</span><span class="sxs-lookup"><span data-stu-id="f1935-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="f1935-106">たとえば、このメソッドを使用すると、カスタム境界線や背景の効果を追加します。</span><span class="sxs-lookup"><span data-stu-id="f1935-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="f1935-107">A<xref:System.Windows.Media.DrawingContext>オブジェクトは、図形、テキスト、画像、またはビデオを描画するためのメソッドを提供する引数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="f1935-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="f1935-108">その結果、このメソッドは、パネル オブジェクトのカスタマイズに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f1935-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f1935-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1935-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="f1935-110">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="f1935-110">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="f1935-111">カスタム放射状パネルのサンプル</span><span class="sxs-lookup"><span data-stu-id="f1935-111">Custom Radial Panel Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159982)
- [<span data-ttu-id="f1935-112">方法トピック</span><span class="sxs-lookup"><span data-stu-id="f1935-112">How-to Topics</span></span>](panel-how-to-topics.md)

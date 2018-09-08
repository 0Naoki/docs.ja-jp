---
title: '方法 : 線を描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: bee343676175098493df347823a3bdbdf17b205f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44198622"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="4d758-102">方法 : 線を描画する</span><span class="sxs-lookup"><span data-stu-id="4d758-102">How to: Draw a Line</span></span>
<span data-ttu-id="4d758-103">この例を使用して線を描画する方法を示します、<xref:System.Windows.Shapes.Line>要素。</span><span class="sxs-lookup"><span data-stu-id="4d758-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="4d758-104">線を描画するために作成、<xref:System.Windows.Shapes.Line>要素。</span><span class="sxs-lookup"><span data-stu-id="4d758-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="4d758-105">使用して、その<xref:System.Windows.Shapes.Line.X1%2A>と<xref:System.Windows.Shapes.Line.Y1%2A>; の開始ポイントを設定して使用するプロパティの<xref:System.Windows.Shapes.Line.X2%2A>と<xref:System.Windows.Shapes.Line.Y2%2A>エンドポイントを設定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="4d758-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="4d758-106">最後に、設定、<xref:System.Windows.Shapes.Shape.Stroke%2A>と<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>線なしの行が表示されないためです。</span><span class="sxs-lookup"><span data-stu-id="4d758-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="4d758-107">設定、<xref:System.Windows.Shapes.Shape.Fill%2A>行要素も何も起こりません、行は内部があるないためです。</span><span class="sxs-lookup"><span data-stu-id="4d758-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="4d758-108">次の例は、内で 3 つの行を描画、<xref:System.Windows.Controls.Canvas>要素。</span><span class="sxs-lookup"><span data-stu-id="4d758-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d758-109">例</span><span class="sxs-lookup"><span data-stu-id="4d758-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="4d758-110">この例より大きなサンプルの一部です。サンプル全体については、次を参照してください。 [Shape 要素のサンプル](https://go.microsoft.com/fwlink/?LinkID=160037)します。</span><span class="sxs-lookup"><span data-stu-id="4d758-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d758-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d758-111">See Also</span></span>  
 <xref:System.Windows.Shapes.Line>  
 [<span data-ttu-id="4d758-112">Shape 要素のサンプル</span><span class="sxs-lookup"><span data-stu-id="4d758-112">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)

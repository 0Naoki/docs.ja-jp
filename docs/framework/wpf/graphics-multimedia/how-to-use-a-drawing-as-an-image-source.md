---
title: '方法: 描画をイメージ ソースとして使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: d4b91a6495e1c54400d5fbfe43b6311d908565a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097861"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="7f900-102">方法: 描画をイメージ ソースとして使用する</span><span class="sxs-lookup"><span data-stu-id="7f900-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="7f900-103">この例は、使用する方法を示します、<xref:System.Windows.Media.Drawing>として、<xref:System.Windows.Controls.Image.Source%2A>の<xref:System.Windows.Controls.Image>コントロール。</span><span class="sxs-lookup"><span data-stu-id="7f900-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="7f900-104">表示する、<xref:System.Windows.Media.Drawing>で、<xref:System.Windows.Controls.Image>コントロールを使用して、<xref:System.Windows.Media.DrawingImage>として、<xref:System.Windows.Controls.Image>コントロールの<xref:System.Windows.Controls.Image.Source%2A>設定と、<xref:System.Windows.Media.DrawingImage>オブジェクトの<xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType>プロパティを表示する描画。</span><span class="sxs-lookup"><span data-stu-id="7f900-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f900-105">例</span><span class="sxs-lookup"><span data-stu-id="7f900-105">Example</span></span>  
 <span data-ttu-id="7f900-106">次の例では、<xref:System.Windows.Media.DrawingImage>と<xref:System.Windows.Controls.Image>を表示するコントロールを<xref:System.Windows.Media.GeometryDrawing>します。</span><span class="sxs-lookup"><span data-stu-id="7f900-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="7f900-107">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7f900-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="7f900-108">![2 つの楕円の GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="7f900-108">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="7f900-109">DrawingImage</span><span class="sxs-lookup"><span data-stu-id="7f900-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="7f900-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f900-110">See also</span></span>

- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="7f900-111">ImageDrawing を使用してイメージを描画する</span><span class="sxs-lookup"><span data-stu-id="7f900-111">Draw an Image Using ImageDrawing</span></span>](how-to-draw-an-image-using-imagedrawing.md)
- [<span data-ttu-id="7f900-112">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="7f900-112">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="7f900-113">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="7f900-113">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="7f900-114">PresentationOptions:Freeze 属性</span><span class="sxs-lookup"><span data-stu-id="7f900-114">PresentationOptions:Freeze Attribute</span></span>](../advanced/presentationoptions-freeze-attribute.md)

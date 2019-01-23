---
title: '方法: キャッシュされた要素をブラシとして使用します。'
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: 7ff0e9eb131faaed3874995ee137126eac31f43d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597932"
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="d72a9-102">方法: キャッシュされた要素をブラシとして使用します。</span><span class="sxs-lookup"><span data-stu-id="d72a9-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="d72a9-103">使用して、<xref:System.Windows.Media.BitmapCacheBrush>を効率的にキャッシュされた要素を再利用するクラス。</span><span class="sxs-lookup"><span data-stu-id="d72a9-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="d72a9-104">要素をキャッシュするには、新しいインスタンスを作成、<xref:System.Windows.Media.BitmapCache>クラスし、要素に割り当てる<xref:System.Windows.UIElement.CacheMode%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d72a9-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d72a9-105">例</span><span class="sxs-lookup"><span data-stu-id="d72a9-105">Example</span></span>  
 <span data-ttu-id="d72a9-106">次のコード例では、キャッシュされた要素を再利用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d72a9-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="d72a9-107">キャッシュされた要素は、<xref:System.Windows.Controls.Image>大きな画像を表示するコントロール。</span><span class="sxs-lookup"><span data-stu-id="d72a9-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="d72a9-108"><xref:System.Windows.Controls.Image>を使用して、コントロールをビットマップとしてキャッシュ、<xref:System.Windows.Media.BitmapCache>クラス、さらに、キャッシュに割り当てることで再利用、<xref:System.Windows.Media.BitmapCacheBrush>します。</span><span class="sxs-lookup"><span data-stu-id="d72a9-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="d72a9-109">ブラシは、効率的に再利用を表示する、25 個のボタンの背景に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d72a9-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="d72a9-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="d72a9-110">See also</span></span>
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="d72a9-111">方法: 要素をキャッシュしてレンダリングのパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="d72a9-111">How to: Improve Rendering Performance by Caching an Element</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)

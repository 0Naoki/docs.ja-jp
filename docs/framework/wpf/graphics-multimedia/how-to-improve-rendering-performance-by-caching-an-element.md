---
title: '方法: 要素をキャッシュしてレンダリングのパフォーマンスを向上させる'
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: 79f427198be370d9cb48cab429906202a62bb72d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647578"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="919d6-102">方法: 要素をキャッシュしてレンダリングのパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="919d6-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="919d6-103">使用して、 <xref:System.Windows.Media.BitmapCache> 、複雑なのレンダリング パフォーマンスを向上させるためにクラス<xref:System.Windows.UIElement>します。</span><span class="sxs-lookup"><span data-stu-id="919d6-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="919d6-104">要素をキャッシュするには、新しいインスタンスを作成、<xref:System.Windows.Media.BitmapCache>クラスし、要素に割り当てる<xref:System.Windows.UIElement.CacheMode%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="919d6-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="919d6-105">再利用することができます、<xref:System.Windows.Media.BitmapCache>で効率的に、<xref:System.Windows.Media.BitmapCacheBrush>します。</span><span class="sxs-lookup"><span data-stu-id="919d6-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="919d6-106">例</span><span class="sxs-lookup"><span data-stu-id="919d6-106">Example</span></span>  
 <span data-ttu-id="919d6-107">次のコード例では、複合型の要素を作成して、要素がアニメーション化されるときにパフォーマンスが向上ビットマップとしてキャッシュする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="919d6-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="919d6-108">要素は、図形のジオメトリの頂点の数を保持するキャンバスです。</span><span class="sxs-lookup"><span data-stu-id="919d6-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="919d6-109">A<xref:System.Windows.Media.BitmapCache>に割り当てられている値、既定値は、<xref:System.Windows.UIElement.CacheMode%2A>キャンバスのし、キャッシュされたビットマップのスムーズな拡張、アニメーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="919d6-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="919d6-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="919d6-110">See also</span></span>
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="919d6-111">方法: キャッシュされた要素をブラシとして使用します。</span><span class="sxs-lookup"><span data-stu-id="919d6-111">How to: Use a Cached Element as a Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)

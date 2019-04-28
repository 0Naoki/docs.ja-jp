---
title: '方法: 3-D モデルのスケールを変換する'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: 6d668de08201d819ce9f8752bedf6c388a6bc718
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769331"
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a><span data-ttu-id="87d13-102">方法: 3-D モデルのスケールを変換する</span><span class="sxs-lookup"><span data-stu-id="87d13-102">How to: Transform the Scale of a 3-D Model</span></span>
<span data-ttu-id="87d13-103">この例では、3-D オブジェクトをスケーリングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="87d13-103">This example shows how to scale a 3-D object.</span></span> <span data-ttu-id="87d13-104">3-D オブジェクトのスケーリングを使用して、<xref:System.Windows.Media.Media3D.ScaleTransform3D>します。</span><span class="sxs-lookup"><span data-stu-id="87d13-104">To scale a 3-D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="87d13-105"><xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>、 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>、および<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A>プロパティを指定する係数を使用して、要素のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="87d13-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="87d13-106">たとえば、 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> 1.5 の値が元の幅の 150 パーセントにオブジェクトを拡大します。</span><span class="sxs-lookup"><span data-stu-id="87d13-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="87d13-107">A<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>値 0.5 は 50% オブジェクトの高さを縮小します。</span><span class="sxs-lookup"><span data-stu-id="87d13-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="87d13-108">次のコードを使用して、<xref:System.Windows.Media.Media3D.ScaleTransform3D>の変換として、<xref:System.Windows.Media.Media3D.GeometryModel3D>します。</span><span class="sxs-lookup"><span data-stu-id="87d13-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="87d13-109">例</span><span class="sxs-lookup"><span data-stu-id="87d13-109">Example</span></span>  
 <span data-ttu-id="87d13-110">次のコードでは、全体のサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="87d13-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="87d13-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="87d13-111">See also</span></span>

- [<span data-ttu-id="87d13-112">3-D 変換をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="87d13-112">Animate 3-D Translations</span></span>](how-to-animate-3-d-translations.md)
- [<span data-ttu-id="87d13-113">3-D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="87d13-113">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="87d13-114">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="87d13-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)

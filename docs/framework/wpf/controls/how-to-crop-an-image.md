---
title: '方法 : イメージをトリミングする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: 189cb92d581ccc9209ebdb4de18487951d17818a
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44077786"
---
# <a name="how-to-crop-an-image"></a><span data-ttu-id="cffd5-102">方法 : イメージをトリミングする</span><span class="sxs-lookup"><span data-stu-id="cffd5-102">How to: Crop an Image</span></span>
<span data-ttu-id="cffd5-103">この例を使用して、イメージをトリミングする方法を示しています。<xref:System.Windows.Media.Imaging.CroppedBitmap>します。</span><span class="sxs-lookup"><span data-stu-id="cffd5-103">This example shows how to crop an image using <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span></span>  
  
 <span data-ttu-id="cffd5-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> 主に使用トリミング後のバージョンのイメージをエンコードする際にファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="cffd5-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> is primarily used when encoding a cropped version of an image to save out to a file.</span></span> <span data-ttu-id="cffd5-105">表示目的でを参照してください。 イメージをトリミングするには、[クリップ領域を作成する](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376)トピック。</span><span class="sxs-lookup"><span data-stu-id="cffd5-105">To crop an image for display purposes see the [Create a Clip Region](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cffd5-106">例</span><span class="sxs-lookup"><span data-stu-id="cffd5-106">Example</span></span>  
 <span data-ttu-id="cffd5-107">次[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]以下のサンプル内で使用されるリソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="cffd5-107">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] defines resources used within the samples below.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 <span data-ttu-id="cffd5-108">次の例を使用して、イメージを作成、<xref:System.Windows.Media.Imaging.CroppedBitmap>のソースとして。</span><span class="sxs-lookup"><span data-stu-id="cffd5-108">The following example creates an image using a <xref:System.Windows.Media.Imaging.CroppedBitmap> as its source.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <span data-ttu-id="cffd5-109"><xref:System.Windows.Media.Imaging.CroppedBitmap>別のソースとしても使用できます<xref:System.Windows.Media.Imaging.CroppedBitmap>、トリミングの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="cffd5-109">The <xref:System.Windows.Media.Imaging.CroppedBitmap> can also be used as the source of another <xref:System.Windows.Media.Imaging.CroppedBitmap>, chaining the cropping.</span></span> <span data-ttu-id="cffd5-110">なお、<xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A>値は、トリミング ビットマップと初期イメージではなくソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="cffd5-110">Note that the <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> uses values that are relative to the source cropped bitmap and not the initial image.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a><span data-ttu-id="cffd5-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="cffd5-111">See Also</span></span>  
 [<span data-ttu-id="cffd5-112">クリップ領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="cffd5-112">Create a Clip Region</span></span>](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376)

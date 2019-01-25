---
title: '方法: 画質を制御する補間モードを使用してスケーリング時'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: 0c295411418dabac74626c3c4ab43fb8210bbfa4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631426"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a><span data-ttu-id="c29b2-102">方法: 画質を制御する補間モードを使用してスケーリング時</span><span class="sxs-lookup"><span data-stu-id="c29b2-102">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>
<span data-ttu-id="c29b2-103">補間モードを<xref:System.Drawing.Graphics>オブジェクト方法に影響を与えます[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]スケール (拡大および縮小) イメージ。</span><span class="sxs-lookup"><span data-stu-id="c29b2-103">The interpolation mode of a <xref:System.Drawing.Graphics> object influences the way [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] scales (stretches and shrinks) images.</span></span> <span data-ttu-id="c29b2-104"><xref:System.Drawing.Drawing2D.InterpolationMode>列挙型は、次のリストに表示される一部のいくつかの補間モードを定義します。</span><span class="sxs-lookup"><span data-stu-id="c29b2-104">The <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration defines several interpolation modes, some of which are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 <span data-ttu-id="c29b2-105">イメージを拡大するには、元のイメージ内の各ピクセルは大きいイメージのピクセルのグループにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29b2-105">To stretch an image, each pixel in the original image must be mapped to a group of pixels in the larger image.</span></span> <span data-ttu-id="c29b2-106">イメージを縮小するには、小さいイメージの 1 つのピクセルに、元のイメージのピクセルのグループをマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29b2-106">To shrink an image, groups of pixels in the original image must be mapped to single pixels in the smaller image.</span></span> <span data-ttu-id="c29b2-107">これらのマッピングを実行するアルゴリズムの効果は、スケーリングされたイメージの品質を決定します。</span><span class="sxs-lookup"><span data-stu-id="c29b2-107">The effectiveness of the algorithms that perform these mappings determines the quality of a scaled image.</span></span> <span data-ttu-id="c29b2-108">高品質な拡大縮小されたイメージを生成するアルゴリズムは、処理時間を必要とする傾向があります。</span><span class="sxs-lookup"><span data-stu-id="c29b2-108">Algorithms that produce higher-quality scaled images tend to require more processing time.</span></span> <span data-ttu-id="c29b2-109">上記の一覧で<xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>最低の品質のモードと<xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>は最高品質のモードです。</span><span class="sxs-lookup"><span data-stu-id="c29b2-109">In the preceding list, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> is the lowest-quality mode and <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> is the highest-quality mode.</span></span>  
  
 <span data-ttu-id="c29b2-110">補間モードを設定するには、メンバーのいずれかを割り当てる、<xref:System.Drawing.Drawing2D.InterpolationMode>列挙体を<xref:System.Drawing.Graphics.InterpolationMode%2A>のプロパティを<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c29b2-110">To set the interpolation mode, assign one of the members of the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to the <xref:System.Drawing.Graphics.InterpolationMode%2A> property of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c29b2-111">例</span><span class="sxs-lookup"><span data-stu-id="c29b2-111">Example</span></span>  
 <span data-ttu-id="c29b2-112">次の例では、イメージを描画し、3 つの異なる補間モードを使用してイメージが圧縮されます。</span><span class="sxs-lookup"><span data-stu-id="c29b2-112">The following example draws an image and then shrinks the image with three different interpolation modes.</span></span>  
  
 <span data-ttu-id="c29b2-113">次の図は、元のイメージと 3 つの小さいイメージを示します。</span><span class="sxs-lookup"><span data-stu-id="c29b2-113">The following illustration shows the original image and the three smaller images.</span></span>  
  
 <span data-ttu-id="c29b2-114">![さまざまな補間設定を持つイメージ](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")</span><span class="sxs-lookup"><span data-stu-id="c29b2-114">![Image with Varied Interpolation Settings](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c29b2-115">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="c29b2-115">Compiling the Code</span></span>  
 <span data-ttu-id="c29b2-116">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="c29b2-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c29b2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c29b2-117">See also</span></span>
- [<span data-ttu-id="c29b2-118">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="c29b2-118">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="c29b2-119">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="c29b2-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)

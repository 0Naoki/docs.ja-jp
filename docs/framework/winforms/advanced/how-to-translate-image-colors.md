---
title: '方法: イメージの色を変換します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 81aecddb28903649ff2d59e80fc90368df5e2db4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703024"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="c057b-102">方法: イメージの色を変換します。</span><span class="sxs-lookup"><span data-stu-id="c057b-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="c057b-103">翻訳は、4 つの色コンポーネントの 1 つ以上の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="c057b-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="c057b-104">翻訳を表すカラー マトリックス エントリは、次の表に付与されます。</span><span class="sxs-lookup"><span data-stu-id="c057b-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="c057b-105">コンポーネントを変換します。</span><span class="sxs-lookup"><span data-stu-id="c057b-105">Component to be translated</span></span>|<span data-ttu-id="c057b-106">マトリックスのエントリ</span><span class="sxs-lookup"><span data-stu-id="c057b-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="c057b-107">赤</span><span class="sxs-lookup"><span data-stu-id="c057b-107">Red</span></span>|<span data-ttu-id="c057b-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="c057b-108">[4][0]</span></span>|  
|<span data-ttu-id="c057b-109">緑</span><span class="sxs-lookup"><span data-stu-id="c057b-109">Green</span></span>|<span data-ttu-id="c057b-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="c057b-110">[4][1]</span></span>|  
|<span data-ttu-id="c057b-111">青</span><span class="sxs-lookup"><span data-stu-id="c057b-111">Blue</span></span>|<span data-ttu-id="c057b-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="c057b-112">[4][2]</span></span>|  
|<span data-ttu-id="c057b-113">[アルファ]</span><span class="sxs-lookup"><span data-stu-id="c057b-113">Alpha</span></span>|<span data-ttu-id="c057b-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="c057b-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c057b-115">例</span><span class="sxs-lookup"><span data-stu-id="c057b-115">Example</span></span>  
 <span data-ttu-id="c057b-116">次の例では、構築、 <xref:System.Drawing.Image> ColorBars.bmp ファイルからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c057b-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="c057b-117">コードでは、イメージ内の各ピクセルの赤の要素を 0.75 を追加します。</span><span class="sxs-lookup"><span data-stu-id="c057b-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="c057b-118">変換後のイメージと共に、元のイメージが描画されます。</span><span class="sxs-lookup"><span data-stu-id="c057b-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="c057b-119">次の図は、右側の左側に、元のイメージと変換後のイメージを示します。</span><span class="sxs-lookup"><span data-stu-id="c057b-119">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="c057b-120">![色を変換](./media/colortrans2.png "colortrans2")</span><span class="sxs-lookup"><span data-stu-id="c057b-120">![Translate Colors](./media/colortrans2.png "colortrans2")</span></span>  
  
 <span data-ttu-id="c057b-121">次の表は、赤の平行移動の前後に 4 つのバーの色のベクターを示します。</span><span class="sxs-lookup"><span data-stu-id="c057b-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="c057b-122">色コンポーネントの最大値が 1 であるため、2 行目に赤のコンポーネントが変更されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c057b-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="c057b-123">(同様に、色コンポーネントの最小値は 0 です。)</span><span class="sxs-lookup"><span data-stu-id="c057b-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="c057b-124">元</span><span class="sxs-lookup"><span data-stu-id="c057b-124">Original</span></span>|<span data-ttu-id="c057b-125">翻訳先</span><span class="sxs-lookup"><span data-stu-id="c057b-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="c057b-126">黒 (0、0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="c057b-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="c057b-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="c057b-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="c057b-128">赤 (1, 0、0, 1)</span><span class="sxs-lookup"><span data-stu-id="c057b-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="c057b-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="c057b-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="c057b-130">緑 (0, 1、0, 1)</span><span class="sxs-lookup"><span data-stu-id="c057b-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="c057b-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="c057b-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="c057b-132">青 (0, 0、1, 1)</span><span class="sxs-lookup"><span data-stu-id="c057b-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="c057b-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="c057b-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c057b-134">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="c057b-134">Compiling the Code</span></span>  
 <span data-ttu-id="c057b-135">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> イベント ハンドラーのパラメーターである `e`<xref:System.Windows.Forms.Control.Paint> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="c057b-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="c057b-136">置換`ColorBars.bmp`イメージ ファイル名と、システムで有効なパス。</span><span class="sxs-lookup"><span data-stu-id="c057b-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c057b-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="c057b-137">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="c057b-138">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="c057b-138">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="c057b-139">イメージの色の変更</span><span class="sxs-lookup"><span data-stu-id="c057b-139">Recoloring Images</span></span>](recoloring-images.md)

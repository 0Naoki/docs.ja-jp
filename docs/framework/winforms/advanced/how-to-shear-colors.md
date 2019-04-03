---
title: '方法: 色を傾斜する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: bb5f9043ea5bdd25e984d73d3640c80f599714e6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826393"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="06621-102">方法: 色を傾斜する</span><span class="sxs-lookup"><span data-stu-id="06621-102">How to: Shear Colors</span></span>
<span data-ttu-id="06621-103">傾斜増加またはカラー コンポーネントを別の色コンポーネントに比例した量ずつ減少します。</span><span class="sxs-lookup"><span data-stu-id="06621-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="06621-104">たとえば、赤のコンポーネントを増加して青のコンポーネントの値の半分して変換を検討してください。</span><span class="sxs-lookup"><span data-stu-id="06621-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="06621-105">このような変換では、(0.2, 0.5, 1) の色になります (0.7, 0.5, 1)。</span><span class="sxs-lookup"><span data-stu-id="06621-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="06621-106">新しいの赤のコンポーネントが 0.2 + (1/2)(1) 0.7 を = です。</span><span class="sxs-lookup"><span data-stu-id="06621-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06621-107">例</span><span class="sxs-lookup"><span data-stu-id="06621-107">Example</span></span>  
 <span data-ttu-id="06621-108">次の例では、構築、 <xref:System.Drawing.Image> ColorBars4.bmp ファイルからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="06621-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="06621-109">コードは、イメージ内の各ピクセルに前の段落で説明されている傾斜変換を適用します。</span><span class="sxs-lookup"><span data-stu-id="06621-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="06621-110">次の図は、右側の左側に、元のイメージと傾斜のイメージを示します。</span><span class="sxs-lookup"><span data-stu-id="06621-110">The following illustration shows the original image on the left and the sheared image on the right:</span></span> 
  
 ![カラー ストライプ化 - サイド示す元のイメージと傾斜のイメージを 2 マスします。](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 <span data-ttu-id="06621-112">次の表は、傾斜変換の前後に 4 つのバーの色のベクターを示します。</span><span class="sxs-lookup"><span data-stu-id="06621-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="06621-113">元</span><span class="sxs-lookup"><span data-stu-id="06621-113">Original</span></span>|<span data-ttu-id="06621-114">傾斜</span><span class="sxs-lookup"><span data-stu-id="06621-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="06621-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="06621-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="06621-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="06621-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="06621-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="06621-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="06621-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="06621-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="06621-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="06621-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="06621-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="06621-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="06621-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="06621-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="06621-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="06621-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="06621-123">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="06621-123">Compiling the Code</span></span>  
 <span data-ttu-id="06621-124">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> イベント ハンドラーのパラメーターである `e`<xref:System.Windows.Forms.Control.Paint> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="06621-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="06621-125">置換`ColorBars.bmp`イメージ名とパス、システムでは無効です。</span><span class="sxs-lookup"><span data-stu-id="06621-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06621-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="06621-126">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="06621-127">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="06621-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="06621-128">イメージの色の変更</span><span class="sxs-lookup"><span data-stu-id="06621-128">Recoloring Images</span></span>](recoloring-images.md)

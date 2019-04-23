---
title: '方法: 不透明な直線および半透明な直線を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- transparency [Windows Forms], lines
- lines [Windows Forms], drawing alpha blended
- alpha blending [Windows Forms], drawing lines
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
ms.openlocfilehash: 7408722dc13e83828cfca3f0615a2730e3c53461
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188267"
---
# <a name="how-to-draw-opaque-and-semitransparent-lines"></a><span data-ttu-id="a0630-102">方法: 不透明な直線および半透明な直線を描画する</span><span class="sxs-lookup"><span data-stu-id="a0630-102">How to: Draw Opaque and Semitransparent Lines</span></span>
<span data-ttu-id="a0630-103">線を描画するときは、<xref:System.Drawing.Pen> オブジェクトを <xref:System.Drawing.Graphics> クラスの <xref:System.Drawing.Graphics.DrawLine%2A> メソッドに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0630-103">When you draw a line, you must pass a <xref:System.Drawing.Pen> object to the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="a0630-104"><xref:System.Drawing.Pen.%23ctor%2A> コンストラクターのパラメーターの 1 つは、<xref:System.Drawing.Color> オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="a0630-104">One of the parameters of the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="a0630-105">不透明な直線を描画するには、色のアルファ コンポーネントを 255 に設定します。</span><span class="sxs-lookup"><span data-stu-id="a0630-105">To draw an opaque line, set the alpha component of the color to 255.</span></span> <span data-ttu-id="a0630-106">半透明な直線を描画するには、アルファ コンポーネントを 1 ～ 254 の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="a0630-106">To draw a semitransparent line, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="a0630-107">半透明な直線を背景の上に描画するとき、線の色は、背景の色とブレンドされます。</span><span class="sxs-lookup"><span data-stu-id="a0630-107">When you draw a semitransparent line over a background, the color of the line is blended with the colors of the background.</span></span> <span data-ttu-id="a0630-108">アルファ コンポーネントは、線と背景色が混在する方法を指定します。0 に近いのアルファ値は、背景色の比重が高く、255 に近いアルファ値は、線の色の比重が高くなります。</span><span class="sxs-lookup"><span data-stu-id="a0630-108">The alpha component specifies how the line and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the line color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0630-109">例</span><span class="sxs-lookup"><span data-stu-id="a0630-109">Example</span></span>  
 <span data-ttu-id="a0630-110">次の例では、ビットマップを描画し、ビットマップを背景として使用する 3 つの線が描画されます。</span><span class="sxs-lookup"><span data-stu-id="a0630-110">The following example draws a bitmap and then draws three lines that use the bitmap as a background.</span></span> <span data-ttu-id="a0630-111">最初の線はアルファ コンポーネントに 255 を使用するので、不透明です。</span><span class="sxs-lookup"><span data-stu-id="a0630-111">The first line uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="a0630-112">2 番目と 3 番目の線は、アルファ コンポーネントに 128 を使用するので、線から背景画像を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a0630-112">The second and third lines use an alpha component of 128, so they are semitransparent; you can see the background image through the lines.</span></span> <span data-ttu-id="a0630-113"><xref:System.Drawing.Graphics.CompositingQuality%2A> プロパティを設定するステートメントにより、3 番目の線がのブレンドがガンマ補正と組み合わせて実行されます。</span><span class="sxs-lookup"><span data-stu-id="a0630-113">The statement that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third line to be done in conjunction with gamma correction.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
 <span data-ttu-id="a0630-114">次の図は、次のコードの出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="a0630-114">The following illustration shows the output of the following code:</span></span>  
  
 ![不透明な直線および半透明な出力を示す図](./media/how-to-draw-opaque-and-semitransparent-lines/opaque-semitransparent-lines.png)  

## <a name="compiling-the-code"></a><span data-ttu-id="a0630-116">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="a0630-116">Compiling the Code</span></span>  
 <span data-ttu-id="a0630-117">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> イベント ハンドラーのパラメーターである `e`<xref:System.Windows.Forms.Control.Paint> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="a0630-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0630-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0630-118">See also</span></span>

- [<span data-ttu-id="a0630-119">アルファ ブレンドの直線と塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="a0630-119">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="a0630-120">方法: コントロールに透明な背景を提供します。</span><span class="sxs-lookup"><span data-stu-id="a0630-120">How to: Give Your Control a Transparent Background</span></span>](../controls/how-to-give-your-control-a-transparent-background.md)
- [<span data-ttu-id="a0630-121">方法: 不透明な直線および半透明ブラシを使用して描画します。</span><span class="sxs-lookup"><span data-stu-id="a0630-121">How to: Draw with Opaque and Semitransparent Brushes</span></span>](how-to-draw-with-opaque-and-semitransparent-brushes.md)

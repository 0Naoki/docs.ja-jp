---
title: '方法: ペンを使用して線を描画するには'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: 3af91611eef4b97dc3461ad8cd7e36c7aa10a16f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713368"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a><span data-ttu-id="2a5e0-102">方法: ペンを使用して線を描画するには</span><span class="sxs-lookup"><span data-stu-id="2a5e0-102">How to: Use a Pen to Draw Lines</span></span>
<span data-ttu-id="2a5e0-103">線を描画する必要があります、<xref:System.Drawing.Graphics>オブジェクトと<xref:System.Drawing.Pen>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2a5e0-103">To draw lines, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="2a5e0-104"><xref:System.Drawing.Graphics>オブジェクトを提供、<xref:System.Drawing.Graphics.DrawLine%2A>メソッド、および<xref:System.Drawing.Pen>オブジェクトは、線、色や幅などの機能を格納します。</span><span class="sxs-lookup"><span data-stu-id="2a5e0-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawLine%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a5e0-105">例</span><span class="sxs-lookup"><span data-stu-id="2a5e0-105">Example</span></span>  
 <span data-ttu-id="2a5e0-106">次の例から線を描画します (20, 10) に (300, 100)。</span><span class="sxs-lookup"><span data-stu-id="2a5e0-106">The following example draws a line from (20, 10) to (300, 100).</span></span> <span data-ttu-id="2a5e0-107">最初のステートメントを使用して、<xref:System.Drawing.Pen.%23ctor%2A>黒のペンを作成するクラスのコンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="2a5e0-107">The first statement uses the <xref:System.Drawing.Pen.%23ctor%2A> class constructor to create a black pen.</span></span> <span data-ttu-id="2a5e0-108">渡される 1 つの引数、<xref:System.Drawing.Pen.%23ctor%2A>コンス トラクターは、<xref:System.Drawing.Color>オブジェクトを作成した、<xref:System.Drawing.Color.FromArgb%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="2a5e0-108">The one argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object created with the <xref:System.Drawing.Color.FromArgb%2A> method.</span></span> <span data-ttu-id="2a5e0-109">作成に使用される値、<xref:System.Drawing.Color>オブジェクト-(255, 0、0, 0): 色のアルファ、赤、緑、および青のコンポーネントに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2a5e0-109">The values used to create the <xref:System.Drawing.Color> object — (255, 0, 0, 0) — correspond to the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="2a5e0-110">これらの値は、不透明な黒のペンを定義します。</span><span class="sxs-lookup"><span data-stu-id="2a5e0-110">These values define an opaque black pen.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2a5e0-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="2a5e0-111">Compiling the Code</span></span>  
 <span data-ttu-id="2a5e0-112">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> イベント ハンドラーのパラメーターである `e`<xref:System.Windows.Forms.Control.Paint> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="2a5e0-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a5e0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a5e0-113">See also</span></span>
- <xref:System.Drawing.Pen>
- [<span data-ttu-id="2a5e0-114">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="2a5e0-114">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="2a5e0-115">GDI+ でのペン、直線、および四角形</span><span class="sxs-lookup"><span data-stu-id="2a5e0-115">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)

---
title: '方法: 結合線'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: a43cfb8a51435aa0c5c3f7aae673d38d3f7792ab
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410876"
---
# <a name="how-to-join-lines"></a><span data-ttu-id="538b1-102">方法: 結合線</span><span class="sxs-lookup"><span data-stu-id="538b1-102">How to: Join Lines</span></span>
<span data-ttu-id="538b1-103">直線の接合部は、2 つの行の端を満たすまたはオーバー ラップによって構成される一般的な領域です。</span><span class="sxs-lookup"><span data-stu-id="538b1-103">A line join is the common area that is formed by two lines whose ends meet or overlap.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="538b1-104">次の 3 つの行の結合スタイルを提供します。 マイタ、傾斜、およびラウンドします。</span><span class="sxs-lookup"><span data-stu-id="538b1-104">provides three line join styles: miter, bevel, and round.</span></span> <span data-ttu-id="538b1-105">直線の接合スタイルのプロパティである、<xref:System.Drawing.Pen>クラス。</span><span class="sxs-lookup"><span data-stu-id="538b1-105">Line join style is a property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="538b1-106">直線の接合スタイルを指定すると、<xref:System.Drawing.Pen>オブジェクトのいずれかで接続されているすべての行を結合スタイルが適用されること<xref:System.Drawing.Drawing2D.GraphicsPath>オブジェクトがそのペンを使用して描画します。</span><span class="sxs-lookup"><span data-stu-id="538b1-106">When you specify a line join style for a <xref:System.Drawing.Pen> object, that join style will be applied to all the connected lines in any <xref:System.Drawing.Drawing2D.GraphicsPath> object drawn using that pen.</span></span>  
  
 <span data-ttu-id="538b1-107">次の図は、直線のベベル結合の結果を示します。</span><span class="sxs-lookup"><span data-stu-id="538b1-107">The following illustration shows the results of the beveled line join example.</span></span>  
  
 ![結合線を示す図。](./media/how-to-join-lines/joined-beveled-lines.gif)  
  
## <a name="example"></a><span data-ttu-id="538b1-109">例</span><span class="sxs-lookup"><span data-stu-id="538b1-109">Example</span></span>  
 <span data-ttu-id="538b1-110">使用して直線の接合スタイルを指定することができます、<xref:System.Drawing.Pen.LineJoin%2A>のプロパティ、<xref:System.Drawing.Pen>クラス。</span><span class="sxs-lookup"><span data-stu-id="538b1-110">You can specify the line join style by using the <xref:System.Drawing.Pen.LineJoin%2A> property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="538b1-111">この例では、水平線と垂直線の間の直線の面取り結合を示します。</span><span class="sxs-lookup"><span data-stu-id="538b1-111">The example demonstrates a beveled line join between a horizontal line and a vertical line.</span></span> <span data-ttu-id="538b1-112">次のコードでは、値で<xref:System.Drawing.Drawing2D.LineJoin.Bevel>に割り当てられている、<xref:System.Drawing.Pen.LineJoin%2A>プロパティのメンバーである、<xref:System.Drawing.Drawing2D.LineJoin>列挙体。</span><span class="sxs-lookup"><span data-stu-id="538b1-112">In the following code, the value <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assigned to the <xref:System.Drawing.Pen.LineJoin%2A> property is a member of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration.</span></span> <span data-ttu-id="538b1-113">他のメンバー、<xref:System.Drawing.Drawing2D.LineJoin>列挙体は<xref:System.Drawing.Drawing2D.LineJoin.Miter>と<xref:System.Drawing.Drawing2D.LineJoin.Round>します。</span><span class="sxs-lookup"><span data-stu-id="538b1-113">The other members of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration are <xref:System.Drawing.Drawing2D.LineJoin.Miter> and <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="538b1-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="538b1-114">Compiling the Code</span></span>  
 <span data-ttu-id="538b1-115">前の例は、Windows フォームで使用するために設計されています。 また必要が<xref:System.Windows.Forms.PaintEventArgs> `e`、はのパラメーター、<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="538b1-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="538b1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="538b1-116">See also</span></span>
- [<span data-ttu-id="538b1-117">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="538b1-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)

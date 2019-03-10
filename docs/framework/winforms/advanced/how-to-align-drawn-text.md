---
title: '方法: 描画するテキストを揃える'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: ab97ab713067af26455fa4261bbddaf900ec91b8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725260"
---
# <a name="how-to-align-drawn-text"></a><span data-ttu-id="6135b-102">方法: 描画するテキストを揃える</span><span class="sxs-lookup"><span data-stu-id="6135b-102">How to: Align Drawn Text</span></span>
<span data-ttu-id="6135b-103">カスタム描画を実行するときに、フォームやコントロールを描画するテキストを中央揃えにすることがあります多くの場合。</span><span class="sxs-lookup"><span data-stu-id="6135b-103">When you perform custom drawing, you may often want to center drawn text on a form or control.</span></span> <span data-ttu-id="6135b-104">描画されるテキストを簡単に合わせることができます、<xref:System.Drawing.Graphics.DrawString%2A>または<xref:System.Windows.Forms.TextRenderer.DrawText%2A>メソッドを正しく書式設定オブジェクトを作成し、適切な書式指定フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="6135b-104">You can easily align text drawn with the <xref:System.Drawing.Graphics.DrawString%2A> or <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods by creating the correct formatting object and setting the appropriate format flags.</span></span>  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a><span data-ttu-id="6135b-105">描画するために、GDI + (DrawString) を使用してテキストを中央揃え</span><span class="sxs-lookup"><span data-stu-id="6135b-105">To draw centered text with GDI+ (DrawString)</span></span>  
  
1.  <span data-ttu-id="6135b-106">使用して、<xref:System.Drawing.StringFormat>と適切な<xref:System.Drawing.Graphics.DrawString%2A>中央揃えのテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="6135b-106">Use a <xref:System.Drawing.StringFormat> with the appropriate <xref:System.Drawing.Graphics.DrawString%2A> method to specify centered text.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a><span data-ttu-id="6135b-107">描画するために、GDI (DrawText) を使用してテキストを中央揃え</span><span class="sxs-lookup"><span data-stu-id="6135b-107">To draw centered text with GDI (DrawText)</span></span>  
  
1.  <span data-ttu-id="6135b-108">使用して、<xref:System.Windows.Forms.TextFormatFlags>列挙体の垂直方向および水平方向には、適切なテキストを中央揃えするほかの折り返し<xref:System.Windows.Forms.TextRenderer.DrawText%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="6135b-108">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration for wrapping as well as vertically and horizontally centering text with the appropriate <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6135b-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="6135b-109">Compiling the Code</span></span>  
 <span data-ttu-id="6135b-110">上記のコード例は、Windows フォームで使用するために設計されていて、必要な<xref:System.Windows.Forms.PaintEventArgs>`e`はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="6135b-110">The preceding code examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6135b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="6135b-111">See also</span></span>
- [<span data-ttu-id="6135b-112">方法: GDI を使用してテキストを描画します。</span><span class="sxs-lookup"><span data-stu-id="6135b-112">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="6135b-113">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="6135b-113">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="6135b-114">方法: フォント ファミリとフォントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6135b-114">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)

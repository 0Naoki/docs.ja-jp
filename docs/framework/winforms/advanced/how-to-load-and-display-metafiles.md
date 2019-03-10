---
title: '方法: ロード テストと表示のメタファイル'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 121f285a95d0169db79bdc302d80dba03b3b40c2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720044"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="30438-102">方法: ロード テストと表示のメタファイル</span><span class="sxs-lookup"><span data-stu-id="30438-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="30438-103"><xref:System.Drawing.Imaging.Metafile>から継承されるクラス、<xref:System.Drawing.Image>クラス、メソッドの記録、表示、およびベクター イメージの検証を提供します。</span><span class="sxs-lookup"><span data-stu-id="30438-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30438-104">例</span><span class="sxs-lookup"><span data-stu-id="30438-104">Example</span></span>  
 <span data-ttu-id="30438-105">ベクター イメージ (メタファイル) を画面に表示する必要があります、<xref:System.Drawing.Imaging.Metafile>オブジェクトと<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="30438-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="30438-106">名前のファイル (またはストリーム) に渡す、<xref:System.Drawing.Imaging.Metafile>コンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="30438-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="30438-107">作成した後、<xref:System.Drawing.Imaging.Metafile>オブジェクトを渡す<xref:System.Drawing.Imaging.Metafile>オブジェクトを<xref:System.Drawing.Graphics.DrawImage%2A>のメソッドを<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="30438-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="30438-108">例は、作成、 <xref:System.Drawing.Imaging.Metafile> EMF (メタファイル) ファイルからオブジェクトとで、左上隅のイメージが描画されます (60, 10)。</span><span class="sxs-lookup"><span data-stu-id="30438-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="30438-109">次の図は、指定した位置に描画するメタファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="30438-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="30438-110">![イメージの位置](./media/imageposition2.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="30438-110">![Image Position](./media/imageposition2.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="30438-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="30438-111">Compiling the Code</span></span>  
 <span data-ttu-id="30438-112">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="30438-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30438-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="30438-113">See also</span></span>
- [<span data-ttu-id="30438-114">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="30438-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)

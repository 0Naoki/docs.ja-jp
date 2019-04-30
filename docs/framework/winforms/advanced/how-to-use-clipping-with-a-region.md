---
title: '方法: 領域でクリッピングを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: cf60b32df805a49f8da2760332dc32e34209f6dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954519"
---
# <a name="how-to-use-clipping-with-a-region"></a><span data-ttu-id="490d5-102">方法: 領域でクリッピングを使用する</span><span class="sxs-lookup"><span data-stu-id="490d5-102">How to: Use Clipping with a Region</span></span>
<span data-ttu-id="490d5-103">プロパティの 1 つ、<xref:System.Drawing.Graphics>クラスは、クリップ領域。</span><span class="sxs-lookup"><span data-stu-id="490d5-103">One of the properties of the <xref:System.Drawing.Graphics> class is the clip region.</span></span> <span data-ttu-id="490d5-104">によって実行するすべての描画を指定した<xref:System.Drawing.Graphics>オブジェクトは、そのクリップ領域に制限<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="490d5-104">All drawing done by a given <xref:System.Drawing.Graphics> object is restricted to the clip region of that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="490d5-105">クリップ領域を設定するには、呼び出すことによって、<xref:System.Drawing.Graphics.SetClip%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="490d5-105">You can set the clip region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="490d5-106">例</span><span class="sxs-lookup"><span data-stu-id="490d5-106">Example</span></span>  
 <span data-ttu-id="490d5-107">次の例では、1 つの多角形で構成されるパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="490d5-107">The following example constructs a path that consists of a single polygon.</span></span> <span data-ttu-id="490d5-108">コードは、そのパスに基づいて、領域を構築します。</span><span class="sxs-lookup"><span data-stu-id="490d5-108">Then the code constructs a region, based on that path.</span></span> <span data-ttu-id="490d5-109">渡されるが、地域、<xref:System.Drawing.Graphics.SetClip%2A>のメソッドを<xref:System.Drawing.Graphics>オブジェクト、および、2 つの文字列を描画します。</span><span class="sxs-lookup"><span data-stu-id="490d5-109">The region is passed to the <xref:System.Drawing.Graphics.SetClip%2A> method of a <xref:System.Drawing.Graphics> object, and then two strings are drawn.</span></span>  
  
 <span data-ttu-id="490d5-110">次の図は、クリップされた文字列を示します。</span><span class="sxs-lookup"><span data-stu-id="490d5-110">The following illustration shows the clipped strings.</span></span>  
  
 <span data-ttu-id="490d5-111">![クリップ](./media/clip1.png "clip1")</span><span class="sxs-lookup"><span data-stu-id="490d5-111">![Clip](./media/clip1.png "clip1")</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="490d5-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="490d5-112">Compiling the Code</span></span>  
 <span data-ttu-id="490d5-113">前の例は、Windows フォームで使用するために設計されています。 また必要が<xref:System.Windows.Forms.PaintEventArgs> `e`、はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="490d5-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="490d5-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="490d5-114">See also</span></span>

- [<span data-ttu-id="490d5-115">GDI+ での領域</span><span class="sxs-lookup"><span data-stu-id="490d5-115">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="490d5-116">領域の使用</span><span class="sxs-lookup"><span data-stu-id="490d5-116">Using Regions</span></span>](using-regions.md)

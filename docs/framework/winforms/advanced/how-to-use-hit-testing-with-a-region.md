---
title: '方法: ヒット テストをリージョンと使用'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 1866810b875063271e206da1fe5d6fc06f7b5de0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564306"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="166e1-102">方法: ヒット テストをリージョンと使用</span><span class="sxs-lookup"><span data-stu-id="166e1-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="166e1-103">ヒット テストの目的では、アイコンやボタンなどの特定のオブジェクトの上にカーソルがかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="166e1-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="166e1-104">例</span><span class="sxs-lookup"><span data-stu-id="166e1-104">Example</span></span>  
 <span data-ttu-id="166e1-105">次の例では、2 つの四角形領域の和集合を形成して十字型の領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="166e1-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="166e1-106">ある変数`point`最新のクリックの位置を保持します。</span><span class="sxs-lookup"><span data-stu-id="166e1-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="166e1-107">コードを調べますかどうか`point`十字型の領域にします。</span><span class="sxs-lookup"><span data-stu-id="166e1-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="166e1-108">ポイントは、リージョン (ヒット) では場合、は、非透過の赤いブラシで領域が入力されます。</span><span class="sxs-lookup"><span data-stu-id="166e1-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="166e1-109">それ以外の場合、領域は、半透明の赤いブラシで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="166e1-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="166e1-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="166e1-110">Compiling the Code</span></span>  
 <span data-ttu-id="166e1-111">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventHandler> のパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="166e1-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="166e1-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="166e1-112">See also</span></span>
- <xref:System.Drawing.Region>
- [<span data-ttu-id="166e1-113">GDI+ での領域</span><span class="sxs-lookup"><span data-stu-id="166e1-113">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)
- [<span data-ttu-id="166e1-114">方法: クリッピング領域を使用します。</span><span class="sxs-lookup"><span data-stu-id="166e1-114">How to: Use Clipping with a Region</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)

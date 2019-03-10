---
title: '方法: マウス ポインターが Toolstripitem を検出します。'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 39173490c31711cca9f26f5f0cb2ab493546dda3
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720814"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="9fcc6-102">方法: マウス ポインターが Toolstripitem を検出します。</span><span class="sxs-lookup"><span data-stu-id="9fcc6-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="9fcc6-103">マウス ポインターが上を検出するために、次の手順を使用して、<xref:System.Windows.Forms.ToolStripItem>します。</span><span class="sxs-lookup"><span data-stu-id="9fcc6-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="9fcc6-104">ポインターが toolstripitem を検出するには</span><span class="sxs-lookup"><span data-stu-id="9fcc6-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
-   <span data-ttu-id="9fcc6-105">使用して、<xref:System.Windows.Forms.ToolStripItem.Selected%2A>をアイテムのプロパティ<xref:System.Windows.Forms.ToolStripItem.CanSelect%2A>は`true`します。</span><span class="sxs-lookup"><span data-stu-id="9fcc6-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="9fcc6-106">これによりを同期することから、<xref:System.Windows.Forms.ToolStripItem.MouseEnter>と<xref:System.Windows.Forms.ToolStripItem.MouseLeave>イベント。</span><span class="sxs-lookup"><span data-stu-id="9fcc6-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fcc6-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="9fcc6-107">See also</span></span>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [<span data-ttu-id="9fcc6-108">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="9fcc6-108">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)

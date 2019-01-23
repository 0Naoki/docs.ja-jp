---
title: '方法: ContextMenuStrip のオープン イベントを処理します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
ms.openlocfilehash: fe4c8fc3d2446b09add7336fa11670ff9ca8fed2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532114"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a><span data-ttu-id="40bf3-102">方法: ContextMenuStrip のオープン イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="40bf3-102">How to: Handle the ContextMenuStrip Opening Event</span></span>
<span data-ttu-id="40bf3-103">動作をカスタマイズすることができます、<xref:System.Windows.Forms.ContextMenuStrip>コントロールを処理することによって、<xref:System.Windows.Forms.ToolStripDropDown.Opening>イベント。</span><span class="sxs-lookup"><span data-stu-id="40bf3-103">You can customize the behavior of your <xref:System.Windows.Forms.ContextMenuStrip> control by handling the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40bf3-104">例</span><span class="sxs-lookup"><span data-stu-id="40bf3-104">Example</span></span>  
 <span data-ttu-id="40bf3-105">次のコード例は、処理する方法を示します、<xref:System.Windows.Forms.ToolStripDropDown.Opening>イベント。</span><span class="sxs-lookup"><span data-stu-id="40bf3-105">The following code example demonstrates how to handle the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span> <span data-ttu-id="40bf3-106">イベント ハンドラーを動的に項目を追加、<xref:System.Windows.Forms.ContextMenuStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="40bf3-106">The event handler adds items dynamically to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="40bf3-107">完全なコード例では、次を参照してください。[方法。ToolStrip の項目を動的に追加](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md)します。</span><span class="sxs-lookup"><span data-stu-id="40bf3-107">For the complete code example, see [How to: Add ToolStrip Items Dynamically](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <span data-ttu-id="40bf3-108">設定、<xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType>プロパティを`true`メニューを開かないようにします。</span><span class="sxs-lookup"><span data-stu-id="40bf3-108">Set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> property to `true` to prevent the menu from opening.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40bf3-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="40bf3-109">See also</span></span>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="40bf3-110">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="40bf3-110">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)

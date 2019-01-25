---
title: '方法: タブ ページにコントロールを追加します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: 42f0be64a6ac050fe8873588263b1faf7e2491a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710184"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a><span data-ttu-id="35b5a-102">方法: タブ ページにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="35b5a-102">How to: Add a Control to a Tab Page</span></span>
<span data-ttu-id="35b5a-103">Windows フォームを使用する<xref:System.Windows.Forms.TabControl>を組織的に他のコントロールを表示します。</span><span class="sxs-lookup"><span data-stu-id="35b5a-103">You can use the Windows Forms <xref:System.Windows.Forms.TabControl> to display other controls in an organized fashion.</span></span> <span data-ttu-id="35b5a-104">次の手順では、最初のタブにボタンを追加する方法を示します。タブ ページのラベルの部分にアイコンを追加する方法の詳細については、次を参照してください。[方法。Windows フォーム TabControl の外観を変更する](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)します。</span><span class="sxs-lookup"><span data-stu-id="35b5a-104">The following procedure shows how to add a button to the first tab. For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
### <a name="to-add-a-control-programmatically"></a><span data-ttu-id="35b5a-105">プログラムでコントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="35b5a-105">To add a control programmatically</span></span>  
  
1.  <span data-ttu-id="35b5a-106">使用して、<xref:System.Windows.Forms.Control.ControlCollection.Add%2A>メソッドによって返されるコレクションの<xref:System.Windows.Forms.Control.Controls%2A>プロパティの<xref:System.Windows.Forms.TabPage>:</span><span class="sxs-lookup"><span data-stu-id="35b5a-106">Use the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.Control.Controls%2A> property of <xref:System.Windows.Forms.TabPage>:</span></span>  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="35b5a-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="35b5a-107">See also</span></span>
- [<span data-ttu-id="35b5a-108">TabControl コントロール</span><span class="sxs-lookup"><span data-stu-id="35b5a-108">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="35b5a-109">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="35b5a-109">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="35b5a-110">方法: Windows フォーム TabControl の外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="35b5a-110">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="35b5a-111">方法: タブ ページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="35b5a-111">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)
- [<span data-ttu-id="35b5a-112">方法: Windows フォーム tabcontrol のタブ追加および削除</span><span class="sxs-lookup"><span data-stu-id="35b5a-112">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)

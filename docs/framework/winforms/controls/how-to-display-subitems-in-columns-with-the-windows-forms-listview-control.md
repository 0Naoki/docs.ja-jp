---
title: '方法: Windows フォーム ListView コントロールの列にサブ項目を表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: 318521cc1377be89ef54706d80c8b2990a6ba1b8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339295"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="00a9f-102">方法: Windows フォーム ListView コントロールの列にサブ項目を表示する</span><span class="sxs-lookup"><span data-stu-id="00a9f-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="00a9f-103">Windows フォーム<xref:System.Windows.Forms.ListView>コントロールは、追加のテキスト、または詳細ビュー内の各アイテムのサブ項目を表示できます。</span><span class="sxs-lookup"><span data-stu-id="00a9f-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="00a9f-104">最初の列には、項目のテキスト、たとえば、従業員数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00a9f-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="00a9f-105">2 番目、3 番目、および後続の列が 2 番目に、最初を表示し、後続の関連するサブ項目。</span><span class="sxs-lookup"><span data-stu-id="00a9f-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="00a9f-106">リスト項目にサブ項目を追加するには</span><span class="sxs-lookup"><span data-stu-id="00a9f-106">To add subitems to a list item</span></span>  
  
1. <span data-ttu-id="00a9f-107">必要なすべての列を追加します。</span><span class="sxs-lookup"><span data-stu-id="00a9f-107">Add any columns needed.</span></span> <span data-ttu-id="00a9f-108">最初の列は、項目の表示されるため<xref:System.Windows.Forms.ListView.Text%2A>プロパティ、サブ項目の数より 1 つ以上の列を必要です。</span><span class="sxs-lookup"><span data-stu-id="00a9f-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="00a9f-109">列を追加する方法の詳細については、次を参照してください。[方法。列を Windows フォーム ListView コントロールを追加する](how-to-add-columns-to-the-windows-forms-listview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="00a9f-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2. <span data-ttu-id="00a9f-110">呼び出す、<xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A>メソッドによって返されるコレクションの<xref:System.Windows.Forms.ListViewItem.SubItems%2A>項目のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="00a9f-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="00a9f-111">次のコード例では、リスト項目の部門と従業員の名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="00a9f-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="00a9f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="00a9f-112">See also</span></span>

- [<span data-ttu-id="00a9f-113">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="00a9f-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="00a9f-114">方法: Windows フォーム ListView コントロールで項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="00a9f-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="00a9f-115">方法: Windows フォーム ListView コントロールに列を追加する</span><span class="sxs-lookup"><span data-stu-id="00a9f-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="00a9f-116">方法: Windows フォーム ListView コントロールのアイコンを表示する</span><span class="sxs-lookup"><span data-stu-id="00a9f-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="00a9f-117">方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加する</span><span class="sxs-lookup"><span data-stu-id="00a9f-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)

---
title: '方法: ToolStrip コントロールにツールヒントを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 884fb75d53e425702cdef46615a16394b835518f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076475"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="f1e7b-102">方法: ToolStrip コントロールにツールヒントを使用する</span><span class="sxs-lookup"><span data-stu-id="f1e7b-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="f1e7b-103">表示することができます、<xref:System.Windows.Forms.ToolTip>の<xref:System.Windows.Forms.ToolStrip>コントロールの設定によってコントロール<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="f1e7b-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="f1e7b-104">ツールヒントを表示するには</span><span class="sxs-lookup"><span data-stu-id="f1e7b-104">To display a ToolTip</span></span>  
  
-   <span data-ttu-id="f1e7b-105">設定、<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>するコントロールのプロパティ`true`します。</span><span class="sxs-lookup"><span data-stu-id="f1e7b-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="f1e7b-106">既定値<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType>は`true`、および既定値の<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType>と<xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType>は`false`します。</span><span class="sxs-lookup"><span data-stu-id="f1e7b-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="f1e7b-107">ツールヒントのテキストをオブジェクトの ToolTipText プロパティを使用するには</span><span class="sxs-lookup"><span data-stu-id="f1e7b-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1.  <span data-ttu-id="f1e7b-108">設定、<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>プロパティをボタンの`true`します。</span><span class="sxs-lookup"><span data-stu-id="f1e7b-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2.  <span data-ttu-id="f1e7b-109">設定、<xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType>プロパティをボタンの`false`します。</span><span class="sxs-lookup"><span data-stu-id="f1e7b-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="f1e7b-110">`AutoToolTip`プロパティは`true`に対して既定で<xref:System.Windows.Forms.ToolStripButton>、 <xref:System.Windows.Forms.ToolStripDropDownButton>、および<xref:System.Windows.Forms.ToolStripSplitButton>します。</span><span class="sxs-lookup"><span data-stu-id="f1e7b-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="f1e7b-111">A<xref:System.Windows.Forms.ToolStripButton>を使用してその`Text`プロパティを<xref:System.Windows.Forms.ToolTip>既定のテキスト。</span><span class="sxs-lookup"><span data-stu-id="f1e7b-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="f1e7b-112">カスタム テキストを表示するこの手順を使用して、<xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>します。</span><span class="sxs-lookup"><span data-stu-id="f1e7b-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1e7b-113">設定した場合<xref:System.Windows.Forms.ToolStripItemDisplayStyle>に<xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>または<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>ボタンのテキストは表示されませんが、ツール ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1e7b-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e7b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1e7b-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="f1e7b-115">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="f1e7b-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)

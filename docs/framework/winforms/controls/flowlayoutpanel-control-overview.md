---
title: FlowLayoutPanel コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
ms.openlocfilehash: 2b08566f4b13ed54bfc0bb83c39777410251dafa
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "56441779"
---
# <a name="flowlayoutpanel-control-overview"></a><span data-ttu-id="6bac0-102">FlowLayoutPanel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="6bac0-102">FlowLayoutPanel Control Overview</span></span>
<span data-ttu-id="6bac0-103">
  <xref:System.Windows.Forms.FlowLayoutPanel> コントロールは、水平または垂直のフローの方向に内容を整列させます。</span><span class="sxs-lookup"><span data-stu-id="6bac0-103">The <xref:System.Windows.Forms.FlowLayoutPanel> control arranges its contents in a horizontal or vertical flow direction.</span></span> <span data-ttu-id="6bac0-104">コントロールの内容をある行から次の行、またはある列から次の列にラップすることができます。</span><span class="sxs-lookup"><span data-stu-id="6bac0-104">You can wrap the control's contents from one row to the next, or from one column to the next.</span></span> <span data-ttu-id="6bac0-105">また、内容をラップする代わりにクリップすることができます。</span><span class="sxs-lookup"><span data-stu-id="6bac0-105">Alternately, you can clip instead of wrap its contents.</span></span>  
  
 <span data-ttu-id="6bac0-106"><xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> プロパティの値を設定して、フローの方向を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6bac0-106">You can specify the flow direction by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> property.</span></span> <span data-ttu-id="6bac0-107"><xref:System.Windows.Forms.FlowLayoutPanel> コントロールは、右から左 (RTL) のレイアウトでフローの方向を正しく反転します。</span><span class="sxs-lookup"><span data-stu-id="6bac0-107">The <xref:System.Windows.Forms.FlowLayoutPanel> control correctly reverses its flow direction in Right-to-Left (RTL) layouts.</span></span> <span data-ttu-id="6bac0-108">また、<xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> プロパティの値を設定して、<xref:System.Windows.Forms.FlowLayoutPanel> コントロールの内容がラップまたはクリップされるかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6bac0-108">You can also specify whether the <xref:System.Windows.Forms.FlowLayoutPanel> control's contents are wrapped or clipped by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> property.</span></span>  
  
 <span data-ttu-id="6bac0-109">
  <xref:System.Windows.Forms.FlowLayoutPanel> コントロールは、<xref:System.Windows.Forms.Control.AutoSize%2A> プロパティを `true\` に設定すると、自動的に内容に合わせたサイズにします。</span><span class="sxs-lookup"><span data-stu-id="6bac0-109">The <xref:System.Windows.Forms.FlowLayoutPanel> control automatically sizes to its contents when you set the <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="6bac0-110">用意されています、 **FlowBreak**プロパティをその子コントロール。</span><span class="sxs-lookup"><span data-stu-id="6bac0-110">It also provides a **FlowBreak** property to its child controls.</span></span> <span data-ttu-id="6bac0-111">FlowBreak プロパティの値を `true` に設定することで、 <xref:System.Windows.Forms.FlowLayoutPanel> コントロールを現在のフロー方向のコントロールにレイアウトすること、および次の行または列にラップすることを停止します。</span><span class="sxs-lookup"><span data-stu-id="6bac0-111">Setting the value of the FlowBreak property to `true` causes the <xref:System.Windows.Forms.FlowLayoutPanel> control to stop laying out controls in the current flow direction and wrap to the next row or column.</span></span>  
  
 <span data-ttu-id="6bac0-112">Windows フォーム コントロールは、<xref:System.Windows.Forms.FlowLayoutPanel> の他のインスタンスを含めて、<xref:System.Windows.Forms.FlowLayoutPanel> コントロールの子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6bac0-112">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.FlowLayoutPanel> control, including other instances of <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="6bac0-113">この機能により、実行時にフォームのサイズを調整する高度なレイアウトを構築することができます。</span><span class="sxs-lookup"><span data-stu-id="6bac0-113">With this capability, you can construct sophisticated layouts that adapt to your form's dimensions at run time.</span></span>  
  
 <span data-ttu-id="6bac0-114">参照してください[チュートリアル。FlowLayoutPanel を使用して Windows フォーム コントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)します。</span><span class="sxs-lookup"><span data-stu-id="6bac0-114">Also see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bac0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bac0-115">See also</span></span>
- <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="6bac0-116">FlowLayoutPanel コントロール</span><span class="sxs-lookup"><span data-stu-id="6bac0-116">FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-windows-forms.md)

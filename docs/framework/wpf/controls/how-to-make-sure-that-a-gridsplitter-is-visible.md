---
title: '方法: GridSplitter を表示されるようにする'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: 52a995a411614bcb677e34c563ad897637742c94
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622482"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="7d534-102">方法: GridSplitter を表示されるようにする</span><span class="sxs-lookup"><span data-stu-id="7d534-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="7d534-103">確認する方法を示します、<xref:System.Windows.Controls.GridSplitter>で他のコントロールによってコントロールが非、<xref:System.Windows.Controls.Grid>します。</span><span class="sxs-lookup"><span data-stu-id="7d534-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d534-104">例</span><span class="sxs-lookup"><span data-stu-id="7d534-104">Example</span></span>  
 <span data-ttu-id="7d534-105"><xref:System.Windows.Controls.Panel.Children%2A>の<xref:System.Windows.Controls.Grid>コントロールは、マークアップまたはコードで定義されている順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d534-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="7d534-106"><xref:System.Windows.Controls.GridSplitter> 最後の要素として定義する実行されていない場合、その他のコントロールでコントロールを隠すことが、<xref:System.Windows.Controls.Panel.Children%2A>コレクションまたはその他を付与するかどうかより高度な制御<xref:System.Windows.Controls.Panel.ZIndexProperty>します。</span><span class="sxs-lookup"><span data-stu-id="7d534-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="7d534-107">防ぐために非表示<xref:System.Windows.Controls.GridSplitter>コントロールは、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="7d534-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
-   <span data-ttu-id="7d534-108">確認します<xref:System.Windows.Controls.GridSplitter>コントロールは、最後の<xref:System.Windows.Controls.Panel.Children%2A>に追加、<xref:System.Windows.Controls.Grid>します。</span><span class="sxs-lookup"><span data-stu-id="7d534-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="7d534-109">次の例は、<xref:System.Windows.Controls.GridSplitter>の最後の要素として、<xref:System.Windows.Controls.Panel.Children%2A>のコレクション、<xref:System.Windows.Controls.Grid>します。</span><span class="sxs-lookup"><span data-stu-id="7d534-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   <span data-ttu-id="7d534-110">設定、<xref:System.Windows.Controls.Panel.ZIndexProperty>上、<xref:System.Windows.Controls.GridSplitter>にコントロールを非はそれ以外の場合よりも高くなります。</span><span class="sxs-lookup"><span data-stu-id="7d534-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="7d534-111">次の例では、<xref:System.Windows.Controls.GridSplitter>より高度な制御<xref:System.Windows.Controls.Panel.ZIndexProperty>よりも、<xref:System.Windows.Controls.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="7d534-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   <span data-ttu-id="7d534-112">それ以外の場合非表示にするコントロールのマージンを設定、<xref:System.Windows.Controls.GridSplitter>ように、<xref:System.Windows.Controls.GridSplitter>公開されます。</span><span class="sxs-lookup"><span data-stu-id="7d534-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="7d534-113">次の例では、余白を設定コントロールをオーバーレイはそれ以外の場合と非表示にする、<xref:System.Windows.Controls.GridSplitter>します。</span><span class="sxs-lookup"><span data-stu-id="7d534-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="7d534-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d534-114">See also</span></span>
- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="7d534-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="7d534-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)

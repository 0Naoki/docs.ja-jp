---
title: '方法: FocusVisualStyle をコントロールに適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: ae7820dac011425251d087dd4109c3f40bdd308c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493249"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="a142d-102">方法: FocusVisualStyle をコントロールに適用する</span><span class="sxs-lookup"><span data-stu-id="a142d-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="a142d-103">この例は、リソースにフォーカスの visual スタイルを作成し、コントロールにスタイルを適用する方法を示しますを使用して、<xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a142d-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a142d-104">例</span><span class="sxs-lookup"><span data-stu-id="a142d-104">Example</span></span>  
 <span data-ttu-id="a142d-105">次の例は、そのコントロールがキーボードでフォーカスの場合にのみ適用される追加のコントロールの複合を作成するスタイルを定義、[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a142d-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="a142d-106">スタイルを定義することでこれは、 <xref:System.Windows.Controls.ControlTemplate>、参照リソースとしてのスタイルを設定するときにその後、<xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a142d-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="a142d-107">境界線に似た、外部の四角形は四角形領域の外側に配置されます。</span><span class="sxs-lookup"><span data-stu-id="a142d-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="a142d-108">スタイルのサイズ設定を使用して、それ以外の場合は変更しない限り、<xref:System.Windows.FrameworkElement.ActualHeight%2A>と<xref:System.Windows.FrameworkElement.ActualWidth%2A>の場合、フォーカスの視覚スタイルが適用される四角形のコントロール。</span><span class="sxs-lookup"><span data-stu-id="a142d-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="a142d-109">この例は、負の値を設定、<xref:System.Windows.FrameworkElement.Margin%2A>フォーカスされたコントロール外に若干の枠を作成します。</span><span class="sxs-lookup"><span data-stu-id="a142d-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="a142d-110">A<xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>が付属している任意のコントロール テンプレートのスタイルに明示的なスタイルまたはテーマ スタイル; からコントロールの主なスタイルも作成できますを使用して、<xref:System.Windows.Controls.ControlTemplate>にそのスタイルを設定して、<xref:System.Windows.FrameworkElement.Style%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a142d-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="a142d-111">フォーカスの視覚スタイルはテーマまたは、UI 全体で一貫して使用する必要があります、異なる 2 つのフォーカスを設定できる各要素を使用するのではなく。</span><span class="sxs-lookup"><span data-stu-id="a142d-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="a142d-112">詳細については、次を参照してください。[コントロール、および FocusVisualStyle フォーカスのスタイル](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)します。</span><span class="sxs-lookup"><span data-stu-id="a142d-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a142d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a142d-113">See also</span></span>
- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [<span data-ttu-id="a142d-114">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a142d-114">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="a142d-115">コントロールのフォーカスのスタイルと FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="a142d-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)

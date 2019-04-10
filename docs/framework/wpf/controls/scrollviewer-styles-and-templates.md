---
title: ScrollViewer のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
ms.openlocfilehash: 9c0edfd7ab4772eb9a1f5ecdd3db611fa36bf8d3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226834"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="0e751-102">ScrollViewer のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0e751-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="0e751-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.ScrollViewer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0e751-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="0e751-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="0e751-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0e751-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e751-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="0e751-106">ScrollViewer パーツ</span><span class="sxs-lookup"><span data-stu-id="0e751-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="0e751-107">次の表に、名前付きパーツ、<xref:System.Windows.Controls.ScrollViewer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0e751-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="0e751-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="0e751-108">Part</span></span>|<span data-ttu-id="0e751-109">型</span><span class="sxs-lookup"><span data-stu-id="0e751-109">Type</span></span>|<span data-ttu-id="0e751-110">説明</span><span class="sxs-lookup"><span data-stu-id="0e751-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0e751-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="0e751-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="0e751-112">内のコンテンツのプレース ホルダー、<xref:System.Windows.Controls.ScrollViewer>します。</span><span class="sxs-lookup"><span data-stu-id="0e751-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="0e751-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="0e751-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="0e751-114"><xref:System.Windows.Controls.Primitives.ScrollBar>コンテンツを水平方向にスクロールするために使用します。</span><span class="sxs-lookup"><span data-stu-id="0e751-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="0e751-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="0e751-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="0e751-116"><xref:System.Windows.Controls.Primitives.ScrollBar>コンテンツを垂直方向にスクロールするために使用します。</span><span class="sxs-lookup"><span data-stu-id="0e751-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="0e751-117">ScrollViewer の状態</span><span class="sxs-lookup"><span data-stu-id="0e751-117">ScrollViewer States</span></span>  
 <span data-ttu-id="0e751-118">次の表のビジュアルの状態、<xref:System.Windows.Controls.ScrollViewer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0e751-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="0e751-119">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="0e751-119">VisualState Name</span></span>|<span data-ttu-id="0e751-120">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="0e751-120">VisualStateGroup Name</span></span>|<span data-ttu-id="0e751-121">説明</span><span class="sxs-lookup"><span data-stu-id="0e751-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0e751-122">有効</span><span class="sxs-lookup"><span data-stu-id="0e751-122">Valid</span></span>|<span data-ttu-id="0e751-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e751-123">ValidationStates</span></span>|<span data-ttu-id="0e751-124">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="0e751-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0e751-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0e751-125">InvalidFocused</span></span>|<span data-ttu-id="0e751-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e751-126">ValidationStates</span></span>|<span data-ttu-id="0e751-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="0e751-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0e751-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0e751-128">InvalidUnfocused</span></span>|<span data-ttu-id="0e751-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e751-129">ValidationStates</span></span>|<span data-ttu-id="0e751-130"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="0e751-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="0e751-131">ScrollViewer ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="0e751-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="0e751-132">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.ScrollViewer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0e751-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="0e751-133">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="0e751-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0e751-134">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e751-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e751-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e751-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0e751-136">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0e751-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0e751-137">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="0e751-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0e751-138">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0e751-138">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="0e751-139">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="0e751-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)

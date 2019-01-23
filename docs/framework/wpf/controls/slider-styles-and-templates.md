---
title: スライダーのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
ms.openlocfilehash: 3b56b26716eb2ffc0a776085579c4d5df09e3ace
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596255"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="fb5d2-102">スライダーのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="fb5d2-102">Slider Styles and Templates</span></span>
<span data-ttu-id="fb5d2-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.Slider>コントロール。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="fb5d2-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fb5d2-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="fb5d2-106">スライダー部分</span><span class="sxs-lookup"><span data-stu-id="fb5d2-106">Slider Parts</span></span>  
 <span data-ttu-id="fb5d2-107">次の表に、名前付きパーツ、<xref:System.Windows.Controls.Slider>コントロール。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="fb5d2-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="fb5d2-108">Part</span></span>|<span data-ttu-id="fb5d2-109">型</span><span class="sxs-lookup"><span data-stu-id="fb5d2-109">Type</span></span>|<span data-ttu-id="fb5d2-110">説明</span><span class="sxs-lookup"><span data-stu-id="fb5d2-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="fb5d2-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="fb5d2-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="fb5d2-112">位置を示す要素のコンテナー、<xref:System.Windows.Controls.Slider>します。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="fb5d2-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="fb5d2-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="fb5d2-114">要素に沿った選択範囲を表示する、<xref:System.Windows.Controls.Slider>します。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="fb5d2-115">選択範囲が表示される場合にのみ、<xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A>プロパティは`true`します。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="fb5d2-116">スライダーの状態</span><span class="sxs-lookup"><span data-stu-id="fb5d2-116">Slider States</span></span>  
 <span data-ttu-id="fb5d2-117">次の表のビジュアルの状態、<xref:System.Windows.Controls.Slider>コントロール。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="fb5d2-118">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="fb5d2-118">VisualState Name</span></span>|<span data-ttu-id="fb5d2-119">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="fb5d2-119">VisualStateGroup Name</span></span>|<span data-ttu-id="fb5d2-120">説明</span><span class="sxs-lookup"><span data-stu-id="fb5d2-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="fb5d2-121">標準</span><span class="sxs-lookup"><span data-stu-id="fb5d2-121">Normal</span></span>|<span data-ttu-id="fb5d2-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fb5d2-122">CommonStates</span></span>|<span data-ttu-id="fb5d2-123">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-123">The default state.</span></span>|  
|<span data-ttu-id="fb5d2-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="fb5d2-124">MouseOver</span></span>|<span data-ttu-id="fb5d2-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fb5d2-125">CommonStates</span></span>|<span data-ttu-id="fb5d2-126">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="fb5d2-127">無効</span><span class="sxs-lookup"><span data-stu-id="fb5d2-127">Disabled</span></span>|<span data-ttu-id="fb5d2-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fb5d2-128">CommonStates</span></span>|<span data-ttu-id="fb5d2-129">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-129">The control is disabled.</span></span>|  
|<span data-ttu-id="fb5d2-130">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="fb5d2-130">Focused</span></span>|<span data-ttu-id="fb5d2-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fb5d2-131">FocusStates</span></span>|<span data-ttu-id="fb5d2-132">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-132">The control has focus.</span></span>|  
|<span data-ttu-id="fb5d2-133">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="fb5d2-133">Unfocused</span></span>|<span data-ttu-id="fb5d2-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fb5d2-134">FocusStates</span></span>|<span data-ttu-id="fb5d2-135">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="fb5d2-136">有効</span><span class="sxs-lookup"><span data-stu-id="fb5d2-136">Valid</span></span>|<span data-ttu-id="fb5d2-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fb5d2-137">ValidationStates</span></span>|<span data-ttu-id="fb5d2-138">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="fb5d2-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fb5d2-139">InvalidFocused</span></span>|<span data-ttu-id="fb5d2-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fb5d2-140">ValidationStates</span></span>|<span data-ttu-id="fb5d2-141"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="fb5d2-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fb5d2-142">InvalidUnfocused</span></span>|<span data-ttu-id="fb5d2-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fb5d2-143">ValidationStates</span></span>|<span data-ttu-id="fb5d2-144"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="fb5d2-145">スライダーの ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="fb5d2-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="fb5d2-146">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.Slider>コントロール。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="fb5d2-147">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="fb5d2-148">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb5d2-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb5d2-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb5d2-149">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="fb5d2-150">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="fb5d2-150">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="fb5d2-151">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="fb5d2-151">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="fb5d2-152">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="fb5d2-152">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="fb5d2-153">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="fb5d2-153">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)

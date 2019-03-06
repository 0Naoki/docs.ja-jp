---
title: RadioButton のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
ms.openlocfilehash: 4f401c928db57a75bafa7fee0e59542b2eb8a3b6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377084"
---
# <a name="radiobutton-styles-and-templates"></a><span data-ttu-id="fe5f3-102">RadioButton のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="fe5f3-102">RadioButton Styles and Templates</span></span>
<span data-ttu-id="fe5f3-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.RadioButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.RadioButton> control.</span></span> <span data-ttu-id="fe5f3-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fe5f3-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="radiobutton-parts"></a><span data-ttu-id="fe5f3-106">RadioButton のパーツ</span><span class="sxs-lookup"><span data-stu-id="fe5f3-106">RadioButton Parts</span></span>  
 <span data-ttu-id="fe5f3-107"><xref:System.Windows.Controls.RadioButton>コントロールには、名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-107">The <xref:System.Windows.Controls.RadioButton> control does not have any named parts.</span></span>  
  
## <a name="radiobutton-states"></a><span data-ttu-id="fe5f3-108">状態の RadioButton</span><span class="sxs-lookup"><span data-stu-id="fe5f3-108">RadioButton States</span></span>  
 <span data-ttu-id="fe5f3-109">次の表のビジュアルの状態、<xref:System.Windows.Controls.RadioButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-109">The following table lists the visual states for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
|<span data-ttu-id="fe5f3-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="fe5f3-110">VisualState Name</span></span>|<span data-ttu-id="fe5f3-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="fe5f3-111">VisualStateGroup Name</span></span>|<span data-ttu-id="fe5f3-112">説明</span><span class="sxs-lookup"><span data-stu-id="fe5f3-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="fe5f3-113">標準</span><span class="sxs-lookup"><span data-stu-id="fe5f3-113">Normal</span></span>|<span data-ttu-id="fe5f3-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fe5f3-114">CommonStates</span></span>|<span data-ttu-id="fe5f3-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-115">The default state.</span></span>|  
|<span data-ttu-id="fe5f3-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="fe5f3-116">MouseOver</span></span>|<span data-ttu-id="fe5f3-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fe5f3-117">CommonStates</span></span>|<span data-ttu-id="fe5f3-118">マウス ポインターがコントロール上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="fe5f3-119">押されている</span><span class="sxs-lookup"><span data-stu-id="fe5f3-119">Pressed</span></span>|<span data-ttu-id="fe5f3-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fe5f3-120">CommonStates</span></span>|<span data-ttu-id="fe5f3-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-121">The control is pressed.</span></span>|  
|<span data-ttu-id="fe5f3-122">無効</span><span class="sxs-lookup"><span data-stu-id="fe5f3-122">Disabled</span></span>|<span data-ttu-id="fe5f3-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fe5f3-123">CommonStates</span></span>|<span data-ttu-id="fe5f3-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-124">The control is disabled.</span></span>|  
|<span data-ttu-id="fe5f3-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="fe5f3-125">Focused</span></span>|<span data-ttu-id="fe5f3-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fe5f3-126">FocusStates</span></span>|<span data-ttu-id="fe5f3-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-127">The control has focus.</span></span>|  
|<span data-ttu-id="fe5f3-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="fe5f3-128">Unfocused</span></span>|<span data-ttu-id="fe5f3-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fe5f3-129">FocusStates</span></span>|<span data-ttu-id="fe5f3-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="fe5f3-131">チェック済み</span><span class="sxs-lookup"><span data-stu-id="fe5f3-131">Checked</span></span>|<span data-ttu-id="fe5f3-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="fe5f3-132">CheckStates</span></span>|<span data-ttu-id="fe5f3-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> は `true` です。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="fe5f3-134">オフ</span><span class="sxs-lookup"><span data-stu-id="fe5f3-134">Unchecked</span></span>|<span data-ttu-id="fe5f3-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="fe5f3-135">CheckStates</span></span>|<span data-ttu-id="fe5f3-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> は `false` です。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="fe5f3-137">不確定です</span><span class="sxs-lookup"><span data-stu-id="fe5f3-137">Indeterminate</span></span>|<span data-ttu-id="fe5f3-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="fe5f3-138">CheckStates</span></span>|<span data-ttu-id="fe5f3-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> が `true` で、<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `null` です。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="fe5f3-140">有効</span><span class="sxs-lookup"><span data-stu-id="fe5f3-140">Valid</span></span>|<span data-ttu-id="fe5f3-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fe5f3-141">ValidationStates</span></span>|<span data-ttu-id="fe5f3-142">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="fe5f3-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fe5f3-143">InvalidFocused</span></span>|<span data-ttu-id="fe5f3-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fe5f3-144">ValidationStates</span></span>|<span data-ttu-id="fe5f3-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="fe5f3-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fe5f3-146">InvalidUnfocused</span></span>|<span data-ttu-id="fe5f3-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fe5f3-147">ValidationStates</span></span>|<span data-ttu-id="fe5f3-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="radiobutton-controltemplate-example"></a><span data-ttu-id="fe5f3-149">オプション ボタン ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="fe5f3-149">RadioButton ControlTemplate Example</span></span>  
 <span data-ttu-id="fe5f3-150">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.RadioButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
 <span data-ttu-id="fe5f3-151">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="fe5f3-152">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe5f3-152">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe5f3-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe5f3-153">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="fe5f3-154">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="fe5f3-154">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="fe5f3-155">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="fe5f3-155">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="fe5f3-156">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="fe5f3-156">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="fe5f3-157">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="fe5f3-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)

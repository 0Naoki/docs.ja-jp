---
title: '方法: スライダーの目盛りをカスタマイズする'
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: b6ade07b0b4c04578d2523d6d8ba992b8b2d31f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696673"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="8c52f-102">方法: スライダーの目盛りをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="8c52f-102">How to: Customize the Ticks on a Slider</span></span>
<span data-ttu-id="8c52f-103">この例は、作成する方法を示します、<xref:System.Windows.Controls.Slider>目盛りがあるコントロール。</span><span class="sxs-lookup"><span data-stu-id="8c52f-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c52f-104">例</span><span class="sxs-lookup"><span data-stu-id="8c52f-104">Example</span></span>  
 <span data-ttu-id="8c52f-105"><xref:System.Windows.Controls.Primitives.TickBar>表示を設定すると、<xref:System.Windows.Controls.Slider.TickPlacement%2A>プロパティ以外の値を<xref:System.Windows.Controls.Primitives.TickPlacement.None>、これは、既定値。</span><span class="sxs-lookup"><span data-stu-id="8c52f-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="8c52f-106">次の例は、作成する方法を示します、<xref:System.Windows.Controls.Slider>で、<xref:System.Windows.Controls.Primitives.TickBar>ことが表示されますが目盛り。</span><span class="sxs-lookup"><span data-stu-id="8c52f-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="8c52f-107"><xref:System.Windows.Controls.Slider.TickPlacement%2A>と<xref:System.Windows.Controls.Slider.TickFrequency%2A>プロパティは、目盛りとそれらの間の間隔の場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="8c52f-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="8c52f-108">移動すると、 <xref:System.Windows.Controls.Primitives.Thumb>、ツール ヒントの値を表示する、<xref:System.Windows.Controls.Slider>します。</span><span class="sxs-lookup"><span data-stu-id="8c52f-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="8c52f-109"><xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A>プロパティは、ツールヒントが表示される場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="8c52f-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="8c52f-110"><xref:System.Windows.Controls.Primitives.Thumb>ため目盛りの場所に対応して動き<xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A>に設定されている`true`します。</span><span class="sxs-lookup"><span data-stu-id="8c52f-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="8c52f-111">次の例は、使用する方法を示します、<xref:System.Windows.Controls.Slider.Ticks%2A>マークに沿った目盛りを作成するプロパティ、<xref:System.Windows.Controls.Slider>間隔は不規則です。</span><span class="sxs-lookup"><span data-stu-id="8c52f-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8c52f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c52f-112">See also</span></span>
- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- [<span data-ttu-id="8c52f-113">スライダーの操作方法に関するトピック</span><span class="sxs-lookup"><span data-stu-id="8c52f-113">Slider How-to Topics</span></span>](https://msdn.microsoft.com/library/534be86c-afb2-425d-8186-631278a9925e)

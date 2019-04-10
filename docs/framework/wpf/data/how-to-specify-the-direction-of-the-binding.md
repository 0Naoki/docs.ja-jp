---
title: '方法: バインディングの方向を指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 4334ed178e7f2ed90928db6b434eb8c9fee77bf7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206435"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="6cad3-102">方法: バインディングの方向を指定する</span><span class="sxs-lookup"><span data-stu-id="6cad3-102">How to: Specify the Direction of the Binding</span></span>
<span data-ttu-id="6cad3-103">この例では、バインドの更新先 (バインディング ターゲット (ターゲット) のプロパティのみ、バインディング ソース (ソース) のプロパティのみ、またはターゲットのプロパティとソースのプロパティの両方) を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6cad3-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cad3-104">例</span><span class="sxs-lookup"><span data-stu-id="6cad3-104">Example</span></span>  
 <span data-ttu-id="6cad3-105">使用する、<xref:System.Windows.Data.Binding.Mode%2A>プロパティ バインディングの方向を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cad3-105">You use the <xref:System.Windows.Data.Binding.Mode%2A> property to specify the direction of the binding.</span></span> <span data-ttu-id="6cad3-106">次の列挙リストは、バインドの更新で使用できるオプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="6cad3-106">The following enumeration list shows the available options for binding updates:</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay> <span data-ttu-id="6cad3-107">対象となるプロパティまたはソースのプロパティのいずれかが変更されるたびに、ターゲット プロパティまたはプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="6cad3-107">updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.OneWay> <span data-ttu-id="6cad3-108">ソース プロパティが変更された場合にのみ、ターゲット プロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="6cad3-108">updates the target property only when the source property changes.</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.OneTime> <span data-ttu-id="6cad3-109">アプリケーションの起動時にのみ、またはターゲット プロパティを更新、<xref:System.Windows.FrameworkElement.DataContext%2A>で変更が行われます。</span><span class="sxs-lookup"><span data-stu-id="6cad3-109">updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource> <span data-ttu-id="6cad3-110">ターゲット プロパティが変更されたときに、ソース プロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="6cad3-110">updates the source property when the target property changes.</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.Default> <span data-ttu-id="6cad3-111">により、既定<xref:System.Windows.Data.Binding.Mode%2A>に使用するターゲット プロパティの値。</span><span class="sxs-lookup"><span data-stu-id="6cad3-111">causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="6cad3-112">詳細については、<xref:System.Windows.Data.BindingMode> 列挙型のページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6cad3-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="6cad3-113"><xref:System.Windows.Data.Binding.Mode%2A> プロパティを設定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="6cad3-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="6cad3-114">ソースの変更を検出するために (に適用できる<xref:System.Windows.Data.BindingMode.OneWay>と<xref:System.Windows.Data.BindingMode.TwoWay>バインド) など、ソースが適切なプロパティ変更通知のメカニズムを実装する必要があります<xref:System.ComponentModel.INotifyPropertyChanged>します。</span><span class="sxs-lookup"><span data-stu-id="6cad3-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="6cad3-115">参照してください[プロパティ変更通知を実装](how-to-implement-property-change-notification.md)の例については、<xref:System.ComponentModel.INotifyPropertyChanged>実装します。</span><span class="sxs-lookup"><span data-stu-id="6cad3-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="6cad3-116"><xref:System.Windows.Data.BindingMode.TwoWay>または<xref:System.Windows.Data.BindingMode.OneWayToSource>バインドを設定して、ソースの更新のタイミングを制御することができます、<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="6cad3-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="6cad3-117">詳細については、「<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cad3-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cad3-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cad3-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="6cad3-119">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="6cad3-119">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="6cad3-120">方法のトピック</span><span class="sxs-lookup"><span data-stu-id="6cad3-120">How-to Topics</span></span>](data-binding-how-to-topics.md)

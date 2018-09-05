---
title: '方法 : PriorityBinding を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: a7729ec3d06ec701cf2194bed5d90b5bed76573a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43671697"
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="3aaee-102">方法 : PriorityBinding を実装する</span><span class="sxs-lookup"><span data-stu-id="3aaee-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="3aaee-103"><xref:System.Windows.Data.PriorityBinding> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]のバインディングの一覧を指定することによって動作します。</span><span class="sxs-lookup"><span data-stu-id="3aaee-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="3aaee-104">バインディングのリストの順序は、最も高い優先度から最も低い優先順位。</span><span class="sxs-lookup"><span data-stu-id="3aaee-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="3aaee-105">最高の優先度のバインドは、値を返す場合が正常に処理されるときはありますありません、リスト内の他のバインディングを処理する必要が。</span><span class="sxs-lookup"><span data-stu-id="3aaee-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="3aaee-106">最高の優先度のバインドを評価する時間がかかる場合がある可能性がありますの優先順位の高いバインドが正常に値を返すまで正常に値を返す次の最も高い優先順位が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3aaee-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3aaee-107">例</span><span class="sxs-lookup"><span data-stu-id="3aaee-107">Example</span></span>  
 <span data-ttu-id="3aaee-108">示すためにどの<xref:System.Windows.Data.PriorityBinding>、動作、`AsyncDataSource`プロパティは、次の 3 つのオブジェクトが作成された: `FastDP`、`SlowerDP`と`SlowestDP`。</span><span class="sxs-lookup"><span data-stu-id="3aaee-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="3aaee-109">Get アクセサー`FastDP`の値を返します、`_fastDP`データ メンバー。</span><span class="sxs-lookup"><span data-stu-id="3aaee-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="3aaee-110">Get アクセサー`SlowerDP`までの値を返す前に 3 秒間待機、`_slowerDP`データ メンバー。</span><span class="sxs-lookup"><span data-stu-id="3aaee-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="3aaee-111">Get アクセサー`SlowestDP`までの値を返す前に 5 秒間待機、`_slowestDP`データ メンバー。</span><span class="sxs-lookup"><span data-stu-id="3aaee-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3aaee-112">この例は、デモンストレーション目的のみで提供されます。</span><span class="sxs-lookup"><span data-stu-id="3aaee-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="3aaee-113">[!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)]桁違いのフィールド セットをよりも、プロパティ定義のガイドラインをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3aaee-113">The [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="3aaee-114">詳細については、次を参照してください。 [NIB: 選択するプロパティとメソッド](https://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af)します。</span><span class="sxs-lookup"><span data-stu-id="3aaee-114">For more information, see [NIB: Choosing Between Properties and Methods](https://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af).</span></span>  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="3aaee-115"><xref:System.Windows.Controls.TextBlock.Text%2A>プロパティが上記にバインド`AsyncDS`を使用して<xref:System.Windows.Data.PriorityBinding>:</span><span class="sxs-lookup"><span data-stu-id="3aaee-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="3aaee-116">バインディング エンジンが処理するときに、<xref:System.Windows.Data.Binding>オブジェクトの場合、最初の開始<xref:System.Windows.Data.Binding>がバインドされている、`SlowestDP`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3aaee-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="3aaee-117">ときにこの<xref:System.Windows.Data.Binding>は、処理は返されません値が正常にためがスリープ状態を 5 秒間、そのため、[次へ]<xref:System.Windows.Data.Binding>要素が処理されます。</span><span class="sxs-lookup"><span data-stu-id="3aaee-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="3aaee-118">次<xref:System.Windows.Data.Binding>は正常に完了しなかった値が 3 秒間スリープ状態にあるためです。</span><span class="sxs-lookup"><span data-stu-id="3aaee-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="3aaee-119">バインディング エンジンは、次に、移動<xref:System.Windows.Data.Binding>にバインドする要素を`FastDP`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3aaee-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="3aaee-120">これは、 <xref:System.Windows.Data.Binding> "高速 Value"の値を返します。</span><span class="sxs-lookup"><span data-stu-id="3aaee-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="3aaee-121"><xref:System.Windows.Controls.TextBlock> "高速 Value"の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aaee-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="3aaee-122">3 秒が経過した後、 `SlowerDP` "低速 Value"の値を返します。</span><span class="sxs-lookup"><span data-stu-id="3aaee-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="3aaee-123"><xref:System.Windows.Controls.TextBlock> "低速 Value"の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aaee-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="3aaee-124">5 秒が経過した後、 `SlowestDP` 「最も低速な値」の値を返します。</span><span class="sxs-lookup"><span data-stu-id="3aaee-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="3aaee-125">そのバインディングは、最初に表示されているために、最高の優先順位が。</span><span class="sxs-lookup"><span data-stu-id="3aaee-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="3aaee-126"><xref:System.Windows.Controls.TextBlock>に「最も低速な値」の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aaee-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="3aaee-127">参照してください<xref:System.Windows.Data.PriorityBinding>については、バインドからの成功した戻り値と見なされます。</span><span class="sxs-lookup"><span data-stu-id="3aaee-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aaee-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="3aaee-128">See Also</span></span>  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="3aaee-129">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="3aaee-129">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="3aaee-130">方法トピック</span><span class="sxs-lookup"><span data-stu-id="3aaee-130">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

---
title: '方法: カスタム ルーティング イベントを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: c351bec05fa8ad8438cb8521f6ab1e6277a40b1d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373401"
---
# <a name="how-to-create-a-custom-routed-event"></a><span data-ttu-id="8d993-102">方法: カスタム ルーティング イベントを作成する</span><span class="sxs-lookup"><span data-stu-id="8d993-102">How to: Create a Custom Routed Event</span></span>
<span data-ttu-id="8d993-103">イベントのルーティングをサポートするために、カスタム イベントを登録する必要があります、<xref:System.Windows.RoutedEvent>を使用して、<xref:System.Windows.EventManager.RegisterRoutedEvent%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="8d993-103">For your custom event to support event routing, you need to register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="8d993-104">この例では、カスタム ルーティング イベント作成の基本を紹介します。</span><span class="sxs-lookup"><span data-stu-id="8d993-104">This example demonstrates the basics of creating a custom routed event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d993-105">例</span><span class="sxs-lookup"><span data-stu-id="8d993-105">Example</span></span>  
 <span data-ttu-id="8d993-106">まず登録次の例に示すように、<xref:System.Windows.RoutedEvent>を使用して、<xref:System.Windows.EventManager.RegisterRoutedEvent%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="8d993-106">As shown in the following example, you first register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="8d993-107">慣例により、<xref:System.Windows.RoutedEvent>静的フィールドの名前サフィックスを末尾***イベント***します。</span><span class="sxs-lookup"><span data-stu-id="8d993-107">By convention, the <xref:System.Windows.RoutedEvent> static field name should end with the suffix ***Event***.</span></span> <span data-ttu-id="8d993-108">この例では、イベントの名前は`Tap`イベントのルーティング方法で、<xref:System.Windows.RoutingStrategy.Bubble>します。</span><span class="sxs-lookup"><span data-stu-id="8d993-108">In this example, the name of the event is `Tap` and the routing strategy of the event is <xref:System.Windows.RoutingStrategy.Bubble>.</span></span> <span data-ttu-id="8d993-109">登録呼び出し後、イベントの add-and-remove [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] イベント アクセサーを提供できます。</span><span class="sxs-lookup"><span data-stu-id="8d993-109">After the registration call, you can provide add-and-remove [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event accessors for the event.</span></span>  
  
 <span data-ttu-id="8d993-110">この特別な例では `OnTap` 仮想メソッド経由でイベントが発生していますが、イベントの発生や変更に対するイベントの反応の仕方はニーズによって変わります。</span><span class="sxs-lookup"><span data-stu-id="8d993-110">Note that even though the event is raised through the `OnTap` virtual method in this particular example, how you raise your event or how your event responds to changes depends on your needs.</span></span>  
  
 <span data-ttu-id="8d993-111">この例は、のサブクラス全体を基本的には実装にも注意してください<xref:System.Windows.Controls.Button>; サブクラスであるが、別のアセンブリとしてビルドし、は別にカスタム クラスとしてインスタンス化し、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ページ。</span><span class="sxs-lookup"><span data-stu-id="8d993-111">Note also that this example basically implements an entire subclass of <xref:System.Windows.Controls.Button>; that subclass is built as a separate assembly and then instantiated as a custom class on a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="8d993-112">これはサブクラス化されたコントロールを他のコントロールで構成されたツリーに挿入できるという概念を示すものです。この状況では、このようなコントロールのカスタム イベントには、あらゆるネイティブ [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 要素とまったく同じイベント ルーティング機能が与えられます。</span><span class="sxs-lookup"><span data-stu-id="8d993-112">This is to illustrate the concept that subclassed controls can be inserted into trees composed of other controls, and that in this situation, custom events on these controls have the very same event routing capabilities as any native [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] element does.</span></span>  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 <span data-ttu-id="8d993-113">トンネリング イベントが作成された同じ方法ですが、<xref:System.Windows.RoutedEvent.RoutingStrategy%2A>設定<xref:System.Windows.RoutingStrategy.Tunnel>登録呼び出しで。</span><span class="sxs-lookup"><span data-stu-id="8d993-113">Tunneling events are created the same way, but with <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> set to <xref:System.Windows.RoutingStrategy.Tunnel> in the registration call.</span></span> <span data-ttu-id="8d993-114">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] のトンネル イベントには接頭辞として "Preview" という単語が付く決まりになっています。</span><span class="sxs-lookup"><span data-stu-id="8d993-114">By convention, tunneling events in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] are prefixed with the word "Preview".</span></span>  
  
 <span data-ttu-id="8d993-115">バブリング イベントの動作例については、「[ルーティング イベントを処理する](how-to-handle-a-routed-event.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d993-115">To see an example of how bubbling events work, see [Handle a Routed Event](how-to-handle-a-routed-event.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d993-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d993-116">See also</span></span>
- [<span data-ttu-id="8d993-117">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="8d993-117">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="8d993-118">入力の概要</span><span class="sxs-lookup"><span data-stu-id="8d993-118">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="8d993-119">コントロールの作成の概要</span><span class="sxs-lookup"><span data-stu-id="8d993-119">Control Authoring Overview</span></span>](../controls/control-authoring-overview.md)

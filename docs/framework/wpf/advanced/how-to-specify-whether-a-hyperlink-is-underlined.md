---
title: '方法: ハイパーリンクに下線を引くかどうかを指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 9e8eb54d4710095a1aba052b16e49c528bd17c0e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371049"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a><span data-ttu-id="5cfad-102">方法: ハイパーリンクに下線を引くかどうかを指定する</span><span class="sxs-lookup"><span data-stu-id="5cfad-102">How to: Specify Whether a Hyperlink is Underlined</span></span>
<span data-ttu-id="5cfad-103"><xref:System.Windows.Documents.Hyperlink>オブジェクトがインライン レベル フロー コンテンツ要素、フロー コンテンツ内のハイパーリンクをホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="5cfad-103">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="5cfad-104">既定では、<xref:System.Windows.Documents.Hyperlink>を使用して、<xref:System.Windows.TextDecoration>下線を表示するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5cfad-104">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="5cfad-105"><xref:System.Windows.TextDecoration> 多数ある場合は特に、オブジェクトは処理を要するインスタンスを作成すると、パフォーマンスにできる<xref:System.Windows.Documents.Hyperlink>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5cfad-105"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="5cfad-106">広範に使用する場合<xref:System.Windows.Documents.Hyperlink>要素などのイベントをトリガーするときにのみ下線を表示するのにすることがあります、<xref:System.Windows.ContentElement.MouseEnter>イベント。</span><span class="sxs-lookup"><span data-stu-id="5cfad-106">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="5cfad-107">次の例では、"マイ MSN"リンクの下線が動的-にのみ表示されるときに、<xref:System.Windows.ContentElement.MouseEnter>イベントがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="5cfad-107">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="5cfad-108">![Textdecorations を表示するハイパーリンク](./media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="5cfad-108">![Hyperlinks displaying TextDecorations](./media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="5cfad-109">Textdecorations をで定義されているハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="5cfad-109">Hyperlinks defined with TextDecorations</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cfad-110">例</span><span class="sxs-lookup"><span data-stu-id="5cfad-110">Example</span></span>  
 <span data-ttu-id="5cfad-111">次のマークアップ サンプルでは、<xref:System.Windows.Documents.Hyperlink>下線なしで定義されています。</span><span class="sxs-lookup"><span data-stu-id="5cfad-111">The following markup sample shows a <xref:System.Windows.Documents.Hyperlink> defined with and without an underline:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 <span data-ttu-id="5cfad-112">次のコード サンプルの下線を作成する方法を示しています、<xref:System.Windows.Documents.Hyperlink>上、<xref:System.Windows.ContentElement.MouseEnter>イベント上で削除し、<xref:System.Windows.ContentElement.MouseLeave>イベント。</span><span class="sxs-lookup"><span data-stu-id="5cfad-112">The following code sample shows how to create an underline for the <xref:System.Windows.Documents.Hyperlink> on the <xref:System.Windows.ContentElement.MouseEnter> event, and remove it on the <xref:System.Windows.ContentElement.MouseLeave> event.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a><span data-ttu-id="5cfad-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5cfad-113">See also</span></span>
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="5cfad-114">WPF アプリケーションのパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="5cfad-114">Optimizing WPF Application Performance</span></span>](optimizing-wpf-application-performance.md)
- [<span data-ttu-id="5cfad-115">文字の装飾を作成する</span><span class="sxs-lookup"><span data-stu-id="5cfad-115">Create a Text Decoration</span></span>](how-to-create-a-text-decoration.md)

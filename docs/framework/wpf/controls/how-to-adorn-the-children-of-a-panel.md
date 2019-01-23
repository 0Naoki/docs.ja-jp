---
title: '方法: パネルの子を装飾する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: ae039243ded93eb2bc7f85f9f07fad1dbe0eac2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544979"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="5ed6b-102">方法: パネルの子を装飾する</span><span class="sxs-lookup"><span data-stu-id="5ed6b-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="5ed6b-103">この例は、プログラムで、指定した子に装飾をバインドする方法を示しています。<xref:System.Windows.Controls.Panel>します。</span><span class="sxs-lookup"><span data-stu-id="5ed6b-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ed6b-104">例</span><span class="sxs-lookup"><span data-stu-id="5ed6b-104">Example</span></span>  
 <span data-ttu-id="5ed6b-105">子に装飾をバインドする、 <xref:System.Windows.Controls.Panel>、これらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5ed6b-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="5ed6b-106">新しい宣言<xref:System.Windows.Documents.AdornerLayer>オブジェクトと呼び出し、 `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>メソッドを持つ子が装飾対象要素の装飾層が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="5ed6b-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="5ed6b-107">呼び出し、親要素の子を列挙、<xref:System.Windows.Documents.AdornerLayer.Add%2A>メソッドを各子要素に装飾をバインドします。</span><span class="sxs-lookup"><span data-stu-id="5ed6b-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="5ed6b-108">次の例は、simplecircleadorner 参照の子に (上記) を連結、<xref:System.Windows.Controls.StackPanel>という*myStackPanel*します。</span><span class="sxs-lookup"><span data-stu-id="5ed6b-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  <span data-ttu-id="5ed6b-109">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] を使用して、装飾を別の要素にバインドする方法は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5ed6b-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ed6b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ed6b-110">See also</span></span>
- [<span data-ttu-id="5ed6b-111">装飾の概要</span><span class="sxs-lookup"><span data-stu-id="5ed6b-111">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)

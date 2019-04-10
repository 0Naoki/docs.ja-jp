---
title: '方法: 列挙値にバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 5026261366d6abde82790f05780d8ba2c29c4a49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210023"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="482b4-102">方法: 列挙値にバインドする</span><span class="sxs-lookup"><span data-stu-id="482b4-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="482b4-103">この例では、列挙型の GetValues メソッドにバインドして列挙型にバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="482b4-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="482b4-104">例</span><span class="sxs-lookup"><span data-stu-id="482b4-104">Example</span></span>  
 <span data-ttu-id="482b4-105">次の例では、<xref:System.Windows.Controls.ListBox>の一覧を表示します<xref:System.Windows.HorizontalAlignment>データ バインディングの列挙値。</span><span class="sxs-lookup"><span data-stu-id="482b4-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="482b4-106"><xref:System.Windows.Controls.ListBox>と<xref:System.Windows.Controls.Button>を変更するようにバインドされて、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>プロパティの値、<xref:System.Windows.Controls.Button>で値を選択して、<xref:System.Windows.Controls.ListBox>します。</span><span class="sxs-lookup"><span data-stu-id="482b4-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="482b4-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="482b4-107">See also</span></span>

- [<span data-ttu-id="482b4-108">メソッドにバインドする</span><span class="sxs-lookup"><span data-stu-id="482b4-108">Bind to a Method</span></span>](how-to-bind-to-a-method.md)
- [<span data-ttu-id="482b4-109">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="482b4-109">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="482b4-110">方法のトピック</span><span class="sxs-lookup"><span data-stu-id="482b4-110">How-to Topics</span></span>](data-binding-how-to-topics.md)

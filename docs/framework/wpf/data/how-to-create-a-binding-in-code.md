---
title: '方法 : コードでバインディングを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 2d13650cb3e9a4e97a6642992b7211f323b9ea96
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502259"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="cff96-102">方法 : コードでバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="cff96-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="cff96-103">この例を作成し、設定する方法を示しています、<xref:System.Windows.Data.Binding>コード。</span><span class="sxs-lookup"><span data-stu-id="cff96-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cff96-104">例</span><span class="sxs-lookup"><span data-stu-id="cff96-104">Example</span></span>  
 <span data-ttu-id="cff96-105"><xref:System.Windows.FrameworkElement>クラスおよび<xref:System.Windows.FrameworkContentElement>クラスの両方を公開、`SetBinding`メソッド。</span><span class="sxs-lookup"><span data-stu-id="cff96-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="cff96-106">これらのクラスを継承する要素をバインドする場合を呼び出すことができます、<xref:System.Windows.FrameworkElement.SetBinding%2A>メソッドを直接します。</span><span class="sxs-lookup"><span data-stu-id="cff96-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="cff96-107">次の例は、という名前のクラスを作成`MyData`、という名前のプロパティを含む`MyDataProperty`します。</span><span class="sxs-lookup"><span data-stu-id="cff96-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="cff96-108">次の例では、バインディング、バインディングのソースを設定するオブジェクトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cff96-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="cff96-109">この例では<xref:System.Windows.FrameworkElement.SetBinding%2A>にバインドする、<xref:System.Windows.Controls.TextBlock.Text%2A>プロパティの`myText`、これは、<xref:System.Windows.Controls.TextBlock>コントロールに`MyDataProperty`。</span><span class="sxs-lookup"><span data-stu-id="cff96-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="cff96-110">完全なコード サンプルでは、次を参照してください。[コードのみのバインドのサンプル](https://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6)します。</span><span class="sxs-lookup"><span data-stu-id="cff96-110">For the complete code sample, see [Code-only Binding Sample](https://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6).</span></span>  
  
 <span data-ttu-id="cff96-111">呼び出す代わりに<xref:System.Windows.FrameworkElement.SetBinding%2A>、使用することができます、<xref:System.Windows.Data.BindingOperations.SetBinding%2A>の静的メソッド、<xref:System.Windows.Data.BindingOperations>クラス。</span><span class="sxs-lookup"><span data-stu-id="cff96-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="cff96-112">次の例で呼び出し<xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>の代わりに<xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType>にバインドする`myText`に`myDataProperty`します。</span><span class="sxs-lookup"><span data-stu-id="cff96-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="cff96-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="cff96-113">See Also</span></span>  
 [<span data-ttu-id="cff96-114">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="cff96-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="cff96-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="cff96-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

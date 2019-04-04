---
title: '方法: Freezable を読み取り専用にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 874724584b44c17ff6c01331295cfa1a60978d54
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360352"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="810f7-102">方法: Freezable を読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="810f7-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="810f7-103">この例では、作成、<xref:System.Windows.Freezable>呼び出すことによって、読み取り専用の<xref:System.Windows.Freezable.Freeze%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="810f7-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="810f7-104">固定することはできません、<xref:System.Windows.Freezable>オブジェクトのかどうかは、次の条件のいずれかが`true`オブジェクトについて。</span><span class="sxs-lookup"><span data-stu-id="810f7-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
-   <span data-ttu-id="810f7-105">アニメーション化されたまたは、データ バインドされたプロパティ。</span><span class="sxs-lookup"><span data-stu-id="810f7-105">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="810f7-106">動的なリソースが設定されているプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="810f7-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="810f7-107">動的リソースの詳細については、、 [XAML リソース](xaml-resources.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="810f7-107">For more information about dynamic resources, see the [XAML Resources](xaml-resources.md).</span></span>  
  
-   <span data-ttu-id="810f7-108">含まれている<xref:System.Windows.Freezable>サブオブジェクトを固定することはできません。</span><span class="sxs-lookup"><span data-stu-id="810f7-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="810f7-109">これらの条件が場合`false`の<xref:System.Windows.Freezable>オブジェクトする予定がない変更を固定するパフォーマンスを向上することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="810f7-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="810f7-110">例</span><span class="sxs-lookup"><span data-stu-id="810f7-110">Example</span></span>  
 <span data-ttu-id="810f7-111">次の例では、フリーズ、<xref:System.Windows.Media.SolidColorBrush>の型である<xref:System.Windows.Freezable>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="810f7-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="810f7-112">詳細については<xref:System.Windows.Freezable>、オブジェクトを参照してください、 [Freezable オブジェクトの概要](freezable-objects-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="810f7-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="810f7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="810f7-113">See also</span></span>
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="810f7-114">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="810f7-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="810f7-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="810f7-115">How-to Topics</span></span>](base-elements-how-to-topics.md)

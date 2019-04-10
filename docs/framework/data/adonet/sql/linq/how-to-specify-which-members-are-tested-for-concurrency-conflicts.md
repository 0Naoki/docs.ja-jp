---
title: '方法: コンカレンシーの競合を検査するメンバーを指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
ms.openlocfilehash: 9a1b4ab2dc28c569473eddbf50b96d10298d8d3c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310435"
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a><span data-ttu-id="6e1cd-102">方法: コンカレンシーの競合を検査するメンバーを指定する</span><span class="sxs-lookup"><span data-stu-id="6e1cd-102">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>
<span data-ttu-id="6e1cd-103">3 つの列挙型のいずれかの適用、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>プロパティを<xref:System.Data.Linq.Mapping.ColumnAttribute>オプティミスティック同時実行競合の検出の更新プログラムに含まれるメンバーを指定する属性を確認します。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-103">Apply one of three enums to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify which members are to be included in update checks for the detection of optimistic concurrency conflicts.</span></span>  
  
 <span data-ttu-id="6e1cd-104"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> プロパティ (デザイン時に設定) は、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の実行時の同時実行機能と一緒に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-104">The <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property (mapped at design time) is used together with run-time concurrency features in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="6e1cd-105">詳細については、次を参照してください。[オプティミスティック同時実行制御。概要](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e1cd-106">`IsVersion=true` として指定されているメンバーがない限り、元のメンバーの各値は、データベースの現在の状態と比較されます。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-106">Original member values are compared with the current database state as long as no member is designated as `IsVersion=true`.</span></span> <span data-ttu-id="6e1cd-107">詳細については、「 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 <span data-ttu-id="6e1cd-108">コード例については、「<xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-108">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="6e1cd-109">競合の検出でこのメンバーを常に使用するには</span><span class="sxs-lookup"><span data-stu-id="6e1cd-109">To always use this member for detecting conflicts</span></span>  
  
1. <span data-ttu-id="6e1cd-110"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-110">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="6e1cd-111"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> プロパティ値を `Always` に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-111">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Always`.</span></span>  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="6e1cd-112">競合の検出でこのメンバーを使用しないようにするには</span><span class="sxs-lookup"><span data-stu-id="6e1cd-112">To never use this member for detecting conflicts</span></span>  
  
1. <span data-ttu-id="6e1cd-113"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-113">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="6e1cd-114"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> プロパティ値を `Never` に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-114">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Never`.</span></span>  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a><span data-ttu-id="6e1cd-115">アプリケーションでメンバーの値が変更された場合にのみ、競合の検出でこのメンバーを使用するには</span><span class="sxs-lookup"><span data-stu-id="6e1cd-115">To use this member for detecting conflicts only when the application has changed the value of the member</span></span>  
  
1. <span data-ttu-id="6e1cd-116"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-116">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="6e1cd-117"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> プロパティ値を `WhenChanged` に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-117">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `WhenChanged`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e1cd-118">例</span><span class="sxs-lookup"><span data-stu-id="6e1cd-118">Example</span></span>  
 <span data-ttu-id="6e1cd-119">次の例では、更新チェックで `HomePage` オブジェクトが検査されないように指定しています。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-119">The following example specifies that `HomePage` objects should never be tested during update checks.</span></span> <span data-ttu-id="6e1cd-120">詳細については、「 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e1cd-120">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6e1cd-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e1cd-121">See also</span></span>

- [<span data-ttu-id="6e1cd-122">方法: 変更の競合を管理する</span><span class="sxs-lookup"><span data-stu-id="6e1cd-122">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="6e1cd-123">データの変更と変更の送信</span><span class="sxs-lookup"><span data-stu-id="6e1cd-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)

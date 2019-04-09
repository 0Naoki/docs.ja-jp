---
title: '方法: メンバーの競合情報を取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: fae1513e7a7ead98318d907b220b7510758c9ffe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115090"
---
# <a name="how-to-retrieve-member-conflict-information"></a><span data-ttu-id="20873-102">方法: メンバーの競合情報を取得する</span><span class="sxs-lookup"><span data-stu-id="20873-102">How to: Retrieve Member Conflict Information</span></span>
<span data-ttu-id="20873-103"><xref:System.Data.Linq.MemberChangeConflict> クラスを使用すると、競合する個々のメンバーに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="20873-103">You can use the <xref:System.Data.Linq.MemberChangeConflict> class to retrieve information about individual members in conflict.</span></span> <span data-ttu-id="20873-104">この同じコンテキストで、メンバーの競合の処理をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="20873-104">In this same context you can provide for custom handling of the conflict for any member.</span></span> <span data-ttu-id="20873-105">詳細については、次を参照してください。[オプティミスティック同時実行制御。概要](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="20873-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="20873-106">例</span><span class="sxs-lookup"><span data-stu-id="20873-106">Example</span></span>  
 <span data-ttu-id="20873-107">次のコードでは、<xref:System.Data.Linq.ObjectChangeConflict> オブジェクトを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="20873-107">The following code iterates through the <xref:System.Data.Linq.ObjectChangeConflict> objects.</span></span> <span data-ttu-id="20873-108">オブジェクトごとに、次に <xref:System.Data.Linq.MemberChangeConflict> オブジェクトを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="20873-108">For each object, it then iterates through the <xref:System.Data.Linq.MemberChangeConflict> objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20873-109"><xref:System.Reflection> 情報を提供するには、<xref:System.Data.Linq.MemberChangeConflict.Member%2A> を含めます。</span><span class="sxs-lookup"><span data-stu-id="20873-109">Include <xref:System.Reflection> in order to provide <xref:System.Data.Linq.MemberChangeConflict.Member%2A> information.</span></span>  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="20873-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="20873-110">See also</span></span>

- [<span data-ttu-id="20873-111">方法: 変更の競合を管理する</span><span class="sxs-lookup"><span data-stu-id="20873-111">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)

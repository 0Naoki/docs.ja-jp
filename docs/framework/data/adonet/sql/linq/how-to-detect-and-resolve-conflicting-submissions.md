---
title: '方法: 検出および送信の競合を解決します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: ab1b56d409a3b185be15ebc8dc119a57038d55bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510508"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="eb653-102">方法: 検出および送信の競合を解決します。</span><span class="sxs-lookup"><span data-stu-id="eb653-102">How to: Detect and Resolve Conflicting Submissions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="eb653-103">には、複数のユーザーがデータベースを変更するために生じる競合を、検出および解決するための多くのリソースが用意されています。</span><span class="sxs-lookup"><span data-stu-id="eb653-103">provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="eb653-104">詳細については、「[方法 :変更の競合を管理](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)します。</span><span class="sxs-lookup"><span data-stu-id="eb653-104">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb653-105">例</span><span class="sxs-lookup"><span data-stu-id="eb653-105">Example</span></span>  
 <span data-ttu-id="eb653-106">次の例は、 `try` / `catch`キャッチ ブロックを<xref:System.Data.Linq.ChangeConflictException>例外。</span><span class="sxs-lookup"><span data-stu-id="eb653-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="eb653-107">各競合のエンティティおよびメンバー情報が、コンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb653-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb653-108">情報の取得をサポートするには、`using System.Reflection` ディレクティブ (Visual Basic の場合は `Imports System.Reflection`) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb653-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="eb653-109">詳細については、「 <xref:System.Reflection> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb653-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="eb653-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb653-110">See also</span></span>
- [<span data-ttu-id="eb653-111">データの変更と変更の送信</span><span class="sxs-lookup"><span data-stu-id="eb653-111">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="eb653-112">方法: 変更の競合を管理します。</span><span class="sxs-lookup"><span data-stu-id="eb653-112">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)

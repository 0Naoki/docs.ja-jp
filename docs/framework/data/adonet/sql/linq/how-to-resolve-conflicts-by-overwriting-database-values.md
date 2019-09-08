---
title: '方法: データベース値を上書きすることで競合を解決する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd6db0b8-c29c-48ff-b768-31d28e7a148c
ms.openlocfilehash: 1da2abcbbb3b87d44aa99016112d9ef2674912c6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781719"
---
# <a name="how-to-resolve-conflicts-by-overwriting-database-values"></a><span data-ttu-id="bd6fa-102">方法: データベース値を上書きすることで競合を解決する</span><span class="sxs-lookup"><span data-stu-id="bd6fa-102">How to: Resolve Conflicts by Overwriting Database Values</span></span>
<span data-ttu-id="bd6fa-103">変更を再送信する前に、データベース内の予期した値と実際の値の違いを調整するために、<xref:System.Data.Linq.RefreshMode.KeepCurrentValues> を使用してデータベース内の値を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="bd6fa-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> to overwrite database values.</span></span> <span data-ttu-id="bd6fa-104">詳細については[、「オプティミスティック同時実行制御」を参照してください。概要](optimistic-concurrency-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bd6fa-104">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd6fa-105">どの場合も、データベースから最新のデータを取得することで、まずクライアントのレコードが更新されます。</span><span class="sxs-lookup"><span data-stu-id="bd6fa-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="bd6fa-106">この処理によって、次の更新処理が同じコンカレンシー チェックで失敗することを防止できます。</span><span class="sxs-lookup"><span data-stu-id="bd6fa-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd6fa-107">例</span><span class="sxs-lookup"><span data-stu-id="bd6fa-107">Example</span></span>  
 <span data-ttu-id="bd6fa-108">このシナリオでは、ユーザー 1 が変更を送信しようとしたときに <xref:System.Data.Linq.ChangeConflictException> 例外がスローされます。これは、途中でユーザー 2 が Assistant 列と Department 列を変更していたためです。</span><span class="sxs-lookup"><span data-stu-id="bd6fa-108">In this scenario, an <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="bd6fa-109">次の表は、この状況を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd6fa-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="bd6fa-110">管理者</span><span class="sxs-lookup"><span data-stu-id="bd6fa-110">Manager</span></span>|<span data-ttu-id="bd6fa-111">Assistant</span><span class="sxs-lookup"><span data-stu-id="bd6fa-111">Assistant</span></span>|<span data-ttu-id="bd6fa-112">Department</span><span class="sxs-lookup"><span data-stu-id="bd6fa-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="bd6fa-113">ユーザー 1 およびユーザー 2 が照会した最初のデータベース状態</span><span class="sxs-lookup"><span data-stu-id="bd6fa-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="bd6fa-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="bd6fa-114">Alfreds</span></span>|<span data-ttu-id="bd6fa-115">Maria</span><span class="sxs-lookup"><span data-stu-id="bd6fa-115">Maria</span></span>|<span data-ttu-id="bd6fa-116">販売</span><span class="sxs-lookup"><span data-stu-id="bd6fa-116">Sales</span></span>|  
|<span data-ttu-id="bd6fa-117">ユーザー 1 が送信しようとした変更内容</span><span class="sxs-lookup"><span data-stu-id="bd6fa-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="bd6fa-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="bd6fa-118">Alfred</span></span>||<span data-ttu-id="bd6fa-119">マーケティング</span><span class="sxs-lookup"><span data-stu-id="bd6fa-119">Marketing</span></span>|  
|<span data-ttu-id="bd6fa-120">ユーザー 2 が既に送信した変更内容</span><span class="sxs-lookup"><span data-stu-id="bd6fa-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="bd6fa-121">Mary</span><span class="sxs-lookup"><span data-stu-id="bd6fa-121">Mary</span></span>|<span data-ttu-id="bd6fa-122">サービス</span><span class="sxs-lookup"><span data-stu-id="bd6fa-122">Service</span></span>|  
  
 <span data-ttu-id="bd6fa-123">ユーザー 1 は、この競合を解決するために、データベース値を現在のクライアント メンバー値で上書きすることに決めます。</span><span class="sxs-lookup"><span data-stu-id="bd6fa-123">User1 decides to resolve this conflict by overwriting database values with the current client member values.</span></span>  
  
 <span data-ttu-id="bd6fa-124">ユーザー 1 が <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> を使用して競合を解決すると、データベース内の結果は次の表のようになります。</span><span class="sxs-lookup"><span data-stu-id="bd6fa-124">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, the result in the database is as in following table:</span></span>  
  
||<span data-ttu-id="bd6fa-125">管理者</span><span class="sxs-lookup"><span data-stu-id="bd6fa-125">Manager</span></span>|<span data-ttu-id="bd6fa-126">Assistant</span><span class="sxs-lookup"><span data-stu-id="bd6fa-126">Assistant</span></span>|<span data-ttu-id="bd6fa-127">Department</span><span class="sxs-lookup"><span data-stu-id="bd6fa-127">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="bd6fa-128">競合解決後の新しい状態</span><span class="sxs-lookup"><span data-stu-id="bd6fa-128">New state after conflict resolution.</span></span>|<span data-ttu-id="bd6fa-129">Alfred</span><span class="sxs-lookup"><span data-stu-id="bd6fa-129">Alfred</span></span><br /><br /> <span data-ttu-id="bd6fa-130">(ユーザー 1 の値)</span><span class="sxs-lookup"><span data-stu-id="bd6fa-130">(from User1)</span></span>|<span data-ttu-id="bd6fa-131">Maria</span><span class="sxs-lookup"><span data-stu-id="bd6fa-131">Maria</span></span><br /><br /> <span data-ttu-id="bd6fa-132">(元の値)</span><span class="sxs-lookup"><span data-stu-id="bd6fa-132">(original)</span></span>|<span data-ttu-id="bd6fa-133">マーケティング</span><span class="sxs-lookup"><span data-stu-id="bd6fa-133">Marketing</span></span><br /><br /> <span data-ttu-id="bd6fa-134">(ユーザー 1 の値)</span><span class="sxs-lookup"><span data-stu-id="bd6fa-134">(from User1)</span></span>|  
  
 <span data-ttu-id="bd6fa-135">次のコード例は、データベース値を現在のクライアント メンバー値で上書きする方法を示しています</span><span class="sxs-lookup"><span data-stu-id="bd6fa-135">The following example code shows how to overwrite database values with the current client member values.</span></span> <span data-ttu-id="bd6fa-136">(個々のメンバーの競合に対する検査やカスタム ハンドリングは行われません)。</span><span class="sxs-lookup"><span data-stu-id="bd6fa-136">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="bd6fa-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd6fa-137">See also</span></span>

- [<span data-ttu-id="bd6fa-138">方法: 変更の競合を管理する</span><span class="sxs-lookup"><span data-stu-id="bd6fa-138">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)

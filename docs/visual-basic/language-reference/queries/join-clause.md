---
title: Join 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: b1551583079c66d1bf5f6963a42d5d24e518fff3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499426"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="3179c-102">Join 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3179c-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="3179c-103">2 つのコレクションを単一のコレクションに結合します。</span><span class="sxs-lookup"><span data-stu-id="3179c-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="3179c-104">結合操作は、一致するキーに基づいて、使用して、`Equals`演算子。</span><span class="sxs-lookup"><span data-stu-id="3179c-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3179c-105">構文</span><span class="sxs-lookup"><span data-stu-id="3179c-105">Syntax</span></span>  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="3179c-106">指定項目</span><span class="sxs-lookup"><span data-stu-id="3179c-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="3179c-107">必須。</span><span class="sxs-lookup"><span data-stu-id="3179c-107">Required.</span></span> <span data-ttu-id="3179c-108">結合するコレクションの制御変数。</span><span class="sxs-lookup"><span data-stu-id="3179c-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="3179c-109">必須。</span><span class="sxs-lookup"><span data-stu-id="3179c-109">Required.</span></span> <span data-ttu-id="3179c-110">左側にあるで識別されるコレクションと結合するコレクション、`Join`演算子。</span><span class="sxs-lookup"><span data-stu-id="3179c-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="3179c-111">A`Join`句は、別の入れ子にすることができます`Join`句、または、`Group Join`句。</span><span class="sxs-lookup"><span data-stu-id="3179c-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="3179c-112">任意。</span><span class="sxs-lookup"><span data-stu-id="3179c-112">Optional.</span></span> <span data-ttu-id="3179c-113">1 つ以上の追加`Join`句をさらに、クエリを絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="3179c-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="3179c-114">任意。</span><span class="sxs-lookup"><span data-stu-id="3179c-114">Optional.</span></span> <span data-ttu-id="3179c-115">1 つ以上の追加`Group Join`句をさらに、クエリを絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="3179c-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="3179c-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="3179c-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="3179c-117">必須。</span><span class="sxs-lookup"><span data-stu-id="3179c-117">Required.</span></span> <span data-ttu-id="3179c-118">結合するコレクションのキーを識別します。</span><span class="sxs-lookup"><span data-stu-id="3179c-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="3179c-119">使用する必要があります、`Equals`結合されているコレクションからキーを比較する演算子。</span><span class="sxs-lookup"><span data-stu-id="3179c-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="3179c-120">使用して、結合条件を組み合わせることができます、`And`演算子を複数のキーを識別します。</span><span class="sxs-lookup"><span data-stu-id="3179c-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="3179c-121">`key1` 左側にあるコレクションから必要があります、`Join`演算子。</span><span class="sxs-lookup"><span data-stu-id="3179c-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="3179c-122">`key2` 右側にあるコレクションから必要があります、`Join`演算子。</span><span class="sxs-lookup"><span data-stu-id="3179c-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="3179c-123">結合条件で使用されるキーは、コレクションの 1 つ以上の項目を含む式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3179c-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="3179c-124">ただし、それぞれのキー式では、該当するコレクションの項目のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3179c-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3179c-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="3179c-125">Remarks</span></span>  
 <span data-ttu-id="3179c-126">`Join`句が結合されているコレクションからのキー値と一致する 2 つのコレクションを結合します。</span><span class="sxs-lookup"><span data-stu-id="3179c-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="3179c-127">結果のコレクションの左側にある特定のコレクションからの値の任意の組み合わせを含めることができます、`Join`演算子とで識別されるコレクション、`Join`句。</span><span class="sxs-lookup"><span data-stu-id="3179c-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="3179c-128">によって指定された条件の結果のみが返されます、`Equals`演算子が満たされています。</span><span class="sxs-lookup"><span data-stu-id="3179c-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="3179c-129">これに相当する`INNER JOIN`sql です。</span><span class="sxs-lookup"><span data-stu-id="3179c-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="3179c-130">複数を使用する`Join`1 つのコレクションに 2 つ以上のコレクションを結合するクエリ内の句。</span><span class="sxs-lookup"><span data-stu-id="3179c-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="3179c-131">なしのコレクションを結合する暗黙の結合を行うことができます、`Join`句。</span><span class="sxs-lookup"><span data-stu-id="3179c-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="3179c-132">これを行うには、複数`In`内の句、`From`句を指定し、`Where`結合に使用するキー識別句。</span><span class="sxs-lookup"><span data-stu-id="3179c-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="3179c-133">使用することができます、`Group Join`句を単一の階層コレクションに結合します。</span><span class="sxs-lookup"><span data-stu-id="3179c-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="3179c-134">これは似ています、 `LEFT OUTER JOIN` sql です。</span><span class="sxs-lookup"><span data-stu-id="3179c-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3179c-135">例</span><span class="sxs-lookup"><span data-stu-id="3179c-135">Example</span></span>  
 <span data-ttu-id="3179c-136">次のコード例では、自分の注文と顧客のリストを結合する暗黙の結合を実行します。</span><span class="sxs-lookup"><span data-stu-id="3179c-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="3179c-137">例</span><span class="sxs-lookup"><span data-stu-id="3179c-137">Example</span></span>  
 <span data-ttu-id="3179c-138">次のコード例では、2 つのコレクションを結合を使用して、`Join`句。</span><span class="sxs-lookup"><span data-stu-id="3179c-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 <span data-ttu-id="3179c-139">この例には、次のような出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3179c-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="3179c-140">例</span><span class="sxs-lookup"><span data-stu-id="3179c-140">Example</span></span>  
 <span data-ttu-id="3179c-141">次のコード例では、2 つのコレクションを結合を使用して、 `Join` 2 つのキー列と句。</span><span class="sxs-lookup"><span data-stu-id="3179c-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 <span data-ttu-id="3179c-142">例では、次のような出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3179c-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="3179c-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="3179c-143">See Also</span></span>  
 [<span data-ttu-id="3179c-144">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="3179c-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="3179c-145">クエリ</span><span class="sxs-lookup"><span data-stu-id="3179c-145">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="3179c-146">Select 句</span><span class="sxs-lookup"><span data-stu-id="3179c-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="3179c-147">From 句</span><span class="sxs-lookup"><span data-stu-id="3179c-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="3179c-148">Group Join 句</span><span class="sxs-lookup"><span data-stu-id="3179c-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="3179c-149">WHERE 句</span><span class="sxs-lookup"><span data-stu-id="3179c-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)

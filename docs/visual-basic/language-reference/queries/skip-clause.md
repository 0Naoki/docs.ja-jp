---
title: Skip 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 615f98bf36d29c1f269d6866b1232ad33a5ae2f2
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925438"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="5d80a-102">Skip 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d80a-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="5d80a-103">コレクション内の指定された数の要素をバイパスし、残りの要素を返します。</span><span class="sxs-lookup"><span data-stu-id="5d80a-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d80a-104">構文</span><span class="sxs-lookup"><span data-stu-id="5d80a-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="5d80a-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="5d80a-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="5d80a-106">必須。</span><span class="sxs-lookup"><span data-stu-id="5d80a-106">Required.</span></span> <span data-ttu-id="5d80a-107">スキップするシーケンスの要素の数に評価される式または値。</span><span class="sxs-lookup"><span data-stu-id="5d80a-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d80a-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="5d80a-108">Remarks</span></span>  
 <span data-ttu-id="5d80a-109">`Skip`句によってクエリ結果一覧の先頭の要素をバイパスし、残りの要素を返します。</span><span class="sxs-lookup"><span data-stu-id="5d80a-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="5d80a-110">スキップする要素の数がで識別される、`count`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="5d80a-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="5d80a-111">使用することができます、`Skip`句、`Take`句をクエリの任意のセグメントからのデータの範囲を返します。</span><span class="sxs-lookup"><span data-stu-id="5d80a-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="5d80a-112">これを行うには、範囲の最初の要素のインデックスを渡す、`Skip`句とする範囲のサイズ、`Take`句。</span><span class="sxs-lookup"><span data-stu-id="5d80a-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="5d80a-113">使用すると、`Skip`クエリ句、する必要がありますも結果が可能にする順序で返されるように、`Skip`意図した結果をバイパスする句。</span><span class="sxs-lookup"><span data-stu-id="5d80a-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="5d80a-114">クエリの結果を順序付けの詳細については、次を参照してください。 [Order By 句](../../../visual-basic/language-reference/queries/order-by-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="5d80a-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="5d80a-115">使用することができます、`SkipWhile`句を指定した条件に応じて、特定の要素だけを無視するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d80a-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d80a-116">例</span><span class="sxs-lookup"><span data-stu-id="5d80a-116">Example</span></span>  
 <span data-ttu-id="5d80a-117">次のコード例では、`Skip`句と組み合わせて、`Take`句をページ内のクエリからデータを返します。</span><span class="sxs-lookup"><span data-stu-id="5d80a-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="5d80a-118">`GetCustomers`関数は、`Skip`値、および使用して、指定された開始インデックスを作成するまで、リスト内の顧客をバイパスする句、`Take`句にそのインデックス値から開始のページが返されます。</span><span class="sxs-lookup"><span data-stu-id="5d80a-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5d80a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d80a-119">See Also</span></span>  
 [<span data-ttu-id="5d80a-120">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="5d80a-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="5d80a-121">クエリ</span><span class="sxs-lookup"><span data-stu-id="5d80a-121">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="5d80a-122">Select 句</span><span class="sxs-lookup"><span data-stu-id="5d80a-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="5d80a-123">From 句</span><span class="sxs-lookup"><span data-stu-id="5d80a-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="5d80a-124">Order By 句</span><span class="sxs-lookup"><span data-stu-id="5d80a-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="5d80a-125">Skip While 句</span><span class="sxs-lookup"><span data-stu-id="5d80a-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="5d80a-126">Take 句</span><span class="sxs-lookup"><span data-stu-id="5d80a-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)

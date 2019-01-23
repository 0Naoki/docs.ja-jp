---
title: INTERSECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: 2fe7a9610863efab9fd332c40f7a644cd5c07e35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595956"
---
# <a name="intersect-entity-sql"></a><span data-ttu-id="3c85a-102">INTERSECT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3c85a-102">INTERSECT (Entity SQL)</span></span>
<span data-ttu-id="3c85a-103">INTERSECT オペランドの左右両方のクエリ式によって返される個別の値のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="3c85a-103">Returns a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="3c85a-104">すべての式は、 `expression`と同じ型であるか、共通の基本型または派生型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c85a-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c85a-105">構文</span><span class="sxs-lookup"><span data-stu-id="3c85a-105">Syntax</span></span>  
  
```  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="3c85a-106">引数</span><span class="sxs-lookup"><span data-stu-id="3c85a-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3c85a-107">コレクションを返す任意の有効なクエリ式。もう一方のクエリ式から返されたコレクションと比較されます。</span><span class="sxs-lookup"><span data-stu-id="3c85a-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c85a-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="3c85a-108">Return Value</span></span>  
 <span data-ttu-id="3c85a-109">`expression`と同じ型であるか、共通の基本データ型または派生型であるコレクション。</span><span class="sxs-lookup"><span data-stu-id="3c85a-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c85a-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="3c85a-110">Remarks</span></span>  
 <span data-ttu-id="3c85a-111">INTERSECT は、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の集合演算子の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="3c85a-111">INTERSECT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="3c85a-112">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のすべての集合演算子は左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="3c85a-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="3c85a-113">優先順位は、[!INCLUDE[esql](../../../../../../includes/esql-md.md)]集合演算子を参照してください[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c85a-113">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c85a-114">例</span><span class="sxs-lookup"><span data-stu-id="3c85a-114">Example</span></span>  
 <span data-ttu-id="3c85a-115">次の Entity SQL クエリでは、INTERSECT 演算子を使用して、INTERSECT オペランドの左右両方のクエリ式によって返される個別の値のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="3c85a-115">The following Entity SQL query uses the INTERSECT operator to return a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="3c85a-116">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="3c85a-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3c85a-117">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c85a-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="3c85a-118">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c85a-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="3c85a-119">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="3c85a-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#INTERSECT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#intersect)]  
  
## <a name="see-also"></a><span data-ttu-id="3c85a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c85a-120">See also</span></span>
- [<span data-ttu-id="3c85a-121">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="3c85a-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

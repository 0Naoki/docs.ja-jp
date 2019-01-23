---
title: '!= (等しくない) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: d5e59fe61dbc05a48e98f5720dca446482b9968e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568136"
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="4583a-102">!= (等しくない) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4583a-102">!= (Not Equal To) (Entity SQL)</span></span>
<span data-ttu-id="4583a-103">2 つの式を比較して、左の式の値が右の式の値と等しくないかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="4583a-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="4583a-104">!= (等しくない) 演算子は、機能的には <> 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="4583a-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4583a-105">構文</span><span class="sxs-lookup"><span data-stu-id="4583a-105">Syntax</span></span>  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="4583a-106">引数</span><span class="sxs-lookup"><span data-stu-id="4583a-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="4583a-107">任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="4583a-107">Any valid expression.</span></span> <span data-ttu-id="4583a-108">両方の式とも、暗黙的に変換可能なデータ型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="4583a-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4583a-109">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="4583a-109">Result Types</span></span>  
 <span data-ttu-id="4583a-110">左の式が右の式と等しくない場合は`true` 、等しい場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="4583a-110">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4583a-111">例</span><span class="sxs-lookup"><span data-stu-id="4583a-111">Example</span></span>  
 <span data-ttu-id="4583a-112">次の Entity SQL クエリは != 演算子を使用して 2 つの式を比較し、左の式が右の式と等しくないかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="4583a-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="4583a-113">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="4583a-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4583a-114">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4583a-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="4583a-115">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="4583a-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="4583a-116">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="4583a-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="4583a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4583a-117">See also</span></span>
- [<span data-ttu-id="4583a-118">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="4583a-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

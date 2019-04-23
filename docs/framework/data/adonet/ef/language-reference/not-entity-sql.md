---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 51d3bdbc4adb0b5fd6275629219698dd9b42fa86
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306769"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="44412-103">!</span><span class="sxs-lookup"><span data-stu-id="44412-103">!</span></span> <span data-ttu-id="44412-104">(NOT) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="44412-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="44412-105">`Boolean` 型の式を否定します。</span><span class="sxs-lookup"><span data-stu-id="44412-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44412-106">構文</span><span class="sxs-lookup"><span data-stu-id="44412-106">Syntax</span></span>  
  
```  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="44412-107">引数</span><span class="sxs-lookup"><span data-stu-id="44412-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="44412-108">ブール値を返す任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="44412-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44412-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="44412-109">Remarks</span></span>  
 <span data-ttu-id="44412-110">感嘆符 (!) には、NOT 演算子と同じ機能があります。</span><span class="sxs-lookup"><span data-stu-id="44412-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44412-111">例</span><span class="sxs-lookup"><span data-stu-id="44412-111">Example</span></span>  
 <span data-ttu-id="44412-112">次の Entity SQL クエリでは、NOT 演算子を使用して `Boolean` 型の式を否定します。</span><span class="sxs-lookup"><span data-stu-id="44412-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="44412-113">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="44412-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="44412-114">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="44412-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="44412-115">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="44412-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="44412-116">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="44412-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## <a name="see-also"></a><span data-ttu-id="44412-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="44412-117">See also</span></span>

- [<span data-ttu-id="44412-118">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="44412-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

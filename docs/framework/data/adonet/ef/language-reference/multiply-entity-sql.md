---
title: '* (乗算)(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
ms.openlocfilehash: 68544823d2279b76920e057829fc61a469d39730
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493860"
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="9f929-102">\* (乗算) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9f929-102">\* (Multiply) (Entity SQL)</span></span>
<span data-ttu-id="9f929-103">2 つの式を乗算します。</span><span class="sxs-lookup"><span data-stu-id="9f929-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f929-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f929-104">Syntax</span></span>  
  
```  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="9f929-105">引数</span><span class="sxs-lookup"><span data-stu-id="9f929-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9f929-106">任意の数値データ型の有効な式。</span><span class="sxs-lookup"><span data-stu-id="9f929-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="9f929-107">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="9f929-107">Result Types</span></span>  
 <span data-ttu-id="9f929-108">2 つの引数の暗黙の型の昇格の結果であるデータ型。</span><span class="sxs-lookup"><span data-stu-id="9f929-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="9f929-109">暗黙的な型の上位変換の詳細については、次を参照してください。[型システム](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="9f929-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f929-110">例</span><span class="sxs-lookup"><span data-stu-id="9f929-110">Example</span></span>  
 <span data-ttu-id="9f929-111">次の Entity SQL クエリでは、\* 算術演算子を使用して 2 つの数値を乗算します。</span><span class="sxs-lookup"><span data-stu-id="9f929-111">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="9f929-112">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="9f929-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9f929-113">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9f929-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9f929-114">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="9f929-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="9f929-115">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="9f929-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTIPLY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="9f929-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f929-116">See also</span></span>
- [<span data-ttu-id="9f929-117">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="9f929-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: abe47f8c72abe13bd5c27fe10a412ff94ab861cf
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855140"
---
# <a name="deref-entity-sql"></a><span data-ttu-id="83a99-102">DEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="83a99-102">DEREF (Entity SQL)</span></span>
<span data-ttu-id="83a99-103">参照値を逆参照し、その逆参照の結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="83a99-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83a99-104">構文</span><span class="sxs-lookup"><span data-stu-id="83a99-104">Syntax</span></span>  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a><span data-ttu-id="83a99-105">引数</span><span class="sxs-lookup"><span data-stu-id="83a99-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="83a99-106">コレクションを返す任意の有効なクエリ式。</span><span class="sxs-lookup"><span data-stu-id="83a99-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83a99-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="83a99-107">Return Value</span></span>  
 <span data-ttu-id="83a99-108">参照されるエンティティの値。</span><span class="sxs-lookup"><span data-stu-id="83a99-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83a99-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="83a99-109">Remarks</span></span>  
 <span data-ttu-id="83a99-110">DEREF 演算子は参照値を逆参照し、その逆参照の結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="83a99-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="83a99-111">たとえば場合、 `r` ref 型の参照は、\<T >、`Deref(r)`型の式は、`T`によって参照されるエンティティを生成する`r`します。</span><span class="sxs-lookup"><span data-stu-id="83a99-111">For example, if `r` is a reference of type ref\<T>, `Deref(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="83a99-112">参照値が null または未解決 (つまり、参照先が存在しない) の場合、DEREF 演算子の結果は null になります。</span><span class="sxs-lookup"><span data-stu-id="83a99-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83a99-113">例</span><span class="sxs-lookup"><span data-stu-id="83a99-113">Example</span></span>  
 <span data-ttu-id="83a99-114">次の [!INCLUDE[esql](../../../../../../includes/esql-md.md)] クエリでは、DEREF 演算子を使用して参照値を逆参照し、その逆参照の結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="83a99-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="83a99-115">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="83a99-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="83a99-116">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="83a99-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="83a99-117">」の手順に従って[方法: PrimitiveType 結果が返されますそのクエリを実行する](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="83a99-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="83a99-118">次のクエリを引数として ExecutePrimitiveTypeQuery メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="83a99-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="83a99-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="83a99-119">See Also</span></span>  
 [<span data-ttu-id="83a99-120">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="83a99-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="83a99-121">REF</span><span class="sxs-lookup"><span data-stu-id="83a99-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [<span data-ttu-id="83a99-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="83a99-122">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="83a99-123">KEY</span><span class="sxs-lookup"><span data-stu-id="83a99-123">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="83a99-124">NULL 値が許容される構造化型</span><span class="sxs-lookup"><span data-stu-id="83a99-124">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)

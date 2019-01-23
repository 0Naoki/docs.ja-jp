---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 15a78558789ef998d31d704a3fcfbf43dc364757
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517033"
---
# <a name="ref-entity-sql"></a><span data-ttu-id="14dd5-102">REF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="14dd5-102">REF (Entity SQL)</span></span>
<span data-ttu-id="14dd5-103">エンティティ インスタンスへの参照を返します。</span><span class="sxs-lookup"><span data-stu-id="14dd5-103">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14dd5-104">構文</span><span class="sxs-lookup"><span data-stu-id="14dd5-104">Syntax</span></span>  
  
```  
REF( expression )   
```  
  
## <a name="arguments"></a><span data-ttu-id="14dd5-105">引数</span><span class="sxs-lookup"><span data-stu-id="14dd5-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="14dd5-106">エンティティ型のインスタンスを生成する任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="14dd5-106">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14dd5-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="14dd5-107">Return Value</span></span>  
 <span data-ttu-id="14dd5-108">指定されたエンティティ インスタンスへの参照。</span><span class="sxs-lookup"><span data-stu-id="14dd5-108">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14dd5-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="14dd5-109">Remarks</span></span>  
 <span data-ttu-id="14dd5-110">エンティティ参照は、エンティティ キーとエンティティ セット名で構成されます。</span><span class="sxs-lookup"><span data-stu-id="14dd5-110">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="14dd5-111">異なるエンティティ セットが同じエンティティ型に基づくことができるので、特定のエンティティ キーが複数のエンティティ セットで使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="14dd5-111">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="14dd5-112">ただし、エンティティ参照は常に一意です。</span><span class="sxs-lookup"><span data-stu-id="14dd5-112">However, an entity reference is always unique.</span></span> <span data-ttu-id="14dd5-113">入力式が永続エンティティを表す場合、このエンティティへの参照が返されます。</span><span class="sxs-lookup"><span data-stu-id="14dd5-113">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="14dd5-114">入力式が永続エンティティではない場合は、NULL 参照が返されます。</span><span class="sxs-lookup"><span data-stu-id="14dd5-114">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="14dd5-115">プロパティ抽出演算子 (.) を使用してエンティティのプロパティにアクセスすると、参照は自動的に逆参照されます。</span><span class="sxs-lookup"><span data-stu-id="14dd5-115">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14dd5-116">例</span><span class="sxs-lookup"><span data-stu-id="14dd5-116">Example</span></span>  
 <span data-ttu-id="14dd5-117">次の Entity SQL クエリは、REF 演算子を使用して入力エンティティ引数の参照を返します。</span><span class="sxs-lookup"><span data-stu-id="14dd5-117">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="14dd5-118">プロパティ抽出演算子 (.) を使用して Product エンティティのプロパティにアクセスすることにより、同じクエリでこの参照が逆参照されます。</span><span class="sxs-lookup"><span data-stu-id="14dd5-118">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="14dd5-119">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="14dd5-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="14dd5-120">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="14dd5-120">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="14dd5-121">」の手順に従って[方法。PrimitiveType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="14dd5-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="14dd5-122">次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="14dd5-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="14dd5-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="14dd5-123">See also</span></span>
- [<span data-ttu-id="14dd5-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="14dd5-124">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)
- [<span data-ttu-id="14dd5-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="14dd5-125">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)
- [<span data-ttu-id="14dd5-126">KEY</span><span class="sxs-lookup"><span data-stu-id="14dd5-126">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)
- [<span data-ttu-id="14dd5-127">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="14dd5-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="14dd5-128">型定義</span><span class="sxs-lookup"><span data-stu-id="14dd5-128">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)

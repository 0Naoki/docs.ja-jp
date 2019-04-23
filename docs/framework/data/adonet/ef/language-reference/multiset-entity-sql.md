---
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: 44e411b8ae2f43bf3a729ac091ffd1eb4c462c63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59303038"
---
# <a name="multiset-entity-sql"></a><span data-ttu-id="366e9-102">MULTISET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="366e9-102">MULTISET (Entity SQL)</span></span>
<span data-ttu-id="366e9-103">値のリストからマルチセットのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="366e9-103">Creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="366e9-104">MULTISET コンストラクターの値はすべて、互換性のある型 `T`である必要があります。</span><span class="sxs-lookup"><span data-stu-id="366e9-104">All the values in the MULTISET constructor must be of a compatible type `T`.</span></span> <span data-ttu-id="366e9-105">空のマルチセット コンストラクターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="366e9-105">Empty multiset constructors are not allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="366e9-106">構文</span><span class="sxs-lookup"><span data-stu-id="366e9-106">Syntax</span></span>  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a><span data-ttu-id="366e9-107">引数</span><span class="sxs-lookup"><span data-stu-id="366e9-107">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="366e9-108">任意の有効な値のリスト。</span><span class="sxs-lookup"><span data-stu-id="366e9-108">Any valid list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="366e9-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="366e9-109">Return Value</span></span>  
 <span data-ttu-id="366e9-110">型 MULTISET のコレクション\<T >。</span><span class="sxs-lookup"><span data-stu-id="366e9-110">A collection of type MULTISET\<T>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="366e9-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="366e9-111">Remarks</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="366e9-112">には、行コンストラクター、オブジェクト コンストラクター、およびマルチセット (またはコレクション) コンストラクターの 3 種類のコンストラクターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="366e9-112">provides three kinds of constructors: row constructors, object constructors, and multiset (or collection) constructors.</span></span> <span data-ttu-id="366e9-113">詳細については、次を参照してください。[構築型](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="366e9-113">For more information, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
 <span data-ttu-id="366e9-114">マルチセット コンストラクターは、値のリストからマルチセットのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="366e9-114">The multiset constructor creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="366e9-115">このコンストラクターの値はすべて、互換性のある型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="366e9-115">All the values in the constructor must be of a compatible type.</span></span>  
  
 <span data-ttu-id="366e9-116">たとえば、次の式は整数のマルチセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="366e9-116">For example, the following expression creates a multiset of integers.</span></span>  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  <span data-ttu-id="366e9-117">入れ子になったマルチセット リテラルは、ラッピング multiset がある 1 つの multiset の要素です。 ときにのみサポートします。たとえば、`{{1, 2, 3}}`します。</span><span class="sxs-lookup"><span data-stu-id="366e9-117">Nested multiset literals are only supported when a wrapping multiset has a single multiset element; for example, `{{1, 2, 3}}`.</span></span> <span data-ttu-id="366e9-118">複数のマルチセット要素が外側のマルチセットに含まれている場合 ( `{{1, 2}, {3, 4}}`など)、入れ子になったマルチセット リテラルはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="366e9-118">When the wrapping multiset has multiple multiset elements (for example, `{{1, 2}, {3, 4}}`), nested multiset literals are not supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="366e9-119">例</span><span class="sxs-lookup"><span data-stu-id="366e9-119">Example</span></span>  
 <span data-ttu-id="366e9-120">次の Entity SQL クエリでは、MULTISET 演算子を使用して、値のリストからマルチセットのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="366e9-120">The following Entity SQL query uses the MULTISET operator to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="366e9-121">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="366e9-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="366e9-122">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="366e9-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="366e9-123">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="366e9-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="366e9-124">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="366e9-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a><span data-ttu-id="366e9-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="366e9-125">See also</span></span>

- [<span data-ttu-id="366e9-126">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="366e9-126">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)
- [<span data-ttu-id="366e9-127">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="366e9-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

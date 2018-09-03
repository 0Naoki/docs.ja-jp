---
title: TREAT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
ms.openlocfilehash: c3291dc6d5bc79430c8bf011ee6a2f4dc213ffad
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486897"
---
# <a name="treat-entity-sql"></a><span data-ttu-id="bc449-102">TREAT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bc449-102">TREAT (Entity SQL)</span></span>
<span data-ttu-id="bc449-103">特定の基本データ型のオブジェクトを指定の派生型のオブジェクトとして処理します。</span><span class="sxs-lookup"><span data-stu-id="bc449-103">Treats an object of a particular base type as an object of the specified derived type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc449-104">構文</span><span class="sxs-lookup"><span data-stu-id="bc449-104">Syntax</span></span>  
  
```  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a><span data-ttu-id="bc449-105">引数</span><span class="sxs-lookup"><span data-stu-id="bc449-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="bc449-106">エンティティを返す任意の有効なクエリ式。</span><span class="sxs-lookup"><span data-stu-id="bc449-106">Any valid query expression that returns an entity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc449-107">指定の式の型は、特定のデータ型のサブタイプである必要があります。または、データ型は式の型のサブタイプである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc449-107">The type of the specified expression must be a subtype of the specified data type, or the data type must be a subtype of the type of expression.</span></span>  
  
 `type`  
 <span data-ttu-id="bc449-108">エンティティ型。</span><span class="sxs-lookup"><span data-stu-id="bc449-108">An entity type.</span></span> <span data-ttu-id="bc449-109">型は名前空間で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc449-109">The type must be qualified by a namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc449-110">指定の式は、特定のデータ型のサブタイプである必要があります。または、データ型は式のサブタイプである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc449-110">The specified expression must be a subtype of the specified data type, or the data type must be a subtype of the expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc449-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="bc449-111">Return Value</span></span>  
 <span data-ttu-id="bc449-112">指定されたデータ型の値。</span><span class="sxs-lookup"><span data-stu-id="bc449-112">A value of the specified data type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc449-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="bc449-113">Remarks</span></span>  
 <span data-ttu-id="bc449-114">TREAT は関連クラス間でキャストを実行するために使用します。</span><span class="sxs-lookup"><span data-stu-id="bc449-114">TREAT is used to perform upcasting between related classes.</span></span> <span data-ttu-id="bc449-115">たとえば、 `Employee` が `Person` から派生し、p が `Person`型である場合、 `TREAT(p AS NamespaceName.Employee)` はジェネリック型の `Person` インスタンスを `Employee`にキャストします。つまり、p を `Employee`として処理できます。</span><span class="sxs-lookup"><span data-stu-id="bc449-115">For example, if `Employee` derives from `Person` and p is of type `Person`, `TREAT(p AS NamespaceName.Employee)` upcasts a generic `Person` instance to `Employee`; that is, it allows you to treat p as `Employee`.</span></span>  
  
 <span data-ttu-id="bc449-116">TREAT は、次のようにクエリを実行できる継承シナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc449-116">TREAT is used in inheritance scenarios where you can do a query like the following:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)   
```  
  
 <span data-ttu-id="bc449-117">このクエリは、 `Person` エンティティを `Employee` 型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="bc449-117">This query upcasts `Person` entities to the `Employee` type.</span></span> <span data-ttu-id="bc449-118">p の値が実際には `Employee`型でない場合、この式は `null`値を返します。</span><span class="sxs-lookup"><span data-stu-id="bc449-118">If the value of p is not actually of type `Employee`, the expression yields the value `null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc449-119">指定された式`Employee`指定したデータ型のサブタイプである必要があります`Person`データ型の式のサブタイプである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc449-119">The specified expression `Employee` must be a subtype of the specified data type `Person`, or the data type must be a subtype of the expression.</span></span> <span data-ttu-id="bc449-120">そうでない場合は、コンパイル時にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="bc449-120">Otherwise, the expression will result in a compile-time error.</span></span>  
  
 <span data-ttu-id="bc449-121">次の表に、いくつかの通常パターンと一般的でないパターンにおける TREAT の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="bc449-121">The following table shows the behavior of treat over some typical patterns and some less common patterns.</span></span> <span data-ttu-id="bc449-122">すべての例外はクライアント側にスローされてから、プロバイダーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="bc449-122">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="bc449-123">パターン</span><span class="sxs-lookup"><span data-stu-id="bc449-123">Pattern</span></span>|<span data-ttu-id="bc449-124">動作</span><span class="sxs-lookup"><span data-stu-id="bc449-124">Behavior</span></span>|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|<span data-ttu-id="bc449-125">`DbNull`を返します。</span><span class="sxs-lookup"><span data-stu-id="bc449-125">Returns `DbNull`.</span></span>|  
|`TREAT (null AS ComplexType)`|<span data-ttu-id="bc449-126">例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="bc449-126">Throws an exception.</span></span>|  
|`TREAT (null AS RowType)`|<span data-ttu-id="bc449-127">例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="bc449-127">Throws an exception/</span></span>|  
|`TREAT (EntityType AS EntityType)`|<span data-ttu-id="bc449-128">`EntityType` または `null`を返します。</span><span class="sxs-lookup"><span data-stu-id="bc449-128">Returns `EntityType` or `null`.</span></span>|  
|`TREAT (ComplexType AS ComplexType)`|<span data-ttu-id="bc449-129">例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="bc449-129">Throws an exception.</span></span>|  
|`TREAT (RowType AS RowType)`|<span data-ttu-id="bc449-130">例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="bc449-130">Throws an exception.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bc449-131">例</span><span class="sxs-lookup"><span data-stu-id="bc449-131">Example</span></span>  
 <span data-ttu-id="bc449-132">次の [!INCLUDE[esql](../../../../../../includes/esql-md.md)] クエリでは、TREAT 演算子を使用して、Course 型のオブジェクトを OnsiteCourse 型のオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="bc449-132">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="bc449-133">クエリに基づいていますが、 [School モデル](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac)します。</span><span class="sxs-lookup"><span data-stu-id="bc449-133">The query is based on the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="bc449-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc449-134">See Also</span></span>  
 [<span data-ttu-id="bc449-135">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="bc449-135">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="bc449-136">NULL 値が許容される構造化型</span><span class="sxs-lookup"><span data-stu-id="bc449-136">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)

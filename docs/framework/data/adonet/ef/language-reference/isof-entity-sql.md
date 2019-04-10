---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: 097d6e7d452ee62a2c8934d2c5fcfdddbeaffc73
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195749"
---
# <a name="isof-entity-sql"></a><span data-ttu-id="81c82-102">ISOF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="81c82-102">ISOF (Entity SQL)</span></span>
<span data-ttu-id="81c82-103">式の型が指定の型であるか、またはそのサブタイプであるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="81c82-103">Determines whether the type of an expression is of the specified type or one of its subtypes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c82-104">構文</span><span class="sxs-lookup"><span data-stu-id="81c82-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="81c82-105">引数</span><span class="sxs-lookup"><span data-stu-id="81c82-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="81c82-106">型を判断するための任意の有効なクエリ式。</span><span class="sxs-lookup"><span data-stu-id="81c82-106">Any valid query expression to determine the type of.</span></span>  
  
 <span data-ttu-id="81c82-107">NOT</span><span class="sxs-lookup"><span data-stu-id="81c82-107">NOT</span></span>  
 <span data-ttu-id="81c82-108">IS OF の EDM.Boolean の結果を否定します。</span><span class="sxs-lookup"><span data-stu-id="81c82-108">Negates the EDM.Boolean result of IS OF.</span></span>  
  
 <span data-ttu-id="81c82-109">ONLY</span><span class="sxs-lookup"><span data-stu-id="81c82-109">ONLY</span></span>  
 <span data-ttu-id="81c82-110">`true` が `expression` 型であり、そのサブタイプでない場合に限り、IS OF が `type` を返すことを指定します。</span><span class="sxs-lookup"><span data-stu-id="81c82-110">Specifies that IS OF returns `true` only if `expression` is of type `type` and not any of one its subtypes.</span></span>  
  
 `type`  
 <span data-ttu-id="81c82-111">`expression` を判定するための型。</span><span class="sxs-lookup"><span data-stu-id="81c82-111">The type to test `expression` against.</span></span> <span data-ttu-id="81c82-112">型は名前空間で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81c82-112">The type must be namespace-qualified.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81c82-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="81c82-113">Return Value</span></span>  
 `true` <span data-ttu-id="81c82-114">場合`expression`は型の T と T が基本型、または派生型の`type`; 場合は null`expression`が実行時に null。 それ以外`false`します。</span><span class="sxs-lookup"><span data-stu-id="81c82-114">if `expression` is of type T and T is either a base type, or a derived type of `type`; null if `expression` is null at runtime; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81c82-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="81c82-115">Remarks</span></span>  
 <span data-ttu-id="81c82-116">式`expression IS NOT OF (type)`と`expression IS NOT OF (ONLY type)`を構文的に等価`NOT (expression IS OF (type))`と`NOT (expression IS OF (ONLY type))`、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="81c82-116">The expressions `expression IS NOT OF (type)` and `expression IS NOT OF (ONLY type)` are syntactically equivalent to `NOT (expression IS OF (type))` and `NOT (expression IS OF (ONLY type))`, respectively.</span></span>  
  
 <span data-ttu-id="81c82-117">次の表に、いくつかの通常およびコーナー パターンにおける `IS OF` 演算子の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="81c82-117">The following table shows the behavior of `IS OF` operator over some typical- and corner patterns.</span></span> <span data-ttu-id="81c82-118">すべての例外はクライアント側にスローされてから、プロバイダーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="81c82-118">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="81c82-119">パターン</span><span class="sxs-lookup"><span data-stu-id="81c82-119">Pattern</span></span>|<span data-ttu-id="81c82-120">動作</span><span class="sxs-lookup"><span data-stu-id="81c82-120">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="81c82-121">null IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="81c82-121">null IS OF (EntityType)</span></span>|<span data-ttu-id="81c82-122">スロー</span><span class="sxs-lookup"><span data-stu-id="81c82-122">Throws</span></span>|  
|<span data-ttu-id="81c82-123">null IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="81c82-123">null IS OF (ComplexType)</span></span>|<span data-ttu-id="81c82-124">スロー</span><span class="sxs-lookup"><span data-stu-id="81c82-124">Throws</span></span>|  
|<span data-ttu-id="81c82-125">null IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="81c82-125">null IS OF (RowType)</span></span>|<span data-ttu-id="81c82-126">スロー</span><span class="sxs-lookup"><span data-stu-id="81c82-126">Throws</span></span>|  
|<span data-ttu-id="81c82-127">TREAT (null AS EntityType) IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="81c82-127">TREAT (null AS EntityType) IS OF (EntityType)</span></span>|<span data-ttu-id="81c82-128">DBNull を返します。</span><span class="sxs-lookup"><span data-stu-id="81c82-128">Returns DBNull</span></span>|  
|<span data-ttu-id="81c82-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="81c82-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span></span>|<span data-ttu-id="81c82-130">スロー</span><span class="sxs-lookup"><span data-stu-id="81c82-130">Throws</span></span>|  
|<span data-ttu-id="81c82-131">TREAT (null AS RowType) IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="81c82-131">TREAT (null AS RowType) IS OF (RowType)</span></span>|<span data-ttu-id="81c82-132">スロー</span><span class="sxs-lookup"><span data-stu-id="81c82-132">Throws</span></span>|  
|<span data-ttu-id="81c82-133">EntityType IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="81c82-133">EntityType IS OF (EntityType)</span></span>|<span data-ttu-id="81c82-134">true または false を返します。</span><span class="sxs-lookup"><span data-stu-id="81c82-134">Returns true/false</span></span>|  
|<span data-ttu-id="81c82-135">ComplexType IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="81c82-135">ComplexType IS OF (ComplexType)</span></span>|<span data-ttu-id="81c82-136">スロー</span><span class="sxs-lookup"><span data-stu-id="81c82-136">Throws</span></span>|  
|<span data-ttu-id="81c82-137">RowType IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="81c82-137">RowType IS OF (RowType)</span></span>|<span data-ttu-id="81c82-138">スロー</span><span class="sxs-lookup"><span data-stu-id="81c82-138">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="81c82-139">例</span><span class="sxs-lookup"><span data-stu-id="81c82-139">Example</span></span>  
 <span data-ttu-id="81c82-140">次[!INCLUDE[esql](../../../../../../includes/esql-md.md)]クエリが、IS OF 演算子を使用して、クエリ式の種類を判断し、TREAT 演算子を使用して、Course 型のオブジェクトを OnsiteCourse 型のオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="81c82-140">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS OF operator to determine the type of a query expression, and then uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="81c82-141">このクエリは、 [School モデル](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100))に基づいています。</span><span class="sxs-lookup"><span data-stu-id="81c82-141">The query is based on the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="81c82-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="81c82-142">See also</span></span>

- [<span data-ttu-id="81c82-143">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="81c82-143">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

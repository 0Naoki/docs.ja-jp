---
title: コンストラクター (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41fa7bde-8d20-4a3f-a3d2-fb791e128010
ms.openlocfilehash: 53aa7fcc82a476c8b8bd87b059e08bee6741c0d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073781"
---
# <a name="constructing-types-entity-sql"></a><span data-ttu-id="91a71-102">コンストラクター (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="91a71-102">Constructing Types (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="91a71-103">次の 3 つの種類のコンス トラクターを提供します。 行コンス トラクター、名前付きの型のコンス トラクター、およびコレクション コンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="91a71-103">provides three kinds of constructors: row constructors, named type constructors, and collection constructors.</span></span>  
  
## <a name="row-constructors"></a><span data-ttu-id="91a71-104">行コンストラクター</span><span class="sxs-lookup"><span data-stu-id="91a71-104">Row Constructors</span></span>  
 <span data-ttu-id="91a71-105">1 つまたは複数の値から構造的に型付けされた匿名レコードを構築するには、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] の行コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="91a71-105">You use row constructors in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="91a71-106">行コンストラクターの結果の型は、行の構築に使用された値の型に対応するフィールド型を持つ行型です。</span><span class="sxs-lookup"><span data-stu-id="91a71-106">The result type of a row constructor is a row type whose field types correspond to the types of the values used to construct the row.</span></span> <span data-ttu-id="91a71-107">たとえば、次の式は型の値を構築します`Record(a int, b string, c int)`:。</span><span class="sxs-lookup"><span data-stu-id="91a71-107">For example, the following expression constructs a value of type `Record(a int, b string, c int)`:</span></span>  
  
 `ROW(1 AS a, "abc" AS b, a + 34 AS c)`  
  
 <span data-ttu-id="91a71-108">行コンストラクターで式の別名が指定されていなければ、Entity Framework は別名の生成を試みます。</span><span class="sxs-lookup"><span data-stu-id="91a71-108">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="91a71-109">詳細については、「別名規則」セクションを参照してください。[識別子](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="91a71-109">For more information, see the "Aliasing Rules" section in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="91a71-110">次の規則は、行コンストラクターで別名を定義する式に適用されます。</span><span class="sxs-lookup"><span data-stu-id="91a71-110">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
-   <span data-ttu-id="91a71-111">行コンストラクターの式で同じコンストラクターの他の別名を参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="91a71-111">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
-   <span data-ttu-id="91a71-112">同じ行コンストラクター内の 2 つの式に同じ別名を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="91a71-112">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="91a71-113">行コンス トラクターの詳細については、次を参照してください。[行](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="91a71-113">For more information about row constructors, see [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).</span></span>  
  
## <a name="collection-constructors"></a><span data-ttu-id="91a71-114">コレクション コンストラクター</span><span class="sxs-lookup"><span data-stu-id="91a71-114">Collection Constructors</span></span>  
 <span data-ttu-id="91a71-115">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のコレクション コンストラクターを使用して、値のリストからマルチセットのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="91a71-115">You use collection constructors in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="91a71-116">コンストラクターのすべての値は、相互に互換性のある型 `T` でなければなりません。また、コンストラクターは `Multiset<T>` 型のコレクションを生成します。</span><span class="sxs-lookup"><span data-stu-id="91a71-116">All the values in the constructor must be of mutually compatible type `T`, and the constructor produces a collection of type `Multiset<T>`.</span></span> <span data-ttu-id="91a71-117">たとえば、次の式は整数のコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="91a71-117">For example, the following expression creates a collection of integers:</span></span>  
  
 `Multiset(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
 <span data-ttu-id="91a71-118">要素の型が確認できないため、空のマルチセット コンストラクターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="91a71-118">Empty multiset constructors are not allowed because the type of the elements cannot be determined.</span></span> <span data-ttu-id="91a71-119">次の式は無効です。</span><span class="sxs-lookup"><span data-stu-id="91a71-119">The following is not valid:</span></span>  
  
 `multiset() {}`  
  
 <span data-ttu-id="91a71-120">詳細については、次を参照してください。 [MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="91a71-120">For more information, see [MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md).</span></span>  
  
## <a name="named-type-constructors-namedtype-initializers"></a><span data-ttu-id="91a71-121">名前付きの型コンストラクター (NamedType 初期化子)</span><span class="sxs-lookup"><span data-stu-id="91a71-121">Named Type Constructors (NamedType Initializers)</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="91a71-122">型コンス トラクター (初期化子) の複合型の名前付きインスタンスを作成し、エンティティ型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="91a71-122">allows type constructors (initializers) to create instances of named complex types and entity types.</span></span> <span data-ttu-id="91a71-123">たとえば、次の式は `Person` 型のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="91a71-123">For example, the following expression creates an instance of a `Person` type.</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="91a71-124">次の式は、複合型のインスタンスを作成する式です。</span><span class="sxs-lookup"><span data-stu-id="91a71-124">The following expression creates an instance of a complex type.</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="91a71-125">次の式は、入れ子になった複合型のインスタンスを作成する式です。</span><span class="sxs-lookup"><span data-stu-id="91a71-125">The following expression creates an instance of a nested complex type.</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="91a71-126">次の式は、入れ子になった複合型を持つエンティティのインスタンスを作成する式です。</span><span class="sxs-lookup"><span data-stu-id="91a71-126">The following expression creates an instance of an entity with a nested complex type.</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="91a71-127">次の例は、複合型のプロパティを null に初期化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="91a71-127">The following example shows how to initialize a property of a complex type to null.</span></span> `MyModel.ZipCode(‘98118’, null)`  
  
 <span data-ttu-id="91a71-128">コンストラクターに対する引数は、型の属性の宣言と同じ順序であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="91a71-128">The arguments to the constructor are assumed to be in the same order as the declaration of the attributes of the type.</span></span>  
  
 <span data-ttu-id="91a71-129">詳細については、次を参照してください。[という名前の型コンス トラクター](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="91a71-129">For more information, see [Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a71-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="91a71-130">See also</span></span>

- [<span data-ttu-id="91a71-131">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="91a71-131">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="91a71-132">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="91a71-132">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="91a71-133">型システム</span><span class="sxs-lookup"><span data-stu-id="91a71-133">Type System</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)

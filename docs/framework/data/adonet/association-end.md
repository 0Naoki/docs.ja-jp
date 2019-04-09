---
title: アソシエーション End
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: e549254533f8362ce3475fb3aa5dbaffb3e900e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108291"
---
# <a name="association-end"></a><span data-ttu-id="f8b59-102">アソシエーション End</span><span class="sxs-lookup"><span data-stu-id="f8b59-102">association end</span></span>
<span data-ttu-id="f8b59-103">*アソシエーション end*を識別、[エンティティ型](../../../../docs/framework/data/adonet/entity-type.md)の一端を[アソシエーション](../../../../docs/framework/data/adonet/association-type.md)とアソシエーションの end に存在できるインスタンスを入力するエンティティの数。</span><span class="sxs-lookup"><span data-stu-id="f8b59-103">An *association end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) on one end of an [association](../../../../docs/framework/data/adonet/association-type.md) and the number of entity type instances that can exist at that end of an association.</span></span> <span data-ttu-id="f8b59-104">アソシエーション End はアソシエーションの一部として定義され、アソシエーションには必ず 2 つのアソシエーション End が必要です。</span><span class="sxs-lookup"><span data-stu-id="f8b59-104">Association ends are defined as part of an association; an association must have exactly two association ends.</span></span> <span data-ttu-id="f8b59-105">[ナビゲーション プロパティ](../../../../docs/framework/data/adonet/navigation-property.md)他の 1 つのアソシエーション end から移動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f8b59-105">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) allow for navigation from one association end to the other.</span></span>  
  
 <span data-ttu-id="f8b59-106">アソシエーション End の定義には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f8b59-106">An association end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="f8b59-107">アソシエーションに含まれるエンティティ型の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="f8b59-107">One of the entity types involved in the association.</span></span> <span data-ttu-id="f8b59-108">(必須)</span><span class="sxs-lookup"><span data-stu-id="f8b59-108">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8b59-109">アソシエーションでは、各アソシエーション End に同じエンティティ型を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="f8b59-109">For a given association, the entity type specified for each association end can be the same.</span></span> <span data-ttu-id="f8b59-110">これにより、自己アソシエーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f8b59-110">This creates a self-association.</span></span>  
  
-   <span data-ttu-id="f8b59-111">[アソシエーション end の多重度](../../../../docs/framework/data/adonet/association-end-multiplicity.md)アソシエーションの 1 つの end に存在できるエンティティ型のインスタンスの数を示します。</span><span class="sxs-lookup"><span data-stu-id="f8b59-111">An [association end multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="f8b59-112">値の 1 つ (1)、0 個または 1 (0..1)、または複数のアソシエーション end の多重度を持つことができます (\*)。</span><span class="sxs-lookup"><span data-stu-id="f8b59-112">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span>  
  
-   <span data-ttu-id="f8b59-113">アソシエーション End の名前。</span><span class="sxs-lookup"><span data-stu-id="f8b59-113">A name for the association end.</span></span> <span data-ttu-id="f8b59-114">(オプション)。</span><span class="sxs-lookup"><span data-stu-id="f8b59-114">(Optional)</span></span>  
  
-   <span data-ttu-id="f8b59-115">アソシエーション End に実行する CASCADE ON DELETE などの操作の情報。</span><span class="sxs-lookup"><span data-stu-id="f8b59-115">Information about operations that are performed on the association end, such as cascade on delete.</span></span> <span data-ttu-id="f8b59-116">(オプション)。</span><span class="sxs-lookup"><span data-stu-id="f8b59-116">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8b59-117">例</span><span class="sxs-lookup"><span data-stu-id="f8b59-117">Example</span></span>  
 <span data-ttu-id="f8b59-118">下のダイアグラムは、`PublishedBy` および `WrittenBy` という 2 つのアソシエーションの概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="f8b59-118">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="f8b59-119">`PublishedBy` アソシエーションのアソシエーション End は `Book` および `Publisher` のエンティティ型です。</span><span class="sxs-lookup"><span data-stu-id="f8b59-119">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="f8b59-120">多重度、 `Publisher` end が 1 つ (1) との多重度、 `Book` end が多く (\*)、出版社が多くの書籍、書籍は 1 つのパブリッシャーによって公開されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="f8b59-120">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 ![次の 3 つのエンティティの種類とモデルの例](./media/association-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="f8b59-122">ADO.NET Entity Framework は概念スキーマ定義言語と呼ばれるドメイン固有言語 (DSL) を使用して ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="f8b59-122">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="f8b59-123">次の CSDL は、上のダイアグラムに示された `PublishedBy` アソシエーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="f8b59-123">The CSDL below defines the `PublishedBy` association shown in the diagram above.</span></span> <span data-ttu-id="f8b59-124">各アソシエーション End の型、名前、および多重度は、XML 属性 (それぞれ `Type` 属性、`Role` 属性、および `Multiplicity` 属性) で指定されます。</span><span class="sxs-lookup"><span data-stu-id="f8b59-124">Note that the type, name, and multiplicity of each association end are specified by XML attributes (the `Type`, `Role`, and `Multiplicity` attributes, respectively).</span></span> <span data-ttu-id="f8b59-125">アソシエーション End に実行する操作に関するオプション情報は、XML 要素 (`OnDelete` 要素) に指定します。</span><span class="sxs-lookup"><span data-stu-id="f8b59-125">Optional information about operations performed on an end is specified in an XML element (the `OnDelete` element).</span></span> <span data-ttu-id="f8b59-126">この場合、出版社を削除すると、関連付けられたすべての書籍も削除されます。</span><span class="sxs-lookup"><span data-stu-id="f8b59-126">In this case, if a publisher is deleted, so are all associated books.</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a><span data-ttu-id="f8b59-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8b59-127">See also</span></span>

- [<span data-ttu-id="f8b59-128">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="f8b59-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="f8b59-129">エンティティ データ モデル</span><span class="sxs-lookup"><span data-stu-id="f8b59-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)

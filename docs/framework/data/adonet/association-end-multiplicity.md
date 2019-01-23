---
title: アソシエーション End の多重度
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 6d1b31c5b5ead701fbe808b91d7191fb84dc86c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502638"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="d13f4-102">アソシエーション End の多重度</span><span class="sxs-lookup"><span data-stu-id="d13f4-102">association end multiplicity</span></span>
<span data-ttu-id="d13f4-103">*アソシエーション end の多重度*の数を定義[エンティティ型](../../../../docs/framework/data/adonet/entity-type.md)の 1 つの end に存在できるインスタンス、[アソシエーション](../../../../docs/framework/data/adonet/association-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="d13f4-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="d13f4-104">アソシエーション End の多重度には、次のいずれかの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d13f4-104">An association end multiplicity can have one of the following values:</span></span>  
  
-   <span data-ttu-id="d13f4-105">1 (1):その 1 つのエンティティ型のインスタンスは、アソシエーション end に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="d13f4-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
-   <span data-ttu-id="d13f4-106">0 または 1 (0..1)。アソシエーション end に 0 個または 1 つのエンティティ型のインスタンスが存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="d13f4-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
-   <span data-ttu-id="d13f4-107">多数 (\*):アソシエーション end に 0、1、または複数のエンティティ型のインスタンスが存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="d13f4-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="d13f4-108">アソシエーションは、多くの場合、そのアソシエーション End の多重度により特徴付けられます。</span><span class="sxs-lookup"><span data-stu-id="d13f4-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="d13f4-109">たとえば、アソシエーション End の多重度が 1 (1) と多数 (\*) の場合、アソシエーションは一対多のアソシエーションと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d13f4-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="d13f4-110">次の例で、`PublishedBy` アソシエーションは一対多のアソシエーションです (出版社が多くの書籍を出版し、書籍は 1 社の出版社により出版されます)。</span><span class="sxs-lookup"><span data-stu-id="d13f4-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="d13f4-111">`WrittenBy` アソシエーションは多対多のアソシエーションです (書籍の著者が複数の場合があり、著者は複数の書籍を執筆することができます)。</span><span class="sxs-lookup"><span data-stu-id="d13f4-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d13f4-112">例</span><span class="sxs-lookup"><span data-stu-id="d13f4-112">Example</span></span>  
 <span data-ttu-id="d13f4-113">下のダイアグラムは、`PublishedBy` および `WrittenBy` という 2 つのアソシエーションの概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="d13f4-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="d13f4-114">`PublishedBy` アソシエーションのアソシエーション End は `Book` および `Publisher` のエンティティ型です。</span><span class="sxs-lookup"><span data-stu-id="d13f4-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="d13f4-115">`Publisher` End の多重度は 1 (1) で、`Book` End の多重度は多数 (\*) です。</span><span class="sxs-lookup"><span data-stu-id="d13f4-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 <span data-ttu-id="d13f4-116">![モデルの例](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="d13f4-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="d13f4-117">ADO.NET Entity Framework は概念スキーマ定義言語と呼ばれるドメイン固有言語 (DSL) を使用して ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="d13f4-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="d13f4-118">次の CSDL は、上のダイアグラムに示された `PublishedBy` アソシエーションを定義しています。</span><span class="sxs-lookup"><span data-stu-id="d13f4-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="d13f4-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d13f4-119">See also</span></span>
- [<span data-ttu-id="d13f4-120">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="d13f4-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="d13f4-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="d13f4-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)

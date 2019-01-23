---
title: Entity Data Model:名前空間
ms.date: 03/30/2017
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
ms.openlocfilehash: aa11902ece5197905c20e7e572562643c57f51c1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590108"
---
# <a name="entity-data-model-namespaces"></a><span data-ttu-id="15511-102">Entity Data Model:名前空間</span><span class="sxs-lookup"><span data-stu-id="15511-102">Entity Data Model: Namespaces</span></span>
<span data-ttu-id="15511-103">名前空間の Entity Data Model (EDM) では、抽象コンテナー[エンティティ型](../../../../docs/framework/data/adonet/entity-type.md)、[複合型](../../../../docs/framework/data/adonet/complex-type.md)、および[アソシエーション](../../../../docs/framework/data/adonet/association-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="15511-103">A namespace in the Entity Data Model (EDM) is an abstract container for [entity types](../../../../docs/framework/data/adonet/entity-type.md), [complex types](../../../../docs/framework/data/adonet/complex-type.md), and [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="15511-104">EDM の名前空間はプログラミング言語の名前空間と似ており、その中に含まれるオブジェクトのコンテキストを指定し、同じ名前を持つ (しかし、別の名前空間に含まれる) オブジェクトを明確に区別する手段になります。</span><span class="sxs-lookup"><span data-stu-id="15511-104">Namespaces in the EDM are similar to namespaces in a programming language: they provide context for the objects that they contain and they provide a way to disambiguate objects that have the same name (but are contained in different namespaces).</span></span>  
  
## <a name="example"></a><span data-ttu-id="15511-105">例</span><span class="sxs-lookup"><span data-stu-id="15511-105">Example</span></span>  
 <span data-ttu-id="15511-106">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)概念スキーマ定義言語と呼ばれるドメイン固有言語 (DSL) を使用して ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="15511-106">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="15511-107">次の CSDL コードは、名前空間を使用して異なる概念モデルに定義された型を識別します。</span><span class="sxs-lookup"><span data-stu-id="15511-107">The following CSDL code uses a namespace to identify a type that is defined in a different conceptual model.</span></span> <span data-ttu-id="15511-108">この例は、`Publisher` 名前空間からインポートされた複合型のプロパティ (`Address`) を持つエンティティ型 (`ExtendedBooksModel`) を定義します。</span><span class="sxs-lookup"><span data-stu-id="15511-108">The example defines an entity type (`Publisher`) that has a complex type property (`Address`) that is imported from the `ExtendedBooksModel` namespace.</span></span> <span data-ttu-id="15511-109">`Using` 要素は、名前空間がインポートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="15511-109">Note that the `Using` element indicates that a namespace has been imported.</span></span> <span data-ttu-id="15511-110">さらに、`Address` プロパティの型は、完全修飾名 (`ExtendedBooksModel.Address`) で定義されており、この型が `ExtendedBooksModel` 名前空間で定義されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="15511-110">Also note that the type of the `Address` property is defined by using its fully qualified name (`ExtendedBooksModel.Address`), indicating that this type is defined in the `ExtendedBooksModel` namespace.</span></span>  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a><span data-ttu-id="15511-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="15511-111">See also</span></span>
- [<span data-ttu-id="15511-112">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="15511-112">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="15511-113">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="15511-113">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)

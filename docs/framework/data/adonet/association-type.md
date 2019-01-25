---
title: アソシエーション型
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 3b01e053a1d61e2ce413ae6683d350b77c402fb5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714595"
---
# <a name="association-type"></a>アソシエーション型
*アソシエーション型*(アソシエーションとも呼ばれます) は、Entity Data Model (EDM) でのリレーションシップを記述するための基本的なビルド ブロックです。 概念モデルでは、アソシエーションは 2 つの間のリレーションシップを表します。[エンティティ型](../../../../docs/framework/data/adonet/entity-type.md)(など`Customer`と`Order`)。 アプリケーションでは、アソシエーションのインスタンスが特定のアソシエーション (`Customer` のインスタンスと `Order` のインスタンスの間のアソシエーションなど) を表します。 アソシエーション インスタンスはで論理的にグループ化、[アソシエーション セット](../../../../docs/framework/data/adonet/association-set.md)します。  
  
 アソシエーションの定義には、次の情報が含まれます。  
  
-   一意の名前  (必須)  
  
-   2 つ[アソシエーション end](../../../../docs/framework/data/adonet/association-end.md)リレーションシップのエンティティ型ごとに 1 つ。 (必須)  
  
    > [!NOTE]
    >  アソシエーションは、2 つ以上のエンティティ型のリレーションシップを表すことができません。 しかし、各アソシエーション End に同じエンティティ型を指定することによって、アソシエーションで自己リレーションシップを定義できます。  
  
-   A[参照整合性制約](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)します。 (オプション)。  
  
 各アソシエーション end を指定する必要があります、[アソシエーション end の多重度](../../../../docs/framework/data/adonet/association-end-multiplicity.md)アソシエーションの 1 つの end に存在できるエンティティ型のインスタンスの数を示します。 アソシエーション End の多重度には、1 (1)、ゼロか 1 (0..1)、または多数 (*) の値を指定することができます。 アソシエーションの一方の end のエンティティ型のインスタンスを介してアクセスできる[ナビゲーション プロパティ](../../../../docs/framework/data/adonet/navigation-property.md)またはエンティティ型で公開されている場合、外部キーです。 詳細については、次を参照してください[Entity Data Model:。外部キー](../../../../docs/framework/data/adonet/foreign-key-property.md)します。  
  
## <a name="example"></a>例  
 下のダイアグラムは、`PublishedBy` および `WrittenBy` という 2 つのアソシエーションの概念モデルを示しています。 `PublishedBy` アソシエーションのアソシエーション End は `Book` および `Publisher` のエンティティ型です。 `Publisher` End の多重度は 1 (1) で、`Book` End の多重度は多数 (*) です。これは、出版社が多くの書籍を出版し、書籍は 1 社の出版社により出版されることを示します。  
  
 ![モデルの例](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)概念スキーマ定義言語と呼ばれるドメイン固有言語 (DSL) を使用して ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 概念モデルを定義します。 次の CSDL は、上のダイアグラムに示された `PublishedBy` アソシエーションを定義しています。  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>関連項目
- [Entity Data Model キーの概念](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)

---
title: ナビゲーション プロパティ
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: 09c0e5e5dbc7b2be89e044c4d111fdd65fada7c7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662180"
---
# <a name="navigation-property"></a>ナビゲーション プロパティ
A*ナビゲーション プロパティ*で、省略可能なプロパティは、[エンティティ型](../../../../docs/framework/data/adonet/entity-type.md)から 1 つのナビゲーションの利用できる[エンド](../../../../docs/framework/data/adonet/association-end.md)の[アソシエーション](../../../../docs/framework/data/adonet/association-type.md)にその他の終了時刻です。 その他とは異なり[プロパティ](../../../../docs/framework/data/adonet/property.md)、ナビゲーション プロパティにデータを使用することはありません。  
  
 ナビゲーション プロパティの定義には、以下が含まれます。  
  
-   名前。 (必須)  
  
-   移動対象のアソシエーション。 (必須)  
  
-   移動対象のアソシエーションの End。 (必須)  
  
 ナビゲーション プロパティは、アソシエーション End の両方のエンティティ型で省略可能です。 1 つのアソシエーション End のエンティティ型にナビゲーション プロパティを定義した場合に、そのアソシエーションの他方の End でもエンティティ型にナビゲーション プロパティを定義する必要はありません。  
  
 ナビゲーション プロパティのデータ型はによって決定されます、[多重度](../../../../docs/framework/data/adonet/association-end-multiplicity.md)、リモートの[アソシエーション end](../../../../docs/framework/data/adonet/association-end.md)します。 たとえば、ナビゲーション プロパティ `OrdersNavProp` が `Customer` エンティティ型に存在し、`Customer` と `Order` の間の一対多のアソシエーションで移動するとします。 ナビゲーション プロパティのリモートのアソシエーション End の多重度が多数 (*) であるため、そのデータ型は (`Order` の) コレクションになります。 同様に、`CustomerNavProp` エンティティ型にナビゲーション プロパティ、`Order` が存在する場合、リモート End の多重度が (1) であるため、データ型は `Customer` になります。  
  
## <a name="example"></a>例  
 下のダイアグラムは、`Book`、`Publisher`、および `Author` という 3 つのエンティティ型の概念モデルを示しています。 Book エンティティ型には、ナビゲーション プロパティ、`Publisher` および `Authors` が定義されています。 Publisher エンティティ型と `Books` エンティティ型には、ナビゲーション プロパティ、`Author` が定義されています。  
  
 ![ナビゲーション プロパティを持つモデル](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)概念スキーマ定義言語と呼ばれるドメイン固有言語 (DSL) を使用して ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 概念モデルを定義します。 次の CSDL は、上のダイアグラムに示された `Book` エンティティ型を定義しています。  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 ナビゲーション プロパティを定義するために必要な情報を伝達する XML 属性が使用されることに注意してください。属性`Name`、プロパティの名前が含まれています`Relationship`、移動対象の関連付けの名前が含まれていますと`FromRole`と`ToRole`アソシエーションの end が含まれています。  
  
## <a name="see-also"></a>関連項目
- [Entity Data Model キーの概念](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)

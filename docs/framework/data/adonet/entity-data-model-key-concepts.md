---
title: Entity Data Model キーの概念
ms.date: 03/30/2017
ms.assetid: c635a16d-6674-45aa-9344-dcb7df992bab
ms.openlocfilehash: d92d2a99562c7eac6fef0ba76cd00241d600c265
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765634"
---
# <a name="entity-data-model-key-concepts"></a>Entity Data Model キーの概念
Entity Data Model (EDM) では、次の 3 つの主要な概念を使用して、データの構造を記述する:*エンティティ型*、*アソシエーション型*、および*プロパティ*です。 これらは、EDM の実装においてデータ構造を記述する上で最も重要な概念です。  
  
## <a name="entity-type"></a>エンティティ型  
 [エンティティ型](../../../../docs/framework/data/adonet/entity-type.md)は、エンティティ データ モデルを使用してデータの構造を記述するための基本的なビルド ブロックです。 概念モデルのエンティティ型がから構築された[プロパティ](../../../../docs/framework/data/adonet/property.md)顧客など、トップレベル概念の構造の記述とビジネス アプリケーションで注文します。 コンピューター プログラムのクラス定義がクラスのインスタンスのテンプレートになるように、エンティティ型はエンティティのテンプレートになります。 エンティティは、特定のオブジェクト (特定の顧客や注文など) を表します。 各エンティティを一意にいる必要があります[エンティティ キー](../../../../docs/framework/data/adonet/entity-key.md)内で、[エンティティ セット](../../../../docs/framework/data/adonet/entity-set.md)です。  エンティティ セットは、特定のエンティティ型のインスタンスのコレクションです。 エンティティ セット (および[アソシエーション セット](../../../../docs/framework/data/adonet/association-set.md)) では論理的にグループ化、[エンティティ コンテナー](../../../../docs/framework/data/adonet/entity-container.md)です。  
  
 エンティティ型では継承がサポートされており、1 つのエンティティ型を別のエンティティ型から派生させることができます。 詳細については、次を参照してください。 [Entity Data Model: 継承](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)です。  
  
## <a name="association-type"></a>アソシエーション型  
 [アソシエーション型](../../../../docs/framework/data/adonet/association-type.md)(アソシエーションとも呼ばれます) は、エンティティ データ モデル内のリレーションシップを記述するための基本的なビルド ブロックです。 概念モデルでは、アソシエーションが 2 つのエンティティ型 (Customer や Order など) の間のリレーションシップを表します。 すべてのアソシエーションが 2 つ[アソシエーション end](../../../../docs/framework/data/adonet/association-end.md)アソシエーションに含まれるエンティティ型を指定します。 各アソシエーション end が指定も、[アソシエーション end の多重度](../../../../docs/framework/data/adonet/association-end-multiplicity.md)アソシエーションの end に存在できるエンティティの数を示すです。 アソシエーション End の多重度には、1 (1)、ゼロか 1 (0..1)、または多数 (*) の値を指定することができます。 アソシエーションの一方の end のエンティティからアクセスできます[ナビゲーション プロパティ](../../../../docs/framework/data/adonet/navigation-property.md)、または公開されている場合、エンティティ型で外部キーを使用します。 詳細については、次を参照してください。[外部キー プロパティ](../../../../docs/framework/data/adonet/foreign-key-property.md)です。  
  
 アプリケーションでは、アソシエーションのインスタンスが特定のアソシエーション (Customer のインスタンスと Order のインスタンスの間のアソシエーションなど) を表します。 アソシエーション インスタンスはで論理的にグループ化、[アソシエーション セット](../../../../docs/framework/data/adonet/association-set.md)です。 アソシエーション セット (および[エンティティ セット](../../../../docs/framework/data/adonet/entity-set.md)) では論理的にグループ化、[エンティティ コンテナー](../../../../docs/framework/data/adonet/entity-container.md)です。  
  
## <a name="property"></a>プロパティ  
 [エンティティ型](../../../../docs/framework/data/adonet/entity-type.md)含める[プロパティ](../../../../docs/framework/data/adonet/property.md)その構造と特性を定義します。 たとえば、Customer エンティティ型には、CustomerId、Name、Address などのプロパティがあります。  
  
 概念モデルのプロパティは、コンピューター プログラムのクラスに定義されるプロパティに似ています。 クラスのプロパティがクラスの構造を定義し、オブジェクトに関する情報を伝達するのと同様に、概念モデルのプロパティはエンティティ型の構造を定義し、エンティティ型のインスタンスに関する情報を伝達します。  
  
 プロパティには、プリミティブ データ (文字列、整数、ブール値など) または構造化データ (複合型) を含めることができます。 詳細については、次を参照してください。 [Entity Data Model: プリミティブ データ型](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)です。  
  
## <a name="representations-of-a-conceptual-model"></a>概念モデルの表現  
 A*概念モデル*エンティティおよびリレーションシップとしていくつかのデータの構造の特定の表現です。 概念モデルを表現する 1 つの手段として、ダイアグラムを使用することができます。 下のダイアグラムは、3 つのエンティティ型 (`Book`、`Publisher`、および `Author`) と 2 つのアソシエーション (`PublishedBy` および `WrittenBy`) の概念モデルを表しています。  
  
 ![ナビゲーション プロパティが含まれるモデル](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")  
  
 しかし、この表現には、モデルに関する詳細を伝える上でいくつかの欠点があります。 たとえば、プロパティ型とエンティティ セットの情報はダイアグラムに示されていません。 ドメイン固有言語 (DSL) を使用すると、概念モデルの詳細情報をさらに明確に伝えることができます。 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)と呼ばれる XML に基づく DSL を使用して*概念スキーマ定義言語*([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 概念モデルを定義します。 以下に、上のダイアグラムに示されている概念モデルの CSDL 定義を示します。  
  
 [!code-xml[EDM_Example_Model#EDMExampleCSDL](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#edmexamplecsdl)]  
  
## <a name="see-also"></a>関連項目  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)

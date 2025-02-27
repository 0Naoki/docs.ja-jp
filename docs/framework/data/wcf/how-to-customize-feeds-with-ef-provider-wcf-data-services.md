---
title: '方法: Entity Framework プロバイダーを使用したフィードのカスタマイズ (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: fd16272e-36f2-415e-850e-8a81f2b17525
ms.openlocfilehash: 8f994065ea42d6fc522fa297cafa8c46a8164e67
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780154"
---
# <a name="how-to-customize-feeds-with-the-entity-framework-provider-wcf-data-services"></a>方法: Entity Framework プロバイダーを使用したフィードのカスタマイズ (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] では、データ サービス応答の Atom シリアル化をカスタマイズして、AtomPub プロトコルで定義されている未使用の要素にエンティティのプロパティをマップできます。 このトピックでは、Entity Framework を使用して、.edmx ファイルで定義されているデータ モデルのエンティティ型のマッピング属性を定義する方法について説明します。 詳細については、「[フィードのカスタマイズ](feed-customization-wcf-data-services.md)」を参照してください。  
  
 このトピックでは、ツールによって生成された .edmx file ファイルを手動で変更します (このファイルには、データ モデルが含まれます)。 エンティティ デザイナーではデータ モデルへの拡張がサポートされていないので、このファイルは手動で変更する必要があります。 Entity Data Model ツールによって生成される .edmx ファイルの詳細については、「 [.Edmx ファイルの概要」 (Entity Framework)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))を参照してください。 このトピックの例では、Northwind サンプル データ サービスおよび自動生成されたクライアント データ サービス クラスを使用します。 このサービスとクライアントデータクラスは、 [WCF Data Services のクイックスタート](quickstart-wcf-data-services.md)を完了したときに作成されます。  
  
### <a name="to-manually-modify-the-northwindedmx-file-to-add-feed-customization-attributes"></a>Northwind.edmx ファイルを手動で変更してフィードのカスタマイズ属性を追加するには  
  
1. **ソリューションエクスプローラー**で、 `Northwind.edmx`ファイルを右クリックし、[ファイルを**開くアプリケーション**の選択] をクリックします。  
  
2. **[-Northwind. .edmx で開く]** ダイアログボックスで、 **[XML エディター]** を選択し、 **[OK]** をクリックします。  
  
3. `ConceptualModels` 要素を見つけて、フィードのカスタマイズ マッピング属性を含む次の要素で既存の `Customers` エンティティ型を置き換えます。  
  
     [!code-xml[Astoria Custom Feeds#EdmFeedCustomers](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/northwind.csdl#edmfeedcustomers)]  
  
4. 変更を保存して Northwind.edmx ファイルを閉じます。  
  
5. OptionalNorthwind .edmx ファイルを右クリックし、 **[カスタムツールの実行]** をクリックします。  
  
     オブジェクト レイヤー ファイルが再生成されます。このファイルが必要になる場合があります。  
  
6. プロジェクトを再コンパイルします。  
  
## <a name="example"></a>例  
 前の例では、URI `http://myservice/Northwind.svc/Customers('ALFKI')` に次の結果が返されます。  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/edmfeedresult.xml#edmfeedresult)]  
  
## <a name="see-also"></a>関連項目

- [Entity Framework プロバイダー](entity-framework-provider-wcf-data-services.md)

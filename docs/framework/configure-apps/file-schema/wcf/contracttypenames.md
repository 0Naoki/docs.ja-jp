---
title: '&lt;contractTypeNames&gt;'
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: 60647e6ec31e7228f09d084ff669a1829770ca14
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144732"
---
# <a name="ltcontracttypenamesgt"></a>&lt;contractTypeNames&gt;
検索対象サービスのコントラクト名であるコントラクト型名のリストと、サービスを検索するときに一般的に使用される条件を指定する構成セクション。 複数のコントラクト名が指定されると、すべてのコントラクトに一致するサービス エンドポイントのみが適用されます。 Windows Communication Foundation (WCF) エンドポイントがのみサポートしている 1 つのコントラクトに注意してください。  
  
 \<system.ServiceModel >  
\<standardEndpoints >  
  
## <a name="syntax"></a>構文  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
 なし。  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|コントラクト型名は、サービスを検索するときに一般的に使用される条件セットを参照するプロパティです。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<findCriteria >](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。 条件は、(探しているサービスの種類を指定して) 検索条件にグループ化することができ、検索 (検索持続期間)、終了条件。|  
  
## <a name="see-also"></a>関連項目  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>

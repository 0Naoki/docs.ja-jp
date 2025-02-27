---
title: <serviceAuthorization> 要素
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: f476f754a340f52859be2986e42754cba0ef3771
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834023"
---
# <a name="serviceauthorization-element"></a>\<serviceAuthorization > 要素

サービス操作へのアクセスを許可する設定を指定します。

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)\
&nbsp; @ no__t @ no__t @no__t @ no__t-3[ **-6 動作 >** ](behaviors.md)\
&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-3[ **\<serviceBehaviors >** ](servicebehaviors.md)\.-9
&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0behavior >** ](behavior-of-servicebehaviors.md)1 のようになります。
&nbsp; @ no__t @ no__t @ no__t @ no__t @ no__t @ no__t @ no__t-7 @ no__t-8 @-9 **&nbsp;1serviceAuthorization > を**登録してください。  

## <a name="syntax"></a>構文

```xml
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

|属性|説明|  
|---------------|-----------------|  
|impersonateCallerForAllOperations|サービスのすべての操作が呼び出し元を偽装するかどうかを指定するブール値。 既定値は `false` です。<br /><br /> 特定のサービス操作が呼び出し元を偽装する場合、スレッド コンテキストは、指定されたサービスを実行する前に呼び出し元のコンテキストに切り替えられます。|  
|principalPermissionMode|サーバーでの操作を実行するために使用されるプリンシパルを設定します。 次の値があります。<br /><br /> -なし<br />-UseWindowsGroups<br />-UseAspNetRoles<br />-カスタム<br /><br /> 既定値は UseWindowsGroups です。 値は、<xref:System.ServiceModel.Description.PrincipalPermissionMode> 型です。 この属性の使用方法の詳細については、@no__t を参照してください。PrincipalPermissionAttribute クラス @ no__t を使用してアクセスを制限します。|  
|roleProviderName|Windows Communication Foundation (WCF) アプリケーションにロール情報を提供するロール プロバイダーの名前を指定する文字列。 既定値は空の文字列です。|  
|ServiceAuthorizationManagerType|サービス承認マネージャーの型を含む文字列。 詳細については、「 <xref:System.ServiceModel.ServiceAuthorizationManager> 」を参照してください。|  

### <a name="child-elements"></a>子要素

|要素|説明|  
|-------------|-----------------|  
|authorizationPolicies|`add` キーワードを使用して追加できる承認ポリシーの種類のコレクションを含みます。 各承認ポリシーは、文字列の単一の必須属性 `policyType` を含みます。 この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。 アクセス制御は、それに基づいて許可または拒否されます。 詳細については、「 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement> 」を参照してください。|  

### <a name="parent-elements"></a>親要素

|要素|説明|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|サービスの動作設定のコレクションが含まれています。|  

## <a name="remarks"></a>コメント

このセクションには、承認、カスタム ロール プロバイダー、および偽装に影響する要素が含まれています。  
  
`principalPermissionMode` 属性は、保護メソッドの使用を承認するときに使用するユーザー グループを指定します。 既定値は `UseWindowsGroups` で、リソースにアクセスしようとしている ID を、"Administrators" や "Users" などの Windows グループから検索するように指定します。 次のコードに示すように、`UseAspNetRoles` を指定して、@no__t 1system.web > 要素で構成されたカスタムロールプロバイダーを使用することもできます。

```xml
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```
  
次のコードは、`principalPermissionMode` 属性で使用される @no__t 0 を示しています。
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

この構成要素の使用例については、「[サービス操作](../../../wcf/samples/authorizing-access-to-service-operations.md)と[承認ポリシー](../../../wcf/samples/authorization-policy.md)へのアクセスの承認」を参照してください。
  
## <a name="see-also"></a>関連項目

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [セキュリティ動作](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [サービス操作へのアクセスの承認](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [2 つのオブジェクトが等しいかどうかをテストする方法サービスのカスタム承認マネージャーを作成する @ no__t-0
- [2 つのオブジェクトが等しいかどうかをテストする方法PrincipalPermissionAttribute クラスを使用してアクセスを制限する @ no__t-0
- [承認ポリシー](../../../wcf/samples/authorization-policy.md)

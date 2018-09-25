---
title: '&lt;claimsAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 0ec7e44363f87e54eae97b70352f520fe87540be
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47074954"
---
# <a name="ltclaimsauthenticationmanagergt"></a>&lt;claimsAuthenticationManager&gt;
入力方向の要求のクレーム認証マネージャーを登録します。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<claimsAuthenticationManager >  
  
## <a name="syntax"></a>構文  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|型|派生したカスタム型を指定します、<xref:System.Security.Claims.ClaimsAuthenticationManager>クラス。 詳細を指定する方法については、`type`属性を [カスタム型の参照] を参照してください。|  
  
### <a name="child-elements"></a>子要素  
 ある場合ありません`type`属性、または、`type`属性参照、<xref:System.Security.Claims.ClaimsAuthenticationManager>クラス、`<claimsAuthenticationManager>`要素は子要素を取りません。 ただし、から派生したクラス<xref:System.Security.Claims.ClaimsAuthenticationManager>子構成要素を定義できます。  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|サービス レベルの id の設定を指定します。|  
  
## <a name="remarks"></a>Remarks  
 によって提供される既定の動作、<xref:System.Security.Claims.ClaimsAuthenticationManager>クラスは、入力方向の要求をエコーします。 いない場合`type`属性が指定されて場合は、`type`属性を指定します、<xref:System.Security.Claims.ClaimsAuthenticationManager>クラス、`<claimsAuthenticationManager>`要素は子要素を取りません。 指定することができます、`type`から派生した型を登録する属性、<xref:System.Security.Claims.ClaimsAuthenticationManager>カスタム動作を実装するクラス。 派生クラスの子要素を使用した構成をサポートできる、`<claimsAuthenticationManager>`要素をオーバーライドすることで、<xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>これらの要素を処理するメソッド。 子要素に対して定義されているスキーマは、最大クラスのデザイナーです。  
  
 `<claimsAuthenticationManager>`要素セット、<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType>プロパティ。  
  
## <a name="example"></a>例  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```

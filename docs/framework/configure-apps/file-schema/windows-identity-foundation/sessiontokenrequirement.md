---
title: '&lt;sessionTokenRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 5a141dd83cb7ef1271906871097eb68da174d22f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ltsessiontokenrequirementgt"></a>&lt;sessionTokenRequirement&gt;
構成を提供、<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>クラスまたは派生クラス。  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<add>  
\<sessionTokenRequirement >  
  
## <a name="syntax"></a>構文  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|有効期間|セッション トークンの有効期間を指定します。|  
  
### <a name="child-elements"></a>子要素  
 なし  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|トークン ハンドラー コレクションに指定されたセキュリティ トークン ハンドラーを追加します。|  
  
## <a name="example"></a>例  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```

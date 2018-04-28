---
title: '&lt;httpDigest&gt; 要素'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 75579a583b774896f43099d3cc30f1679b10a889
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
---
# <a name="lthttpdigestgt-element"></a>&lt;httpDigest&gt; 要素
サービスに対するクライアントの認証時に使用されるダイジェスト型の資格情報を指定します。  
  
 \<system.ServiceModel >  
\<ビヘイビアー >  
\<endpointBehaviors>  
\<behavior>  
\<clientCredentials>  
\<httpDigest >  
  
## <a name="syntax"></a>構文  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|`impersonationLevel`|クライアントがサーバーと通信する偽装設定を設定します。 クライアントが選択する偽装モードは、サーバーでは適用されません。 以下の値が有効です。<br /><br /> 識別します。 サーバーは、id およびクライアントの権限を取得できますが、クライアントを偽装することはできません。<br />偽装: サーバーは、ローカル システム上のクライアントのセキュリティ コンテキストを偽装できます。<br />委任: サーバーはリモート システム上のクライアントのセキュリティ コンテキストを偽装することができます。<br />-Anonymous: サーバーことはできませんの権限を借用またはクライアントを識別します。<br />-None: 偽装レベルが割り当てられていません。<br /><br /> 既定値は Identification です。 この属性は <xref:System.Security.Principal.TokenImpersonationLevel> 型です。|  
  
### <a name="child-elements"></a>子要素  
 なし  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|サービスに対するクライアントの認証に使用される資格情報を指定します。|  
  
## <a name="remarks"></a>コメント  
 ダイジェストは、アルゴリズムと入力セットを使用して決定されるハッシュです。 認証する側と認証される側はアルゴリズムに同意し、入力として使用されるデータを交換します。 クライアントはハッシュを計算して、サービスに送信できます。 また、サービスもハッシュを計算して、値を比較します。 一致すると、クライアントが検証されます。  
  
 この機能は、Windows の Active Directory およびインターネット インフォメーション サービス (IIS) と共に有効にする必要があります。 詳細については、次を参照してください。 [IIS 6.0 のダイジェスト認証](http://go.microsoft.com/fwlink/?LinkId=88443)です。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>  
 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>  
 <xref:System.ServiceModel.Security.HttpDigestClientCredential>  
 [セキュリティ動作](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [クライアントのセキュリティ保護](../../../../../docs/framework/wcf/securing-clients.md)  
 [証明書の使用](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [サービスおよびクライアントのセキュリティ保護](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

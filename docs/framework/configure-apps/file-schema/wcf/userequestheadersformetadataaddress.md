---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 842f989ab1f2f0b9e8fe08e8fd729f983e846ffc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261569"
---
# <a name="userequestheadersformetadataaddress"></a>\<useRequestHeadersForMetadataAddress >
メタデータのアドレス情報を要求メッセージ ヘッダーから取得できるようにします。  
  
\<system.ServiceModel >  
\<<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<useRequestHeadersForMetadataAddress >  
  
## <a name="syntax"></a>構文  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
 なし。  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<defaultPorts>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|クライアント アプリケーションがリッスンする既定の通信エンドポイントの一覧を表示する既定のポートのコレクション。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|動作の要素を指定します。|  
  
## <a name="see-also"></a>関連項目
- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>

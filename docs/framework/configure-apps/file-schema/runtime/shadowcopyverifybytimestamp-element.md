---
title: '&lt;shadowCopyVerifyByTimestamp&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a37e41aa653fb3cd5990b75f3c5467a88660113
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622261"
---
# <a name="ltshadowcopyverifybytimestampgt-element"></a>&lt;shadowCopyVerifyByTimestamp&gt; Element
シャドウ コピーが [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] で導入された既定の起動の動作を使用するか、.NET Framework の以前のバージョンの起動の動作に戻すかどうかを指定します。  
  
 \<configuration > 要素  
\<ランタイム > 要素  
\<shadowCopyVerifyByTimestamp> Element  
  
## <a name="syntax"></a>構文  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|enabled|必須の属性です。<br /><br /> アセンブリがアセンブリをシャドウ コピーする前に更新されているかどうかを判断する、開始するときにシャドウ コピーを使用するアプリケーション ドメインがアセンブリのタイムスタンプを比較するかどうかを指定します。|  
  
## <a name="enabled-attribute"></a>enabled 属性  
  
|値|説明|  
|-----------|-----------------|  
|true|起動時に、前回シャドウ コピーのディレクトリにコピーされたとき以降に更新されたアセンブリだけをコピーします。 これは、既定値は、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]します。|  
|False|起動時にすべてのファイルにコピーされましたが、.NET Framework の以前のバージョンの起動の動作に戻ります。|  
  
### <a name="child-elements"></a>子要素  
 なし。  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|`configuration`|共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。|  
|`runtime`|アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。|  
  
## <a name="remarks"></a>Remarks  
 以降では、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]アセンブリのシャドウ コピーの場合は、そのタイムスタンプが前回、シャドウ コピーのディレクトリにコピーされたとき以降に変更されたことを示します。 」の説明に従って、シャドウ コピーを使用する多くのアプリケーションの起動時間が短縮これ[アセンブリのシャドウ コピー](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)します。 この動作の変更率が高いと、アセンブリの更新の頻度を持つアプリケーションの利点可能性があります。 その場合は、この要素を使用して、以前のバージョンの .NET Framework の動作を復元することができます。  
  
## <a name="example"></a>例  
 次の例でシャドウ コピーの既定のスタートアップ動作を無効にする方法を示しています、 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]、.NET Framework の以前のバージョンの起動の動作に戻ります。  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>関連項目
- [ランタイム設定スキーマ](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [構成ファイル スキーマ](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [アセンブリのシャドウ コピー](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)

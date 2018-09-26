---
title: '&lt;アサート&gt;要素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b15e569ff6e42298c0a1de02f77ab7c302c70d86
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193513"
---
# <a name="ltassertgt-element"></a>&lt;アサート&gt;要素
<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> メソッドの呼び出し時にメッセージ ボックスを表示するかどうかを指定し、メッセージの書き込み先のファイルの名前も指定します。  
  
 \<configuration>  
\<system.diagnostics >  
\<アサート >  
  
## <a name="syntax"></a>構文  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|`assertuienabled`|省略可能な属性です。<br /><br /> かどうかを表示する際にメッセージ ボックスを指定します、 **Debug.Assert**メソッドを評価する**false**します。|  
|`logfilename`|省略可能な属性です。<br /><br /> 場合に、メッセージを書き込むファイルの名前を示す**Debug.Assert**に評価される**false**します。|  
  
## <a name="assertuienabled-attribute"></a>assertuienabled 属性  
  
|[値]|説明|  
|-----------|-----------------|  
|`true`|メッセージ ボックスが表示されます。 既定値です。|  
|`false`|メッセージ ボックスは表示されません。|  
  
### <a name="child-elements"></a>子要素  
 なし。  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|`configuration`|共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。|  
|`system.diagnostics`|メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。|  
  
## <a name="remarks"></a>Remarks  
 両方の属性で、 **\<アサート >** 要素は省略可能です。 メッセージ ボックスに、メッセージを書き込むファイルを指定せず無効にできますか、メッセージ ボックスが有効のままにしてメッセージを記述するファイルを指定することができます。  
  
## <a name="example"></a>例  
 次の例は、呼び出すときに表示するメッセージ ボックスを無効にする方法を示しています。 **Debug.Assert**にメッセージを書き込むと`c:\log.txt`します。  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Diagnostics.Debug>  
 [トレースおよびデバッグ設定のスキーマ](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)

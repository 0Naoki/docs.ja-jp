---
title: "軽減策: DataContractJsonSerializer での制御文字のシリアル化"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6da580d208736a64e2094f701fb4c1241a488322
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>軽減策: DataContractJsonSerializer での制御文字のシリアル化

.NET Framework 4.7 以降では、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> での制御文字のシリアル化の方法が、ECMAScript V6 および V8 に準拠するように変更されました。 
 
## <a name="impact"></a>影響

.NET framework 4.6.2 以前のバージョンでは、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> で、ECMAScript V6 および V8 標準と互換性がある方法で `\b`、`\f`、`\t` などの一部の特殊制御文字がシリアル化されませんでした。

.NET Framework 4.7 以降のバージョンの .NET Framework を対象とするアプリの場合、これらの制御文字のシリアル化は ECMAScript V6 および V8 と互換性があります。 影響を受ける API は次のとおりです。

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a>軽減策

.NET Framework 4.7 以降のバージョンの .NET Framework を対象とするアプリの場合、この動作は既定で有効になります。

この動作が望ましくない場合は、app.config または web.config ファイルの `<runtime>` セクションに次の行を追加して、この機能を無効にすることができます。

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a>関連項目
[.NET Framework 4.7 における再ターゲットの変更点](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

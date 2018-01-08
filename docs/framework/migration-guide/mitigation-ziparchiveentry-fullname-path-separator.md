---
title: "軽減策: ZipArchiveEntry.FullName パスの区切り文字"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ca43e4952f7ff457cf61c2c36334ab6213e50ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a>軽減策: ZipArchiveEntry.FullName パスの区切り文字
[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 以降を対象とするアプリでは、<xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> プロパティで使用されるパスの区切り文字は、以前のバージョンの .NET Framework で使用されていた円記号 ("\\") からスラッシュ ("/") に変更されました。   <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType> メソッドのオーバーロードのいずれかを呼び出すことで、<xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> オブジェクトが作成されます。  
  
## <a name="impact"></a>影響  
 この変更によって、.NET の実装が [.ZIP ファイル形式の仕様](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)のセクション 4.4.17.1 に準拠するようになったほか、Windows 以外のシステムで ZIP アーカイブを圧縮解除できるようになりました。  
  
 Macintosh などの Windows 以外のオペレーティング システムで以前のバージョンの .NET Framework を対象とするアプリで作成された zip ファイルを圧縮解除すると、ディレクトリ構造を保持できません。 たとえば、Macintosh で、ディレクトリ パスとファイル名が円記号 ("\\") 文字で連結された名前を持つ一連のファイルを作成するとします。 その場合、圧縮解除されたファイルのディレクトリ構造は保持されません。  
  
 .NET Framework <xref:System.IO> 名前空間の API によって、Windows オペレーティング システムで展開される .zip ファイルでは、この変更の影響は最小限になるはずです。これらの API では、スラッシュ ("/") または円記号 ("\\") をパスの区切り文字としてシームレスに処理できるためです。  
  
## <a name="mitigation"></a>軽減策  
 この動作が望ましくない場合は、アプリケーション構成ファイルの [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに構成設定を追加して、無効にすることができます。 以下は、`<runtime>` セクションと無効への切り替えの両方を示しています。  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 また、以前のバージョンの .NET Framework を対象とするものの、[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 以降のバージョンで実行されているアプリでは、アプリケーション構成ファイルの [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに構成設定を追加して、この動作を有効にすることができます。 以下は、`<runtime>` セクションと有効への切り替えの両方を示しています。  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a>参照  
 [変更の再ターゲット](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)  
 [4.6.1 でのアプリケーションの互換性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)

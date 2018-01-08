---
title: "軽減策: カスタムの IMessageFilter.PreFilterMessage 実装"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 38a8c3556d78431672ebeab16a3fa65e2debc0e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a>軽減策: カスタムの IMessageFilter.PreFilterMessage 実装
.NET Framework の [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 以降のバージョンを対象とする Windows フォーム アプリでは、<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> メソッドが呼び出されると、カスタムの <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 実装は <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 実装が次のような場合に、メッセージを安全にフィルター処理できます。  
  
-   次の操作のいずれか、または両方を行う場合:  
  
    -   <xref:System.Windows.Forms.Application.AddMessageFilter%2A> メソッドを呼び出してメッセージ フィルターを追加する。  
  
    -   <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> メソッドを呼び出してメッセージ フィルターを削除する。 メソッドをオーバーライドします。  
  
-   **なおかつ**、<xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> メソッドを呼び出してメッセージをポンプする場合。  
  
## <a name="impact"></a>影響  
 この変更によって影響を受けるのは、.NET Framework の [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 以降のバージョンを対象とする Windows フォーム アプリのみです。  
  
 .NET Framework の以前のバージョンを対象とする Windows フォーム アプリの場合、このような実装で、<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> メソッドが呼び出されると <xref:System.IndexOutOfRangeException> 例外がスローされることがあります。  
  
## <a name="mitigation"></a>軽減策  
 この変更が望ましくない場合は、[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] またはそれ以降のバージョンを対象とするアプリでこの変更を無効にできます。この無効化は、そのアプリの構成ファイルの [\<<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに次の構成設定を追加して行います。  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />   
</runtime>  
```  
  
 また、.NET Framework の以前のバージョンを対象とするものの [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] またはそれ以降のバージョンで実行されているアプリでは、そのアプリの構成ファイルの [\<<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに次の構成設定を追加して、この動作を有効にできます。  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />   
</runtime>  
```  
  
## <a name="see-also"></a>参照  
 [変更の再ターゲット](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)

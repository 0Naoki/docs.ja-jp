---
title: ".NET Framework 1.1 からの移行"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework 4.5, migrating from 1.1
- .NET Framework 1.1, migrating to .NET Framework 4.5
ms.assetid: 7ead0cb3-3b19-414a-8417-a1c1fa198d9e
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5757894a63ed556413147b8ef8c85c2d31ef11a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="migrating-from-the-net-framework-11"></a>.NET Framework 1.1 からの移行
[!INCLUDE[win7](../../../includes/win7-md.md)] 以降のバージョンの Windows オペレーティング システムでは、[!INCLUDE[net_v11_long](../../../includes/net-v11-long-md.md)] はサポートされません。 このため、 [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] を対象とするアプリケーションは変更を行わないと、 [!INCLUDE[win7](../../../includes/win7-md.md)] 以降のバージョンのオペレーティング システムでは実行できません。 このトピックでは、[!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] を対象とするアプリケーションを [!INCLUDE[win7](../../../includes/win7-md.md)] 以降のバージョンの Windows オペレーティング システムで実行するために必要な手順について説明します。 [!INCLUDE[net_v11_long](../../../includes/net-v11-long-md.md)] と [!INCLUDE[win8](../../../includes/win8-md.md)] に関する詳細については、「[Windows 8、Windows 8.1、または Windows 10 での .NET Framework 1.1 アプリの実行](../../../docs/framework/install/run-net-framework-1-1-apps.md)」を参照してください。  
  
## <a name="retargeting-or-recompiling"></a>再ターゲットまたは再コンパイル  
 [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] を使用してコンパイルしたアプリケーションを [!INCLUDE[win7](../../../includes/win7-md.md)] 以降のバージョンの Windows オペレーティング システムで実行するには、次の 2 つの方法があります。  
  
-   アプリケーションを [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] に再ターゲットして実行することができます。 再ターゲットするには、[\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 要素をアプリケーションの構成ファイルに追加して [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] で実行できるようにする必要があります。 そのための構成ファイルの形式は次のとおりです。  
  
    ```xml  
    <configuration>   
       <startup>  
          <supportedRuntime version="v4.0"/>  
       </startup>  
    </configuration>  
    ```  
  
-   [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]をターゲットとするコンパイラでアプリケーションを再コンパイルできます。 最初に Visual Studio 2003 を使用してソリューションを開発およびコンパイルした場合は、ソリューションを [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] で開きます。これにより、 **[Project Compatibility]** (プロジェクト互換性) ダイアログ ボックスによってソリューションおよびプロジェクト ファイルが Visual Studio 2003 で使用される形式から [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)]で使用される Microsoft Build Engine (MSBuild) 形式に変換されます。  
  
 再コンパイルまたは再ターゲットのいずれを選択するかに関係なく、アプリケーションが .NET Framework の新しいバージョンで導入された変更の影響を受けるかどうかを確認する必要があります。 変更には次の 2 種類があります。  
  
-   [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] より新しいバージョンで加えられた、互換性に影響する変更。  
  
-   [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] より新しいバージョンで非推奨または旧式とマークされた型と型のメンバー。  
  
 アプリケーションを再ターゲットするか、再コンパイルするかに関係なく、 [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)]より後にリリースされた .NET Framework の各バージョンについては、互換性に影響する変更と旧式の型および型のメンバーを確認する必要があります。  
  
## <a name="breaking-changes"></a>互換性に影響する変更点  
 互換性に影響する変更が行われた場合は、変更内容に応じて、アプリケーションの再ターゲットおよび再コンパイル時の回避策が提示される場合があります。 場合によっては、アプリケーションの構成ファイルの [\<runtime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 要素に子要素を追加することで、以前の動作を復元できます。 たとえば、次の構成ファイルは [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] での文字列の並べ替えおよび比較の動作を復元し、アプリケーションの再ターゲットまたは再コンパイルのいずれにも使用できます。  
  
```xml  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
 ただし、ソース コードの変更とアプリケーションの再コンパイルが必要になる場合があります。  
  
 互換性に影響する可能性がある変更点がアプリケーションに与える影響を評価するには、次の変更一覧を確認する必要があります。  
  
-   「[.NET Framework 2.0 の互換性に影響する変更点](http://go.microsoft.com/fwlink/?LinkId=125263) 」に記載されている、 [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] を対象とするアプリケーションに影響する可能性がある [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)]の変更点。  
  
-   「[.NET Framework 3.5 SP1 の変更点](http://go.microsoft.com/fwlink/?LinkID=186989) 」に記載されている、 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] から [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)]の変更点。  
  
-   「[.NET Framework 4 への移行に関する問題](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)」に記載されている、[!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] から [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] の変更点。  
  
## <a name="obsolete-types-and-members"></a>旧式の型およびメンバー  
 旧式の型およびメンバーの影響は、アプリケーションを再ターゲットする場合と再コンパイルする場合とでは若干異なります。 旧式の型およびメンバーを使用しても、その型およびメンバーをアセンブリから物理的に削除しない限り、再ターゲットしたアプリケーションには影響しません。 旧式の型およびメンバーを使用してアプリケーションを再コンパイルすると、通常はコンパイラ エラーではなく、コンパイラの警告が発生します。 ただし、場合によってはコンパイラ エラーが発生し、旧式の型またはメンバーを使用したコードをコンパイルできないことがあります。 その場合は、旧式の型またはメンバーを呼び出すソース コードを変更してからアプリケーションを再コンパイルする必要があります。 旧式の型およびメンバーの詳細については、「[.NET Framework クラス ライブラリの互換性のために残されている機能](../../../docs/framework/whats-new/whats-obsolete.md)」を参照してください。  
  
 [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] のリリース以後に非推奨になった型およびメンバーの影響を評価するには、「[.NET Framework クラス ライブラリの互換性のために残されている機能](../../../docs/framework/whats-new/whats-obsolete.md)」を参照してください。 [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)]、[!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)]、および [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] について、旧式の型およびメンバーの一覧を確認してください。

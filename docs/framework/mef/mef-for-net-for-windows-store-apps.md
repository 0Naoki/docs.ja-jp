---
title: Windows ストア アプリ用 .NET 用 MEF
ms.date: 03/30/2017
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cb7807fbfc1fbaf039fd7aef04331210dfa7cfa
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2018
ms.locfileid: "46583431"
---
# <a name="mef-for-net-for-windows-store-apps"></a>Windows ストア アプリ用 .NET 用 MEF
<xref:System.Composition?displayProperty=nameWithType> とその子名前空間には、Managed Extensibility Framework (MEF) を使用して拡張可能な [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリを開発するための型が含まれています。 これらの名前空間は、[!INCLUDE[win8](../../../includes/win8-md.md)] オペレーティング システムの [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] サブセットの一部です。  
  
 これらの名前空間は、.NET Framework で配布されているコア クラス ライブラリの一部ではありません。 これらの名前空間をインストールするには、[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] でプロジェクトを開き、**[プロジェクト]** メニューの **[Manage NuGet Packages]** をクリックし、Microsoft.Composition パッケージをオンライン検索します。  
  
-   <xref:System.Composition?displayProperty=nameWithType> は、[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリのコア MEF を構成するクラスを提供します。  
  
-   <xref:System.Composition.Convention?displayProperty=nameWithType> は、規則に基づく構成モデルでの MEF の使用をサポートする型を提供します。  
  
-   <xref:System.Composition.Hosting?displayProperty=nameWithType> は、ホスト アプリケーションの開発者に役立つ MEF 型を提供します。  
  
-   <xref:System.Composition.Hosting.Core?displayProperty=nameWithType> は、合成エンジンによって内部的に使用される MEF 型を提供します。  
  
 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] についての詳細およびそれに含まれる名前空間と型の一覧については、Windows デベロッパー センターで「[Windows ストア アプリ用 .NET の概要](https://go.microsoft.com/fwlink/p/?LinkID=238312)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [Windows ストア アプリ用 .NET の概要](https://go.microsoft.com/fwlink/p/?LinkID=238312)  
 [Windows ストア アプリ用 .NET – サポートされている API](https://go.microsoft.com/fwlink/p/?LinkID=247912)  
 [MEF (Managed Extensibility Framework)](../../../docs/framework/mef/index.md)

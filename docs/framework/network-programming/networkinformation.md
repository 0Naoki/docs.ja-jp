---
title: NetworkInformation
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
ms.openlocfilehash: 333baa68f4bd80b98e8bb03929ab41dc9cbed7a1
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150954"
---
# <a name="networkinformation"></a>NetworkInformation
<xref:System.Net.NetworkInformation> 名前空間を使用すると、ネットワーク イベント、変更、統計、プロパティについての情報を収集できます。 また、<xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> クラスを使用して、リモート ホストに到達可能かどうかを確認することもできます。  
  
## <a name="network-availability-and-events"></a>ネットワークの可用性とイベント  
 <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> クラスを使用して、ネットワークのアドレスまたは可用性が変更されたかどうかを確認できます。 このクラスを使用するには、変更を処理するイベント ハンドラーを作成し、それを <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> または <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler> に関連付けます。 詳細については、「[方法: ネットワークの可用性とアドレスの変更を検出する](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md)」を参照してください。  
  
## <a name="network-statistics-and-properties"></a>ネットワークの統計情報とプロパティ  
 インターフェイスまたはプロトコルを使用して、ネットワークの統計情報とプロパティを収集できます。 <xref:System.Net.NetworkInformation.NetworkInterface>、<xref:System.Net.NetworkInformation.NetworkInterfaceType>、<xref:System.Net.NetworkInformation.PhysicalAddress> の各クラスは、特定のネットワーク インターフェイスについての情報を提供します。一方、<xref:System.Net.NetworkInformation.IPInterfaceProperties>、<xref:System.Net.NetworkInformation.IPGlobalProperties>、<xref:System.Net.NetworkInformation.IPGlobalStatistics>、<xref:System.Net.NetworkInformation.TcpStatistics>、<xref:System.Net.NetworkInformation.UdpStatistics> の各クラスは、レイヤー 3 とレイヤー 4 のパケットについての情報を提供します。 詳細については、「[方法: インターフェイス情報とプロトコル情報を取得する](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md)」を参照してください。  
  
## <a name="determine-if-a-remote-host-is-reachable"></a>リモート ホストに到達可能かどうかの確認  
 <xref:System.Net.NetworkInformation.Ping> クラスを使用して、リモート ホストがネットワークで稼働しているかどうか、また到達可能かどうかを確認できます。 詳細については、「[方法: ホストに対して ping を実行](../../../docs/framework/network-programming/how-to-ping-a-host.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [ネットワーク プログラミングのサンプル](../../../docs/framework/network-programming/network-programming-samples.md)  
 [ネットワーク情報テクノロジのサンプル](https://go.microsoft.com/fwlink/?LinkID=179564)  
 [NetStat ツール テクノロジのサンプル](https://go.microsoft.com/fwlink/?LinkID=179562)  
 [ping クライアント テクノロジのサンプル](https://go.microsoft.com/fwlink/?LinkID=179565)

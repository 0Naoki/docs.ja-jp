---
title: "Net.TCP ポート共有 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ポート アクティベーション [WCF]"
  - "ポート共有 [WCF]"
ms.assetid: f13692ee-a179-4439-ae72-50db9534eded
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Net.TCP ポート共有
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] では、高パフォーマンス通信用の新しい TCP ベースのネットワーク プロトコル \(net.tcp:\/\/\) が提供されます。  また、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] には、net.tcp ポートを複数のユーザー プロセスで共有できる新しいシステム コンポーネントとして Net.TCP ポート共有サービスが導入されています。  
  
## 背景と動機  
 TCP\/IP プロトコルの導入当初は、それを使用するアプリケーション プロトコルは少ししかありませんでした。  TCP\/IP では、ポート番号を使用して一意の 16 ビットのポート番号を各アプリケーション プロトコルに割り当てることでアプリケーションが区別されました。  たとえば、現在 HTTP トラフィックは TCP ポート 80、SMTP は TCP ポート 25、FTP は TCP ポート 20 と 21 を使用するように標準化されています。  他のアプリケーションで TCP をトランスポートとして使用する場合は、規則により、または正式な標準化を通じて別の利用可能なポート番号を選択できます。  
  
 ポート番号を使用してアプリケーションを区別することについては、セキュリティの問題がありました。  通常、ファイアウォールは、よく知られたわずかなエントリ ポイントを除いてすべてのポートの TCP トラフィックをブロックするよう構成されています。そのため、非標準のポートを使用するアプリケーションを展開する際に、企業のファイアウォールまたはパーソナル ファイアウォールがあるために展開が複雑になることや、展開が不可能になる場合がよくあります。  アプリケーションが、許可済みの標準の Well\-known ポートで通信できる場合は、外部攻撃の侵入経路を減らすことができます。  多くのファイアウォールは、TCP ポート 80 のトラフィックを既定で許可するよう構成されているため、多くのネットワーク アプリケーションが HTTP プロトコルを利用します。  
  
 多くの異なる HTTP アプリケーションのトラフィックを 1 つの TCP ポートに多重化する HTTP.SYS モデルが、Windows プラットフォームで標準になってきました。  このモデルを使用すると、ファイアウォール管理者は共通の制御点を使用できるようになり、また、アプリケーション開発者はネットワークを利用できる新しいアプリケーションを構築する際に、展開コストを最小限にできます。  
  
 インターネット インフォメーション サービス \(IIS\) には、HTTP アプリケーション間でポートを共有する機能が以前からあります。  しかし、このインフラストラクチャが完全に一般化されたのは、[!INCLUDE[iis601](../../../../includes/iis601-md.md)] での HTTP.SYS \(カーネル モードの HTTP プロトコル リスナー\) の導入以降のことでした。  実際には、HTTP.SYS が、任意のユーザー プロセスで HTTP トラフィック専用の TCP ポートを共有することを許可します。  この機能により、多数の HTTP アプリケーションが同一の物理コンピューター上にそれぞれ別の独立したプロセスとして共存しながら、TCP ポート 80 でのトラフィックの送受信に必要なネットワーク インフラストラクチャを共有することができます。  Net.TCP ポート共有サービスは、net.tcp アプリケーションで同じ種類のポート共有を可能にします。  
  
## ポート共有アーキテクチャ  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] のポート共有アーキテクチャには主に 3 つのコンポーネントがあります。  
  
-   ワーカー プロセス : 共有ポートを使用して net.tcp:\/\/ で通信するすべてのプロセスです。  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] TCP トランスポート : net.tcp:\/\/ protocol を実装します。  
  
-   Net.TCP ポート共有サービス : 多数のワーカー プロセスで 1 つの TCP ポートを共有できます。  
  
 Net.TCP ポート共有サービスは、net.tcp:\/\/ を通じて通信されるワーカー プロセスの代わりに net.tcp:\/\/ 接続を受け入れるユーザー モードの Windows サービスです。  ソケット接続が到着すると、ポート共有サービスは受信メッセージ ストリームを検査して送信先アドレスを取得します。  このアドレスを基にポート共有サービスは、最終的に処理されるアプリケーションにデータ ストリームをルーティングできます。  
  
 net.tcp:\/\/ ポート共有を使用する [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] サービスを開くときに、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] TCP トランスポート インフラストラクチャは、アプリケーション プロセスの TCP ソケットを直接開きません。  その代わりにトランスポート インフラストラクチャは、サービスのベース アドレス URI \(Uniform Resource Identifier\) を Net.TCP ポート共有サービスに登録し、ポート共有サービスがトランスポート インフラストラクチャの代わりにメッセージをリッスンするまで待機します。  アプリケーション サービス宛てのメッセージが到着すると、そのメッセージはポート共有サービスによりディスパッチされます。  
  
## ポート共有のインストール  
 Net.TCP ポート共有サービスは、[!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] をサポートするすべてのオペレーティング システムで利用できますが、サービスは既定では有効にされていません。  セキュリティ予防措置として、管理者は Net.TCP ポート共有サービスを初めて使用する前に手動で有効にする必要があります。  Net.TCP ポート共有サービスでは、ポート共有サービスが所有するネットワーク ソケットのいくつかの特性を操作するための構成オプションが公開されます。  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [方法 : Net.TCP ポート共有サービスを有効にする](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md).  
  
## アプリケーションでの Net.tcp ポート共有の使用  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] アプリケーションで net.tcp:\/\/ ポート共有を使用する最も簡単な方法は、<xref:System.ServiceModel.NetTcpBinding> を使用してサービスを公開し、<xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> プロパティを使用して Net.TCP ポート共有サービスを有効にすることです。  
  
 その方法[!INCLUDE[crabout](../../../../includes/crabout-md.md)]「[方法 : ポート共有を使用するように WCF サービスを構成する](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md)」を参照してください。  
  
## ポート共有のセキュリティへの影響  
 Net.TCP ポート共有サービスは、アプリケーションとネットワークの間に、処理を行うための 1 つの層を提供しますが、アプリケーションでポート共有を使用する場合、アプリケーションがネットワークを直接リッスンしている場合と同様に、アプリケーションをセキュリティで保護する必要があります。  具体的には、ポート共有を使用するアプリケーションでは、そのアプリケーションが実行される際のプロセス特権を評価する必要があります。  組み込みの Network Service アカウントを使用してアプリケーションを実行することを検討します。このアカウントはネットワーク通信に必要な最小限のプロセス特権のセットを使用して実行されます。  
  
## 参照  
 [Net.TCP ポート共有サービスを構成する](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)   
 [ホスト](../../../../docs/framework/wcf/feature-details/hosting.md)   
 [方法 : ポート共有を使用するように WCF サービスを構成する](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md)   
 [方法 : Net.TCP ポート共有サービスを有効にする](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md)
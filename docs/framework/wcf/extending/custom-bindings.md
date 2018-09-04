---
title: カスタム バインディング
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, endpoints
- Windows Communication Foundation, configuration
ms.assetid: 58532b6d-4eea-4a4f-854f-a1c8c842564d
ms.openlocfilehash: 694b4faaafea62799a96aabe8f023a0d495f8d50
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43540206"
---
# <a name="custom-bindings"></a>カスタム バインディング
システムが提供するバインディングの中にサービスの要件を満たすものがない場合は、<xref:System.ServiceModel.Channels.CustomBinding> クラスを使用できます。 すべてのバインディングは、バインド要素の順序付き集合から作成されます。 カスタム バインドは、一連のシステム指定のバインド要素から作成したり、ユーザー定義のカスタム バインド要素を含めたりできます。 カスタム バインド要素を使用すると、たとえば、新しいトランスポートまたはエンコーダーをサービス エンドポイントで使用できるようになります。 実施例については、次を参照してください。[カスタム バインドのサンプル](https://msdn.microsoft.com/library/657e8143-beb0-472d-9cfe-ed1a19c2ab08)します。 詳細については、次を参照してください。 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)します。  
  
## <a name="construction-of-a-custom-binding"></a>カスタム バインドの構築  
 カスタム バインディングは、特定の順序で "積み重ねられている" バインディング要素のコレクションから <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> コンストラクターを使用して作成します。  
  
-   最上位にあるのは、トランザクションのフローを可能にするオプションの <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> クラスです。  
  
-   その次にあるのは、WS-ReliableMessaging 仕様で定義されているセッションおよび順序指定のメカニズムを提供する、オプションの <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> クラスです。 セッションは、SOAP 中継局およびトランスポート中継局を通過できます。  
  
-   その次には、承認、認証、保護、機密性などのセキュリティ機能を提供する、オプションの <xref:System.ServiceModel.Channels.SecurityBindingElement> クラスがあります。  
  
-   その次には、二重通信をネイティブでサポートしないトランスポート プロトコル (HTTP など) を使用して双方向の二重通信を可能にする、オプションの <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> クラスがあります。  
  
-   その次には、一方向通信を提供する、オプションの <xref:System.ServiceModel.Channels.OneWayBindingElement> クラスがあります。  
  
-   その次にあるのは、オプションのストリーム セキュリティ バインド要素で、次のいずれかになります。  
  
    -   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
-   その次にあるのは、必須のメッセージ エンコード バインド要素です。 独自のメッセージ エンコーダーを使用するか、次の 3 つのメッセージ エンコーディング バインディングのいずれかを使用できます。  
  
    -   <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
  
 最下位には、必須のトランスポート要素があります。 独自のトランスポートまたは Windows Communication Foundation (WCF) は、次のトランスポート バインド要素の 1 つを使用することができます。  
  
-   <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.PeerTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>  
  
-   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>  
  
-   <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
 各層のオプションの概要を次の表に示します。  
  
|レイヤー|オプション|必須|  
|-----------|-------------|--------------|  
|トランザクション|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|いいえ|  
|信頼性|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|Ｘ|  
|セキュリティ|<xref:System.ServiceModel.Channels.SecurityBindingElement>|いいえ|  
|エンコード|テキスト、バイナリ、MTOM (Message Transmission Optimization Mechanism)、カスタム|はい|  
|Transport|TCP、HTTP、HTTPS、名前付きパイプ (IPC)、ピアツーピア (P2P)、メッセージ キュー (MSMQ)、カスタム|はい|  
  
 さらに、独自のバインド要素を定義し、それを定義済みの層のいずれかの間に挿入できます。  
  
## <a name="see-also"></a>関連項目  
 [エンドポイントの作成の概要](../../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [サービスとクライアントを構成するためのバインディングの使用](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [システム標準のバインディング](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [方法 : システム指定のバインディングをカスタマイズする](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)  
 [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [カスタム バインド](../../../../docs/framework/wcf/samples/custom-binding.md)

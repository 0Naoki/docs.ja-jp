---
title: "クライアント アーキテクチャ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02624403-0d77-41cb-9a86-ab55e98c7966
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e749594d7a37b89d5dbf02013b2f667d923af7ed
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2017
---
# <a name="client-architecture"></a>クライアント アーキテクチャ
アプリケーションは、[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] クライアント オブジェクトを使用してサービス操作を呼び出します。 このトピックでは、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント オブジェクト、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント チャネル、およびこれらとその基になるチャネル アーキテクチャのリレーションシップについて説明します。 基本的な概要について[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]クライアント オブジェクトを参照してください[WCF クライアントの概要](../../../../docs/framework/wcf/wcf-client-overview.md)です。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]チャネル レイヤを参照してください[、チャネル レイヤの拡張](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)です。  
  
## <a name="overview"></a>概要  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアントはサービス モデル ランタイムによって作成されます。クライアントは次の要素から構成されます。  
  
-   自動的に生成される、サービス コントラクトのクライアント実装。これは、アプリケーション コードからの呼び出しを送信メッセージに変換すると共に、応答メッセージを出力パラメーターに変換して、アプリケーションが取得できる値を返します。  
  
-   コントロール インターフェイス (<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>) の実装。これは、さまざまなインターフェイスをグループ化し、コントロールの機能 (特に、クライアント セッションの終了機能とチャネルの破棄機能) へのアクセスを提供します。  
  
-   クライアント チャネル。これは、使用するバインディングによって指定される構成設定に基づいて構築されます。  
  
 アプリケーションは、このようなクライアントを作成するオンデマンドで使用するか、<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>またはのインスタンスを作成することで、<xref:System.ServiceModel.ClientBase%601>によって生成されるクラスを派生、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)です。 これらの作成済みのクライアント クラスは、<xref:System.ServiceModel.ChannelFactory> によって動的に構築されるクライアント チャネル実装にカプセル化され、処理が代行されます。 したがって、クライアント チャネルと、クライアント チャネルを生成するチャネル ファクトリが、このトピックの説明の中心となります。  
  
## <a name="client-objects-and-client-channels"></a>クライアント オブジェクトとクライアント チャネル  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアントの基本インターフェイスは、<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> インターフェイスです。これは、中核となるクライアント機能だけでなく、<xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType> の基本的な通信オブジェクト機能、<xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType> のコンテキスト機能、および <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType> の拡張可能な動作を公開します。  
  
 ただし、<xref:System.ServiceModel.IClientChannel> インターフェイスではサービス コントラクトそのものは定義しません。 サービス コントラクト インターフェイスで宣言されている (通常のようなツールを使用してサービス メタデータから生成、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md))。 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント型は、<xref:System.ServiceModel.IClientChannel> とターゲットのサービス コントラクト インターフェイスの両方を拡張したもので、アプリケーションから直接操作を呼び出したり、クライアント側のランタイム機能にアクセスしたりできるようにします。 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアントを作成することにより、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> オブジェクトには、構成済みサービス エンドポイントに接続して対話できるランタイムの作成に必要な情報が提供されます。  
  
 上述のとおり、この 2 つの [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント型は、使用する前に構成する必要があります。 最も単純な [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント型は、<xref:System.ServiceModel.ClientBase%601> (または、サービス コントラクトが双方向コントラクトである場合は、<xref:System.ServiceModel.DuplexClientBase%601>) から派生するオブジェクトです。 これらのクライアント型はコンストラクターを使用して作成し、プログラムで構成するか、または構成ファイルを使用して構成します。また、サービス操作を呼び出すために直接呼び出されます。 基本的な概要について<xref:System.ServiceModel.ClientBase%601>、オブジェクトを参照してください[WCF クライアントの概要](../../../../docs/framework/wcf/wcf-client-overview.md)です。  
  
 2 番目のクライアント型は、実行時に <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> メソッドへの呼び出しから生成されます。 通常、通信の詳細厳重に関係していてアプリケーションと呼ばれるこのクライアントの種類を使用して、*クライアント チャネル オブジェクト*、基になるクライアント ランタイムやチャネルより直接的な対話を可能にします。システムです。  
  
## <a name="channel-factories"></a>チャネル ファクトリ  
 クライアント呼び出しをサポートする、基になるランタイムを作成するクラスは、<xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> クラスです。 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント オブジェクトも [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント チャネル オブジェクトも、<xref:System.ServiceModel.ChannelFactory%601> オブジェクトを使用してインスタンスを作成します。<xref:System.ServiceModel.ClientBase%601> 派生クライアント オブジェクトはチャネル ファクトリの処理をカプセル化しますが、さまざまなシナリオを想定した場合、チャネル ファクトリを直接使用することをお勧めします。 よくあるシナリオとしては、既存のファクトリから新しいクライアント チャネルを繰り返し作成する必要がある場合です。 クライアント オブジェクトを使用している場合は、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] プロパティを呼び出して、<xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A?displayProperty=nameWithType> クライアント オブジェクトから、基になるチャネル ファクトリを取得できます。  
  
 チャネル ファクトリに関して覚えておく必要のある重要なことは、これらのファクトリが、<xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> を呼び出す前に、指定されている構成のクライアント チャネルの新しいインスタンスを作成するという点です。 いったん <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> (または <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> や <xref:System.ServiceModel.ClientBase%601.CreateChannel%2A?displayProperty=nameWithType>、または [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント オブジェクトに対する任意の操作) を呼び出した場合、ターゲットのエンドポイント アドレスを変更するだけでは、チャネル ファクトリを変更したり、別のサービス インスタンスへのチャネルを取得したりすることはできません。 異なる構成でクライアント オブジェクトやクライアント チャネルを作成するには、まず新しいチャネル ファクトリを作成する必要があります。  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]使用してさまざまな問題[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]クライアント オブジェクトと[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]クライアント チャネルを参照してください[にアクセスするサービスの WCF クライアントを使用して](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)です。  
  
 次の 2 つのセクションでは、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント チャネル オブジェクトの作成と使用について説明します。  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>新しい WCF クライアント チャネル オブジェクトの作成  
 次のサービス コントラクトが生成されていることを前提に、クライアント チャネルの使用方法を説明します。  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 `ISampleService` サービスに接続するには、チャネル ファクトリ (<xref:System.ServiceModel.ChannelFactory%601>) を直接使用して生成したコントラクト インターフェイスを使用します。 特定のコントラクトのチャネル ファクトリを作成して構成した後は、<xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> メソッドを呼び出して、`ISampleService` サービスとの通信に使用できるクライアント チャネル オブジェクトを返すことができます。  
  
 サービス コントラクト インターフェイスで <xref:System.ServiceModel.ChannelFactory%601> クラスを使用する場合、明示的にチャネルを開いたり、閉じたり、中止したりするには、<xref:System.ServiceModel.IClientChannel> インターフェイスにキャストする必要があります。 処理を容易にするために、Svcutil.exe ツールでは、サービス コントラクト インターフェイスと <xref:System.ServiceModel.IClientChannel> の両方を実装するヘルパー インターフェイスも生成されます。これにより、キャストを行わずにクライアント チャネル インフラストラクチャとのやりとりを実現できます。 上記のサービス コントラクトを実装するヘルパー クライアント チャネルの定義を、次のコード例に示します。  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>新しい WCF クライアント チャネル オブジェクトの作成  
 クライアント チャネルを使用して `ISampleService` サービスに接続するには、チャネル ファクトリを直接使用して生成したコントラクト インターフェイス (またはヘルパー バージョン) を使用して、コントラクト インターフェイスの型を型パラメーターとして渡します。 特定のコントラクトのチャネル ファクトリを作成して構成したら、<xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> メソッドを呼び出して、`ISampleService` サービスとの通信に使用できるクライアント チャネル オブジェクトを返すことができます。  
  
 作成したクライアント チャネル オブジェクトで <xref:System.ServiceModel.IClientChannel> とコントラクト インターフェイスを実装します。 その結果、これらを使用して、このコントラクトをサポートするサービスと対話する操作を直接呼び出すことができます。  
  
 クライアント オブジェクトを使用するかクライアント チャネル オブジェクトを使用するかは、開発者がきめ細かな制御を優先するか容易さを優先するかの違いだけです。 クラスやオブジェクトの処理に慣れている多くの開発者の場合、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント チャネルではなく [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアント オブジェクトを選択することも考えられます。  
  
 例については、次を参照してください。[する方法: ChannelFactory を使用して](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)です。

---
title: "アクティビティ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70471705-f55f-4da1-919f-4b580f172665
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cbcf33aa734cde1d2458e46cd161f9ea5197a827
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="activity"></a>アクティビティ
ここでは、[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] トレース モデルのアクティビティ トレースについて説明します。 アクティビティは、ユーザーがエラーの範囲を絞り込む上で役立つ処理単位です。 同じアクティビティで発生したエラーは直接関連します。 たとえば、メッセージを復号化できなかったために、ある操作が失敗したとします。 この操作とメッセージ復号化失敗のトレースは同じアクティビティ内に表示され、復号化エラーと要求エラー間の直接相関関係が示されます。  
  
## <a name="configuring-activity-tracing"></a>アクティビティ トレースの構成  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]アプリケーションを処理するための定義済みのアクティビティの提供 (を参照してください[アクティビティ リスト](../../../../../docs/framework/wcf/diagnostics/tracing/activity-list.md))。 また、ユーザー トレースをグループ化するために、アクティビティをプログラムによって定義することもできます。 詳細については、次を参照してください。[ユーザー コード トレースの出力](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md)です。  
  
 実行時にアクティビティ トレースを出力するには、次の構成コードに示すように、`ActivityTracing` トレース ソースや、他の `System.ServiceModel` トレース ソースまたはカスタム トレース ソースの [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 設定を使用します。  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
 詳細に把握する構成要素と属性が使用されている、次を参照してください。、[トレースの構成](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)トピックです。  
  
## <a name="viewing-activities"></a>アクティビティの表示  
 アクティビティと、ユーティリティで表示できます、[サービス トレース ビューアー ツール (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)です。 ActivityTracing が有効な場合、このツールはトレースを取得し、アクティビティに基づいて並べ替えます。 トレース転送を表示することもできます。 トレース転送は、さまざまなアクティビティが相互にどのように関連しているかを示します。 これにより、特定のアクティビティによって別のアクティビティが開始されたことを確認できます。 たとえば、Secure Conversation トークンを取得するために、あるメッセージ要求によってセキュリティ ハンドシェイクが開始されたことを確認できます。  
  
### <a name="correlating-activities-in-service-trace-viewer"></a>サービス トレース ビューアーでのアクティビティの関連付け  
 次のように、サービス トレース ビューアー ツールには、アクティビティの 2 つのビューが用意されています。  
  
-   **リスト**ビュー、トレースを直接関連付けますプロセス間でアクティビティ ID が使用されています。 異なるプロセス (クライアントとサービスなど) のトレースであっても、同じアクティビティ ID を持つトレースは、同じアクティビティにグループ化されます。 したがって、サービスで発生したエラーによってクライアントでエラーが発生した場合、ツールの同じアクティビティ ビューに両方のエラーが表示されることになります。  
  
-   **グラフ**アクティビティがプロセスによってグループ化を表示します。 このビューでは、クライアントとサービスのトレースは、アクティビティ ID が同じであっても、異なるアクティビティに表示されます。 アクティビティ ID は同じであるが、異なるプロセスに含まれるアクティビティを相互に関連付けるために、このツールでは、関連するアクティビティ間のメッセージ フローが示されます。  
  
 詳細については、およびサービス トレース ビューアー ツールのグラフィカル ビューを表示するには、「[サービス トレース ビューアー ツール (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)と[相関トレースの表示のサービス トレース ビューアーを使用して、トラブルシューティング](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)です。  
  
## <a name="defining-the-scope-of-an-activity"></a>アクティビティ スコープの定義  
 アクティビティはデザイン時に定義され、作業の論理単位を表します。 同じアクティビティ識別子を使用して出力されたトレースは直接関連し、同じアクティビティに含まれます。 アクティビティはエンドポイントの境界を越えることができるため (要求など)、アクティビティには 2 つのスコープが定義されています。  
  
-   `Global` スコープ (アプリケーションごと)。 このスコープでは、アクティビティは 128 ビットの、グローバルに一意なアクティビティ識別子 (gAId) によって識別されます。 gAId は、エンドポイント全体にわたって伝達されます。  
  
-   `Local` スコープ (エンドポイントごと)。 このスコープでは、アクティビティは、gAId、アクティビティ トレースを出力するトレース ソース名、およびプロセス ID によって識別されます。この 3 つの組み合わせによって、ローカル アクティビティ ID (lAId) が構成されます。 lAId は、アクティビティの (ローカル) 境界の定義に使用されます。  
  
## <a name="trace-schema"></a>トレース スキーマ  
 トレースはスキーマを使用して Microsoft プラットフォーム間で出力できます。 "e2e"(「エンド ツー エンド」) には、一般的に使用されるスキーマです。 このスキーマには、128 ビット識別子 (gAId)、トレース ソース名、およびプロセス ID が含まれます。 マネージ コードでは、<xref:System.Diagnostics.XmlWriterTraceListener> が e2e スキーマでトレースを出力します。  
  
 開発者は、スレッド ローカル ストレージ (TLS) の GUID を使用して <xref:System.Diagnostics.CorrelationManager.ActivityId%2A> プロパティを設定することにより、トレースで出力する AID を設定できます。 次に例を示します。  
  
```  
// set the current Activity ID to a new GUID.  
CorrelationManager.ActivityId = Guid.NewGuid();  
```  
  
 次の例に示すように、トレース ソースを使用してトレースを出力すると、TLS での gAId の設定が明確に示されます。  
  
```  
TraceSource traceSource = new TraceSource("myTraceSource");  
traceSource.TraceEvent(TraceEventType.Warning, eventId, "Information");  
```  
  
 出力されるトレースには、TLS の現在の gAId、トレース ソースのコンストラクターにパラメーターとして渡されるトレース ソース名、および現在のプロセスの ID が含まれます。  
  
## <a name="activity-lifetime"></a>アクティビティの有効期間  
 最も厳密な意味では、アクティビティの形跡は、出力されたトレースでアクティビティ ID が初めて使用されたときに始まり、出力されたトレースでアクティビティ ID が最後に使用されたときに終わります。 <xref:System.Diagnostics> には、定義済みのトレースの種類のセットが用意されています。これは、アクティビティの有効期間の境界を明示的にマークするための Start トレースと Stop トレースを含みます。  
  
-   Start: アクティビティの開始を示します。 "Start"トレースは、新しい処理マイルス トーンの開始のレコードを示します。 このトレースには、特定のプロセスの特定のトレース ソースに使用される新しいアクティビティ ID が含まれます。ただし、エンドポイント間でアクティビティ ID が伝達される場合を除きます (この場合は、エンドポイントごとに 1 つの "Start" トレースが表示されます)。 新しいアクティビティの開始の例として、新しい処理スレッドの作成や、新しいパブリック メソッドの入力などがあります。  
  
-   Stop: アクティビティの終了を示します。 "Stop"トレースは、既存の処理マイルス トーンの終了のレコードを示します。 このトレースには、特定のプロセスの特定のトレース ソースに使用される既存のアクティビティ ID が含まれます。ただし、エンドポイント間でアクティビティ ID が伝達される場合を除きます (この場合は、エンドポイントごとに 1 つの "Stop" トレースが表示されます)。  アクティビティの停止の例には、処理スレッドの終了や、先頭が"Start"トレースによって示されたメソッドの終了が含まれます。  
  
-   Suspend: アクティビティの処理の中断を示します。 "Suspend"トレースには、処理されるは後で再開が予想される既存のアクティビティ ID が含まれています。 中断イベントと再開イベントの間に、現在のトレース ソースからこの ID を使用してトレースが出力されることはありません。 中断の例として、外部ライブラリ関数の呼び出し時、または I/O 完了ポートなどのリソースで待機する際のアクティビティの一時停止などがあります。  
  
-   Resume: アクティビティの処理の再開を示します。 "Resume"トレースには、現在のトレース ソースからの最後が出力されたトレースが"Suspend"トレースであった既存のアクティビティ id が含まれています。 再開の例として、外部ライブラリ関数の呼び出しからの復帰や、I/O 完了ポートなどのリソースによって処理の再開が通知された場合などがあります。  
  
-   Transfer: 一部のアクティビティが発生し、他のユーザー、他のユーザーに関連付けるために、アクティビティが"Transfer"トレースには、他のアクティビティに関連ことができます。 転送により、アクティビティ間の直接の関係が記録されます。  
  
 Start トレースと Stop トレースは、関連付けにとっては重要ではありません。 ただし、これらのトレースは、パフォーマンスの向上、プロファイリング、およびアクティビティ スコープの検証に役立ちます。  
  
 同じアクティビティの直接関連するイベントを検出するときや、転送トレースを追跡する場合に関連アクティビティのイベントを検出するときに、ツールはこれらのトレースを使用して、トレース ログのナビゲーションを最適化することができます。 たとえば、ツールが Start/Stop トレースを確認したときに、特定のアクティビティのログの解析を中止できます。  
  
 Start/Stop トレースは、プロファイリングに使用することもできます。 開始マーカーと終了マーカーの間で使用されるリソースは、論理アクティビティを含むアクティビティの包括時間を表します。 Suspend トレースから Resume トレースまでの時間間隔を減算することで、アクティビティの実際の時間がわかります。  
  
 また、Stop トレースは、実装済みのアクティビティのスコープを検証する際に特に役立ちます。 特定のアクティビティ内ではなく Stop トレースの後に出現する処理トレースがある場合、これはコードの欠陥を示している可能性があります。  
  
## <a name="guidelines-for-using-activity-tracing"></a>アクティビティ トレースを使用するためのガイドライン  
 ActivityTracing トレース (Start、Stop、Suspend、Resume、および Transfer) を使用する際のガイドラインを以下に示します。  
  
-   トレースは、ツリーではなく循環有向グラフです。 あるアクティビティを発生させたアクティビティに制御を戻すことができます。  
  
-   アクティビティは処理の境界を示します。処理の境界は、システム管理者にとって重要であり、サポートを容易にする上でも役立ちます。  
  
-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] の各メソッド (クライアントとサーバーの両方) は、新しいアクティビティを開始し、(処理の終了後に) その新しいアクティビティを終了した後、アンビエント アクティビティに戻ることによって境界が設定されます。  
  
-   接続のリッスンやメッセージの待機など、長時間にわたって実行される (継続中の) アクティビティは、対応する開始マーカーと終了マーカーによって表されます。  
  
-   メッセージの受信または処理によって起動されるアクティビティは、トレースの境界によって表されます。  
  
-   アクティビティはアクティビティを表します。オブジェクトとは限りません。 アクティビティとして解釈する必要があります"これが発生しているときにします。 である必要があります。 である必要があります。 (有効なトレース出力が発生したときに) これが発生していた" と解釈する必要があります。  
  
## <a name="see-also"></a>参照  
 [トレースの構成](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [サービス トレース ビューアーを使用した相関トレースの表示とトラブルシューティング](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [エンドツーエンドのトレースのシナリオ](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 [サービス トレース ビューアー ツール (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [ユーザー コード トレースの出力](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md)

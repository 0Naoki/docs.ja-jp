---
title: ADO.NET のデータ追跡
ms.date: 03/30/2017
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
ms.openlocfilehash: 037db6f4e5695e00401c81e1490953efe2fc9b99
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421100"
---
# <a name="data-tracing-in-adonet"></a>ADO.NET のデータ追跡
SQL Server、Oracle、OLE DB と ODBC だけでなく、ADO.NET の .NET データ プロバイダーでサポートされている組み込みデータ トレース機能を搭載した ADO.NET <xref:System.Data.DataSet>、および SQL Server のネットワーク プロトコル。  
  
 データ アクセス API 呼び出しのトレースは、次の問題を診断する際に役立ちます。  
  
-   クライアント プログラムとデータベース間のスキーマの不一致  
  
-   データベースの使用不可またはネットワーク ライブラリの問題  
  
-   誤った SQL がアプリケーションによりハードコーディングまたは生成された  
  
-   プログラミング ロジックが不適切  
  
-   複数の ADO.NET コンポーネント間または ADO.NET と独自コンポーネント間の対話に起因する問題  
  
 トレースを拡張することにより異なるトレース技術をサポートできます。このため、開発者はアプリケーション スタックのあらゆるレベルで問題をトレースできます。 トレースは ADO.NET のみで使用できる機能ではありませんが、Microsoft プロバイダーでは、汎用トレース機能および instrumentation API を活用しています。  
  
 設定して、ADO.NET におけるマネージ トレースの構成の詳細については、次を参照してください。[データ アクセスのトレース](https://msdn.microsoft.com/library/hh880086.aspx)します。  
  
## <a name="accessing-diagnostic-information-in-the-extended-events-log"></a>拡張イベント ログの診断情報へのアクセス  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server では、データ アクセス トレース ([データ アクセスのトレース](https://msdn.microsoft.com/library/hh880086.aspx)) が容易にできるようにからの接続の障害などの診断情報とクライアントのイベントを関連付けるために簡単に更新されました、サーバーの接続のリング バッファーやアプリケーションのパフォーマンス情報を拡張イベント ログでします。 拡張イベント ログの読み取り方法の詳細については、次を参照してください。[イベント セッション データの表示](https://msdn.microsoft.com/library/hh710068\(SQL.110\).aspx)します。  
  
 接続操作では、ADO.NET はクライアント接続 ID を送信します。 接続に失敗した場合、接続リング バッファーを表示できます ([接続リング バッファーによる SQL Server 2008 のトラブルシューティング](https://go.microsoft.com/fwlink/?LinkId=207752)) を見つけて、`ClientConnectionID`フィールドでに関する診断情報を取得し、接続エラーです。 クライアント接続 ID は、エラーが発生した場合にのみリング バッファーに記録されます。 (接続がログイン前のパケットを送信する前に失敗すると、クライアント接続 ID は生成されません。)クライアント接続 ID は 16 バイトの GUID です。 拡張イベント セッション内のイベントに `client_connection_id` アクションが追加された場合にも、拡張イベントのターゲット出力のクライアント接続 ID を見つけることができます。 それ以上にクライアントのドライバーの診断について支援が必要な場合は、データ アクセスのトレースを有効にし、接続コマンドを再実行して、データ アクセスのトレースの `ClientConnectionID` フィールドを確認することができます。  
  
 `SqlConnection.ClientConnectionID` プロパティを使用して、クライアント接続 ID をプログラムによって取得できます。  
  
 `ClientConnectionID` は、正常に接続を確立する <xref:System.Data.SqlClient.SqlConnection> オブジェクトで使用できます。 接続試行が失敗すると、`ClientConnectionID` は `SqlException.ToString` を通じて利用可能になることがあります。  
  
 ADO.NET は、スレッド固有のアクティビティ ID も送信します。 TRACK_CAUSAILITY オプションが有効な状態でセッションが開始されると、アクティビティ ID は拡張イベントのセッションでキャプチャされます。 アクティブな接続のパフォーマンスの問題については、クライアントのデータ アクセスのトレース (`ActivityID` フィールド) からアクティビティ ID を取得した後、その拡張イベントの出力のアクティビティ ID を検索できます。 拡張イベントのアクティビティ ID は 16 バイトの GUID (クライアント接続 ID の GUID と同じではありません) であり、4 バイトのシーケンス番号が追加されています。 シーケンス番号は、スレッド内で要求の順序を表し、スレッドのバッチと RPC ステートメントの相対的順序を示します。 `ActivityID` は、現在、データ アクセスのトレースが有効な場合、データ アクセスのトレースの構成のワードの 18 番目のビットが有効にされると、オプションとして SQL のバッチ ステートメントと RPC の要求に送信されるようになっています。  
  
 次は、リング バッファーに格納され、RPC とバッチ操作でクライアントから送信されるアクティビティ ID を記録する拡張イベントのセッションを開始するために [!INCLUDE[tsql](../../../../includes/tsql-md.md)] を使用するサンプルです。  
  
```  
create event session MySession on server   
add event connectivity_ring_buffer_recorded,   
add event sql_statement_starting (action (client_connection_id)),   
add event sql_statement_completed (action (client_connection_id)),   
add event rpc_starting (action (client_connection_id)),   
add event rpc_completed (action (client_connection_id))  
add target ring_buffer with (track_causality=on)  
```  
  
## <a name="see-also"></a>関連項目  
 [.NET Framework のネットワークのトレース](../../../../docs/framework/network-programming/network-tracing.md)  
 [アプリケーションのトレースとインストルメント](../../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 [ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター](https://go.microsoft.com/fwlink/?LinkId=217917)

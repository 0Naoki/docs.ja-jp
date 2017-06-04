---
title: "複数のアクティブな結果セット (MARS) の有効化 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 576079e4-debe-4ab5-9204-fcbe2ca7a5e2
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# 複数のアクティブな結果セット (MARS) の有効化
複数のアクティブな結果セット \(MARS : Multiple Active Result Set\) は、SQL Server で動作する機能であり、複数のバッチを単一の接続で実行することができます。  SQL Server で使用できるように MARS が有効になっているときは、使用中の各コマンド オブジェクトは接続にセッションを追加します。  
  
> [!NOTE]
>  単一の MARS セッションは、MARS 用に 1 つの論理接続を開いた後、アクティブな各コマンドにつき 1 つの論理接続を開きます。  
  
## 接続文字列で MARS を有効または無効にする  
  
> [!NOTE]
>  次の接続文字列では、SQL Server に含まれるサンプルの **AdventureWorks** データベースを使用します。  指定されている接続文字列は、データベースが MSSQL1 という名前のサーバーにインストールされていることを前提としています。  必要に応じて、お使いの環境に合わせて接続文字列を変更してください。  
  
 既定では、MARS 機能は無効になっています。  この機能を有効にするには、キーワード ペア "MultipleActiveResultSet\=True" を接続文字列に追加します。"  True" は、MARS を有効にするための唯一の有効な値です。  次の例では、SQL Server のインスタンスに接続し、MARS が有効になるよう指定する方法について説明します。  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=True"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=True";  
```  
  
 MARS を無効にするには、キーワード ペア "MultipleActiveResultSet\=False" を接続文字列に追加します。"  False" は、MARS を無効にするための唯一の有効な値です。  次の接続文字列では、MARS を無効にしています。  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=False"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=False";  
```  
  
## MARS の使用に関する特記事項  
 一般に、MARS の有効な接続を使用するために、既存のアプリケーションを修正する必要はありません。  ただし、MARS 機能をご自分のアプリケーションで使用する場合、次の特記事項について理解しておく必要があります。  
  
### ステートメント インタリーブ  
 MARS 操作は、サーバー上で同期して実行されます。  SELECT ステートメントと BULK INSERT ステートメントをインタリーブすることができます。  ただし、DML \(データ操作言語\) と DDL \(データ定義言語\) のステートメントはアトミック実行されます。  バッチのアトミック実行中にステートメントを実行しようとすると、いずれもブロックされます。  サーバーでの並列実行は MARS の機能ではありません。  
  
 MARS 接続において、SELECT ステートメントを含むバッチと DML ステートメントを含むバッチの 2 つが送信されると、SELECT ステートメントの実行中に DML の実行が開始されます。  ただし、DML ステートメントは SELECT ステートメントが進行する前に実行を完了しなければなりません。  両方のステートメントが同じトランザクションで実行されている場合、SELECT ステートメントの実行を開始した後に行われた DML ステートメントによる変更は、読み取り操作では表示されません。  
  
 SELECT ステートメント内の WAITFOR ステートメントは、待機中、つまり最初の行が作成されるまではトランザクションを生成しません。  これは、WAITFOR ステートメントが待機している間は、同一の接続内では他のいかなるバッチも実行されないことを意味します。  
  
### MARS セッションのキャッシュ  
 MARS を有効にして接続が開かれている場合、論理セッションが作成されます。このセッションによってオーバーヘッドが増加します。  オーバーヘッドを最小化してパフォーマンスを向上させるため、**SqlClient** は接続内の MARS セッションをキャッシュします。  キャッシュには、最大 10 個の MARS セッションが含まれます。  ユーザーがこの値を変更することはできません。  セッションが限度に達すると新しいセッションが作成され、エラーは生成されません。  キャッシュとそのキャッシュに含まれるセッションは、接続ごとに作成されます。接続をまたいで共有されることはありません。  セッションが解放されると、プールの上限に達している場合を除き、セッションはプールに返されます。  キャッシュ プールがいっぱいになっている場合、セッションは閉じられます。  MARS セッションの有効期限は終了しません。  クリーンアップされるのは、接続オブジェクトが破棄されるときだけです。  MARS セッションのキャッシュはプリロードされません。  アプリケーションがさらに多くのセッションを要求したときに読み込まれます。  
  
### スレッド セーフ  
 MARS 操作は、スレッド セーフではありません。  
  
### 接続プール  
 MARS の有効な接続は、その他の接続と同じようにプールされます。  アプリケーションが 2 つの接続を開き、その一方は MARS が有効で他方は MARS が無効になっている場合、それら 2 つの接続は別々のプールに入れられます。  詳細については、「[SQL Server の接続プール \(ADO.NET\)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)」を参照してください。  
  
### SQL Server のバッチ実行環境  
 接続を開くとき、既定の環境が定義されます。  この環境は、MARS の論理セッションにコピーされます。  
  
 バッチ実行環境には、次のコンポーネントが含まれます。  
  
-   SET オプション \(ANSI\_NULLS、DATE\_FORMAT、LANGUAGE、TEXTSIZE など\)  
  
-   セキュリティ コンテキスト \(ユーザーまたはアプリケーションのロール\)  
  
-   データベース コンテキスト \(現在のデータベース\)  
  
-   実行状態を表す変数 \(@@ERROR、@@ROWCOUNT、@@FETCH\_STATUS、@@IDENTITY など\)  
  
-   最上位の一時テーブル  
  
 MARS を使用すると、既定の実行環境が接続に関連付けられます。  所定の接続で実行を開始する新しいバッチは、いずれも既定の環境のコピーを受け取ります。  コードが所定のバッチで実行されるときは、その環境に対して行われるすべての変更は、常に特定のバッチにスコープ設定されます。  実行が完了すると、実行の設定は既定の環境にコピーされます。  単一のバッチが複数のコマンドを発行し、それらが同じトランザクションで連続して実行される場合、そのセマンティクスは、以前のクライアントやサーバーを含む接続で公開されているときのセマンティクスと同じです。  
  
### 並列実行  
 MARS は、アプリケーション内で複数の接続に対するすべての要件を削除するようには設計されていません。  アプリケーションがサーバーに対するコマンドの完全な並列実行を必要とする場合、複数の接続を使用する必要があります。  
  
 たとえば、次のようなシナリオがあるとします。  2 つのコマンド オブジェクトが作成され、一方は結果セットを処理し、もう一方はデータを更新するとします。それらは MARS を介して共通の接続を共有します。  このシナリオでは、最初のコマンド オブジェクトの結果をすべて読み取るまで、`Transaction`.`Commit` による更新に失敗し、次の例外が発生します。  
  
 メッセージ: トランザクション コンテキストを他のセッションが使用中です。  
  
 ソース: .Net SqlClient Data Provider  
  
 期待される出力: \(null\)  
  
 受信: System.Data.SqlClient.SqlException  
  
 このシナリオに対応するには、次の 3 つの方法があります。  
  
1.  リーダーが作成されてからトランザクションを開始し、リーダーがトランザクションの一部にならないようにします。  すべての更新は、それ自身のトランザクションになります。  
  
2.  リーダーが閉じてからすべての操作をコミットします。  この場合、後続の更新バッチが実行される可能性があります。  
  
3.  MARS を使用せず、代わりに MARS が導入される以前に行っていたように、コマンド オブジェクトごとに別々の接続を使用します。  
  
### MARS サポートの検出  
 アプリケーションは、`SqlConnection.ServerVersion` の値を読み取って MARS サポートを確認することができます。  SQL Server 2005 のメジャー番号は 9、SQL Server 2008 のメジャー番号は 10 です。  
  
## 参照  
 [複数のアクティブな結果セット \(MARS\)](../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)   
 [ADO.NET Managed Providers and DataSet Developer Center \(ADO.NET マネージ プロバイダーと DataSet デベロッパー センター\)](http://go.microsoft.com/fwlink/?LinkId=217917)
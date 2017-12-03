---
title: "インスタンス ストア"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2629668-0923-4987-b943-67477131c1e0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c794c6e20b479ea4686caba29704f8851d108432
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2017
---
# <a name="instance-stores"></a>インスタンス ストア
インスタンス ストアは、インスタンスの論理コンテナーです。 この場所には、インスタンス データとメタデータが格納されます。 インスタンス ストアは、専用の物理的なストレージを意味しているわけではありません。 インスタンス ストアには SQL Server データベースの永続的な情報と、メモリ内の非永続的な状態の情報が含まれます。 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] には SQL Workflow Instance Store が付属しています。これはインスタンス ストアの具象実装で、ワークフローが SQL Server 2005 または SQL Server 2008 データベースにインスタンス データとメタデータを永続化できるようにします。 また、Windows Server App Fabric には、インスタンス ストアの具象実装も用意されています。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Windows Server App Fabric のインスタンス ストア、クエリ、およびコントロール プロバイダー](http://go.microsoft.com/fwlink/?LinkID=201201&clcid=0x409)です。  
  
 永続化 API は、ホストがコマンド要求 (<xref:System.Activities.DurableInstancing.LoadWorkflowCommand> や <xref:System.Activities.DurableInstancing.SaveWorkflowCommand> など) をインスタンス ストアに送信できるようにするための、ホストとインスタンス ストア間のインターフェイスです。 この API の具象実装は、永続化プロバイダーと呼ばれます。 永続化プロバイダーはホストからの要求を受け取り、インスタンス ストアを変更します。  
  
 ホストで多くのインスタンス ストアを使用し、インスタンス ストアを多くのホストで使用できるように、ホストとインスタンス ストアはプラグ可能です。 通常、インスタンス ストアは特定のホストの使用パターンに合わせて最適化されますが、インスタンス ストアとホストはそれぞれのライフ サイクルで進化する場合があります。 たとえば、 **WorkflowServiceHost**と**SqlWorkflowInstanceStore**連携して動作するよう設計されています。 ワークフロー サービス インスタンスのデータおよびメタデータを永続化を使用してそのインスタンス ストアを使用して、独自のインスタンス ストアを作成することができます、 **WorkflowServiceHost**です。 たとえば、SQL Server データベースに保存するのではなく、OracleWorkflowInstanceStore を作成して、ワークフローに Oracle データベースに情報を永続化させることができます。  
  
 通常、ホストは保存されたオブジェクトを変更する機能を追加して拡張されます。 たとえば、インスタンス永続化システムには、ワークフローのホストでは、「中断」操作、および SQL インスタンス ストアをサポートする拡張機能があります。  ワークフロー ホストは保存または読み込みなどの標準的なコマンドを送信して、インスタンス ストアに対してワークフローの保存または読み込みを行ったり、インスタンス ストアにワークフローを保存したりします。 中断されたワークフロー インスタンスが読み込まれないように、中断の拡張機能によって、ワークフロー インスタンスの保存および読み込みを行うコマンドに追加のセマンティクスが追加されます。 SQL インスタンス ストアの永続化プロバイダーは、ワークフロー インスタンスの保存と読み込み用のコマンドを理解し、SQL Server データベースの永続オブジェクトのテーブルを変更する適切なストアド プロシージャを呼び出して、コマンドを実装します。  
  
 インスタンス ストア内では、ホストはインスタンスの所有者として動作します。 ホストは、同時に複数のインスタンス ストアを持つ複数のインスタンスの所有者として動作します。 ホストはインスタンスに関連付けられているインスタンス キーの GUID を提供します。 インスタンス キーは、インスタンスを識別する一意の別名です。 永続化システムは、ホストが要求したコマンドを実行するときに、インスタンスの所有者情報を作成、更新、および削除します。  
  
 ホストとインスタンス ストアとの対話に関連する重要な手順を次に示します。  
  
1.  取得、 **InstanceStore**永続化プロバイダーからです。  

2.  呼び出してインスタンスへのハンドルを取得、<xref:System.Runtime.DurableInstancing.InstanceStore.CreateInstanceHandle%2A>メソッドを**InstanceStore**です。  
  
3.  呼び出して、インスタンス ハンドルに対してコマンドを呼び出し、<xref:System.Runtime.DurableInstancing.InstanceStore.Execute%2A>メソッドを**InstanceStore**です。  
  
4.  確認、<xref:System.Runtime.DurableInstancing.InstanceView>によって返される**InstanceStore.Execute**コマンドの結果を確認します。
